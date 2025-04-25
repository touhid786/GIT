import pandas as pd
import unicodedata
import re
import os

def clean_employee_id(series):
    def normalize(val):
        val = str(val)
        val = unicodedata.normalize("NFKD", val)
        val = val.encode("ascii", errors="ignore").decode("utf-8")
        val = re.sub(r"\s+", "", val)  # remove all whitespace
        val = re.sub(r"[^\w]", "", val)  # remove non-alphanumeric
        val = val.upper().strip()
        return val

    return series.fillna("").apply(normalize)

def filter_and_generate_excel(file1_path, file2_path, result_file_path):
    try:
        print("Reading Excel files...")
        df1 = pd.read_excel(file1_path, usecols=['EmployeeId', 'EmployeeName'], engine='openpyxl')
        df2 = pd.read_excel(file2_path, usecols=['EmployeeId', 'ManagerId'], engine='openpyxl')

        print("Cleaning EmployeeId columns...")
        df1['EmployeeId'] = clean_employee_id(df1['EmployeeId'])
        df2['EmployeeId'] = clean_employee_id(df2['EmployeeId'])

        df1.drop_duplicates(subset='EmployeeId', inplace=True)
        df2.drop_duplicates(subset='EmployeeId', inplace=True)

        print("Merging on EmployeeId...")
        merged_df = pd.merge(df1, df2, on='EmployeeId', how='inner')
        result_df = merged_df[['EmployeeId', 'EmployeeName', 'ManagerId']]
        result_df.to_excel(result_file_path, index=False, engine='openpyxl')

        print(f"\nFiltered results saved to: {result_file_path}")
        print(f"Total matched records: {len(result_df)}")
        print("\nSample of matched records:")
        print(result_df.head(10))

        # Debug unmatched
        unmatched_file1 = df1[~df1['EmployeeId'].isin(df2['EmployeeId'])]
        unmatched_file2 = df2[~df2['EmployeeId'].isin(df1['EmployeeId'])]

        print(f"\nUnmatched IDs in File1: {len(unmatched_file1)}")
        print(f"Unmatched IDs in File2: {len(unmatched_file2)}")

        # Export unmatched to Excel
        unmatched1_path = os.path.join(os.path.dirname(result_file_path), "unmatched_from_file1.xlsx")
        unmatched2_path = os.path.join(os.path.dirname(result_file_path), "unmatched_from_file2.xlsx")
        unmatched_file1.to_excel(unmatched1_path, index=False, engine='openpyxl')
        unmatched_file2.to_excel(unmatched2_path, index=False, engine='openpyxl')
        print(f"Unmatched records saved to:\n  {unmatched1_path}\n  {unmatched2_path}")

    except FileNotFoundError as fnf_error:
        print(f"File not found: {fnf_error}")
    except MemoryError:
        print("MemoryError: Try converting files to CSV or reading in chunks.")
    except Exception as e:
        print(f"Unexpected error: {e}")

# File paths
file1_path = 'C:\\PYTHON\\File1.xlsx'
file2_path = 'C:\\PYTHON\\File2.xlsx'
result_file_path = 'C:\\PYTHON\\results.xlsx'

filter_and_generate_excel(file1_path, file2_path, result_file_path)
