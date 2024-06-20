# expa-analytics-appscript-boilerplate
A boilerplate :EXPA Performance Analytics Data to Google Sheets using AppScripts

This is a boilerplate script is designed to fetch and analyze application data from the AIESEC API, process the data, and write the results to a Google Sheets document. The script is intended for users who need to automate data collection and reporting for different entities within AIESEC.

## What is a Boilerplate Project?

A boilerplate project is a starting template that contains the essential components and structure needed to begin a specific type of project. It provides a standardized way to set up the basic configuration and code required for the project, allowing developers to focus on the unique aspects of their application without having to build common functionalities from scratch. This Script is a boilerplate project for automating data collection and reporting from the AIESEC Analytics API

## Prerequisites

- Google account with access to Google Sheets
- Google Apps Script project setup
- AIESEC API access token

## Files Included

- `main.gs`: The main Google Apps Script file
- `README.md`: Documentation on how to use the script

## Setup Instructions

1. **Create a Google Sheet:**
   - Open Google Sheets and create a new spreadsheet.
   - Note the name of the sheet (you will need to use this name in the script).

2. **Set Up Google Apps Script:**
   - In your Google Sheet, go to `Extensions > Apps Script`.
   - Delete any existing code in the script editor.
   - Copy and paste the code from `code.gs` into the script editor.

3. **Configure the Script:**
   - Replace `'YOUR TOKEN HERE'` with your actual AIESEC API access token.
   - Update the `startDate` and `endDate` variables if needed.
   - Update the `sheetName` variable to match the name of your Google Sheet.

4. **Authorize the Script:**
   - Click the disk icon to save the script.
   - Click the play button (triangle icon) to run the script.
   - Follow the prompts to authorize the script to access your Google Sheets.

5. **Run the Script:**
   - After authorization, click the play button again to run the script.
   - The script will fetch data from the AIESEC API and write it to your Google Sheet.

## Explanation of the Code

### Constants and Configuration

- `baseUrl` and `accessToken`: Set the base URL for the AIESEC API and the access token for authentication.
- `entitiesList`: An array of objects representing the entities to fetch data for.
- `regexList`: An array of objects representing the patterns to match specific data types (e.g., oGV, oGTa, iGV).
- `startDate`, `endDate`, `sheetName`: Configuration for the date range and Google Sheet name.
- `keysList` and `headersList`: Define the keys for exchange stages and the headers for the Google Sheet.

### Helper Functions

- `fetchDataByLC(startDate, endDate, lcId)`: Fetch data from the API for a specific entity within the date range.
- `extractData(apiOutput)`: Extract relevant data from the API response using regex patterns.
- `prepareSheet()`: Prepare the Google Sheet by setting up headers.
- `writeRowToSheet(rowIndex, rowData)`: Write a row of data to the Google Sheet.

### Main Process

- `startProcess()`: The main function that orchestrates the entire process.
  - Prepares the sheet.
  - Fetches data for each entity.
  - Extracts and processes the data.
  - Writes the data to the Google Sheet.

## Example Output

The script writes the following columns to the Google Sheet for each entity and data type:
- Entity
- Function
- Matched
- Applied
- Approved
- Realized
- Finished
- Completed

Each row corresponds to a specific entity and data type combination, with the respective counts for each exchange stage.

## Troubleshooting

- Ensure the sheet name matches the `sheetName` variable.
- Ensure the access token is valid and not expired.
- Check the API endpoint and data structure if there are changes in the AIESEC API.

## Conclusion

This script automates the process of fetching and analyzing application data from the AIESEC API and writing it to a Google Sheet. It is designed to be easily configurable and extendable for various reporting needs.
