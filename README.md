# Automation Sheets: streamlined extraction and consolidation of parliamentary data from Google Drive to BigQuery
Automation Sheets is a data pipeline designed to automate the extraction, consolidation, and export of parliamentary information—such as bulletins and agendas—stored in Google Sheets across multiple Google Drive folders. The project transforms a fragmented collection of files into a centralized, query-ready database in BigQuery, enabling dynamic visualization and reporting through Looker Studio. It is specifically designed to support Public Affairs teams in monitoring institutional activity more efficiently.

### Project Objectives
1. **Automated data retrieval**
The core function is to automate the discovery and extraction of relevant data from Google Sheets that have been recently modified or added to specific Drive folders. This ensures that only the most current and relevant information is processed.

2. **Data consolidation**
Extracted data is appended to a structured master sheet that serves as a centralized database. This unified dataset allows for easier querying, reporting, and cross-referencing of initiatives across categories (e.g., national, regional, legislative agendas).

3. **Scheduled execution**
To keep the database consistently up to date, the pipeline is designed to be run on a scheduled, recurring basis (e.g., weekly) via time-based triggers, eliminating the need for manual execution.

### Implementation steps
I. **Google Drive and Colab integration**
The project is executed in Google Colab, using the gspread library to interface with Google Sheets. It mounts Google Drive to access the relevant folders and reads the content of each file using the Google Sheets API.

II. **Library imports and setup**
Libraries, such as `pandas` for data manipulation and `oauth2client` for authentication, are imported. The user must set up a Google Cloud project and authenticate access to the Drive files using a JSON credentials file.


III. **Folder structure and iteration logic**
The script loops through multiple predefined folders in Google Drive, each corresponding to a source type, such as:

- Parliamentary bulletins

- Regional or autonomous bulletins

- Parliamentary agendas

During iteration, the script checks each file’s last modified date and filters in only those updated after a predefined threshold date.

IV. **Data extraction and appending**
For each eligible file, relevant data is extracted and processed. Depending on the folder or source type, the content is appended to the appropriate tab or section within the unified master sheet. This ensures consistent data structure and categorization.

V. **Export to BigQuery**
After consolidation, the master dataset is exported to a predefined BigQuery table. This step transforms the sheet-based data into a robust, cloud-based database, optimized for querying and integration with BI tools.

VI. **Dashboard integration**
The final output is designed to feed into a Looker Studio dashboard, enabling real-time monitoring of legislative activity and generating insights for Public Affairs and institutional stakeholders.

-------------
### Value for Public Affairs
This solution significantly reduces the manual workload required to monitor and track institutional documents. It ensures that teams have access to the most up-to-date information, structured in a consistent and queryable format, ready for analysis and visualization. It enhances the strategic capacity of Public Affairs departments by providing timely intelligence in an automated, scalable manner.
