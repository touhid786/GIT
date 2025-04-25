import pandas as pd

def filter_and_generate_excel(file1_path, file2_path, result_file_path):
    try:
        # Load only required columns — this reduces memory usage
        df1 = pd.read_excel(file1_path, usecols=['EmployeeId', 'EmployeeName'], engine='openpyxl')
        df2 = pd.read_excel(file2_path, usecols=['EmployeeId', 'ManagerId'], engine='openpyxl')

        # Normalize data types (very important for consistent merge)
        df1['EmployeeId'] = df1['EmployeeId'].astype(str).str.strip()
        df2['EmployeeId'] = df2['EmployeeId'].astype(str).str.strip()

        # Efficient inner join on EmployeeId
        merged_df = pd.merge(df1, df2, on='EmployeeId', how='inner')

        # Select the required columns
        result_df = merged_df[['EmployeeId', 'EmployeeName', 'ManagerId']]

        # Write results to Excel
        result_df.to_excel(result_file_path, index=False, engine='openpyxl')

        print(f"Filtered results saved successfully to: {result_file_path}")
        
        # Display the results
        print(result_df.head(10))  # Display the first 10 records

    except FileNotFoundError as fnf_error:
        print(f"File not found: {fnf_error}")
    except ValueError as ve:
        print(f"ValueError: {ve}")
    except MemoryError:
        print("MemoryError: The operation ran out of memory. Consider using chunksize or optimizing the dataset.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Define file paths
file1_path = 'C:\\PYTHON\\File1.xlsx'
file2_path = 'C:\\PYTHON\\File2.xlsx'
result_file_path = 'C:\\PYTHON\\results.xlsx'

# Call the function to filter and generate the Excel file
filter_and_generate_excel(file1_path, file2_path, result_file_path)
