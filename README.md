# Data Catalog

This repository contains three files: `datacatalog.php`, `fetch.php`, and `pydruid_fetch.py`, which together provide functionality to display a data catalog with dynamic data fetching from Druid.

## Functionality

- `datacatalog.php`: This PHP script generates an HTML table displaying metadata from a CSV file (`metadata.csv`). It sanitizes the data, creates clickable links for the "File Name" column, and passes the filename to the `fetch.php` script when clicked.

- `fetch.php`: This PHP script handles the request when a link in the "File Name" column is clicked. It executes the `pydruid_fetch.py` Python script, passing the filename as a command-line argument. It then parses the JSON response and dynamically generates an HTML table to display the data.

- `pydruid_fetch.py`: This Python script connects to a local Druid server, executes a SQL query with the provided filename, and returns the queried data in JSON format.

## Local Deployment

To deploy and run this data catalog locally:

1. Ensure that you have PHP and Python 3 installed on your local machine.

2. Configure the necessary settings:
   - Ensure that the CSV file `metadata.csv` is present and contains the metadata information.
   - Modify the Druid connection details (`druid_host`, `druid_port`, `druid_path`, `druid_scheme`) in `pydruid_fetch.py` to match your local Druid server configuration.

3. Start a local web server to run the PHP scripts.
4. Access the data catalog in your web browser by visiting http://localhost:8000/datacatalog.php.
5. Ensure that druid services are running.

Note: These files are configured for local deployment and are not intended for production server deployment. To deploy on a server, you'll need to update the configuration settings accordingly.
