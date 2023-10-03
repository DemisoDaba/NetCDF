import netCDF4 as nc
import pandas as pd

# Specify the name of your NetCDF file
netcdf_file_name = "myfile.nc"

# Open the NetCDF file for reading
nc_file = nc.Dataset(netcdf_file_name, 'r')

# Loop through all variables in the NetCDF file
for variable_name in nc_file.variables.keys():
    # Extract the data from the NetCDF file
    data = nc_file.variables[variable_name][:]
    
    # Create a DataFrame from the data
    df = pd.DataFrame(data)
    
    # Define the CSV file name
    csv_file_name = f"{variable_name}.csv"
    
    # Save the DataFrame to a CSV file in the same directory
    df.to_csv(csv_file_name, index=False)
    
    print(f"Converted and saved {variable_name} to {csv_file_name}")

# Close the NetCDF file
nc_file.close()
