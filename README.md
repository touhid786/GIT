# GIT


import pandas as pd

def filter_and_generate_excel(file1_path, file2_path, result_file_path):
    try:
        # Load only required columns — this reduces memory usage
        df1 = pd.read_excel(file1_path, usecols=['EmployeeId', 'EmployeeName', 'ManagerId'], engine='openpyxl')
        df2 = pd.read_excel(file2_path, usecols=['EmployeeId'], engine='openpyxl')

        # Normalize data types (very important for consistent merge)
        df1['EmployeeId'] = df1['EmployeeId'].astype(str).str.strip()
        df2['EmployeeId'] = df2['EmployeeId'].astype(str).str.strip()

        # Efficient inner join on EmployeeId
        merged_df = pd.merge(df1, df2, on='EmployeeId', how='inner')

        # Write results to Excel
        merged_df.to_excel(result_file_path, index=False, engine='openpyxl')

        print(f"Filtered results saved successfully to: {result_file_path}")

    except FileNotFoundError as fnf_error:
        print(f"File not found: {fnf_error}")
    except Exception as e:
        print(f"Error occurred: {e}")

# File paths
file1_path = 'C:\\PYTHON\\File1.xlsx'
file2_path = 'C:\\PYTHON\\File2.xlsx'
result_file_path = 'C:\\PYTHON\\results.xlsx'

filter_and_generate_excel(file1_path, file2_path, result_file_path)
