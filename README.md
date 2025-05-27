# Nagios Reporting Script

This script retrieves data from Nagios using its JSON API, generates an Excel report with host and service statuses, and creates a corresponding PDF summary.

## Dependencies

- `requests`: For making HTTP requests to Nagios API.
- `pandas`: For handling data in DataFrame format.
- `openpyxl`: For creating and manipulating Excel files.
- `matplotlib`: For generating visual summaries in PDF format.

## Configuration

- `NAGIOS_URL`: URL of Nagios JSON API.
- `USERNAME` and `PASSWORD`: Credentials for accessing Nagios API.
- `OUTPUT_XLSX`: File name for the Excel report.
- `OUTPUT_PDF`: File name for the PDF summary.

## Usage

1. Specify the `target_hosts` and `target_services` lists to define which hosts and services to monitor.
2. Run the script to fetch data from Nagios, generate the Excel report (`OUTPUT_XLSX`), and the PDF summary (`OUTPUT_PDF`).

## Script Explanation

- **Data Retrieval**: The script iterates over each host and service defined in `target_hosts` and `target_services`. It retrieves service status using parameters passed to the Nagios API (`statusjson.cgi`).
  
- **Excel Generation**: The script creates an Excel workbook (`Workbook()` from `openpyxl`), formats headers, and populates data retrieved from Nagios into the spreadsheet.

- **PDF Generation**: Using `matplotlib`, the script generates a PDF summary from the retrieved data, displaying host and service statuses in a tabular format.

## Example Output

- Excel file (`OUTPUT_XLSX`) stores detailed service status data across specified hosts.
- PDF file (`OUTPUT_PDF`) summarizes service statuses in a visually appealing format.

## Notes

- Ensure proper configuration of Nagios credentials (`USERNAME` and `PASSWORD`).
- Customize `target_hosts` and `target_services` according to your Nagios setup.

