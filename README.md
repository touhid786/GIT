import pandas as pd
import unicodedata

def clean_employee_id(series):
    # Normalize Unicode, remove non-ASCII, remove special characters, strip, uppercase
    return (
        series.astype(str)
        .apply(lambda x: unicodedata.normalize("NFKD", x))
        .str.encode("ascii", errors="ignore").str.decode("utf-8")
        .str.replace(r"[^\w]", "", regex=True)  # Remove non-word characters
        .str.strip()
        .str.upper()
    )

def filter_and_generate_excel(file1_path, file2_path, result_file_path):
    try:
        print("Reading input files...")
        df1 = pd.read_excel(file1_path, usecols=['EmployeeId', 'EmployeeName'], engine='openpyxl')
        df2 = pd.read_excel(file2_path, usecols=['EmployeeId', 'ManagerId'], engine='openpyxl')

        print("Cleaning EmployeeId columns...")
        df1['EmployeeId'] = clean_employee_id(df1['EmployeeId'])
        df2['EmployeeId'] = clean_employee_id(df2['EmployeeId'])

        print("Dropping duplicates...")
        df1.drop_duplicates(subset='EmployeeId', inplace=True)
        df2.drop_duplicates(subset='EmployeeId', inplace=True)

        print("Merging data on EmployeeId...")
        merged_df = pd.merge(df1, df2, on='EmployeeId', how='inner')

        result_df = merged_df[['EmployeeId', 'EmployeeName', 'ManagerId']]
        result_df.to_excel(result_file_path, index=False, engine='openpyxl')

        print(f"\nFiltered results saved to: {result_file_path}")
        print(f"Total records in File1: {len(df1)}")
        print(f"Total records in File2: {len(df2)}")
        print(f"Total matched records: {len(result_df)}")
        print("\nSample matches:")
        print(result_df.head(10))

        # Optional: Show some EmployeeIds that did not match (debugging)
        unmatched_ids_1 = df1[~df1['EmployeeId'].isin(df2['EmployeeId'])]
        unmatched_ids_2 = df2[~df2['EmployeeId'].isin(df1['EmployeeId'])]

        print(f"\nUnmatched in File1: {len(unmatched_ids_1)}")
        print(f"Unmatched in File2: {len(unmatched_ids_2)}")

    except FileNotFoundError as fnf_error:
        print(f"File not found: {fnf_error}")
    except MemoryError:
        print("MemoryError: Try splitting the files or converting to CSV.")
    except Exception as e:
        print(f"Unexpected error: {e}")

# File paths
file1_path = 'C:\\PYTHON\\File1.xlsx'
file2_path = 'C:\\PYTHON\\File2.xlsx'
result_file_path = 'C:\\PYTHON\\results.xlsx'

filter_and_generate_excel(file1_path, file2_path, result_file_path)
