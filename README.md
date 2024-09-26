# automation_sheets
The project automates data extraction from Google Sheets in various Drive folders. It iterates through folders containing parliamentary bulletins and agendas, retrieving files modified after a specified date. The data is then appended to a unified database sheet. 

The project focuses on automating the extraction and consolidation of data from Google Sheets stored in multiple folders on Google Drive. Here’s a detailed breakdown of the components and steps involved:

### Objectives
1. **Automated data retrieval**: the primary goal is to automate the identification and extraction of specific data from Google Sheets. The focus is on files that have been modified or uploaded after a designated date, ensuring that only the most recent and relevant information is processed.

2. **Data consolidation**: after extraction, the project aims to append this data into a centralized database sheet. This unification of data allows for easier analysis and reporting, as all relevant information is compiled in one location.

3. **Scheduled automation**: to maintain up-to-date data, the project includes the implementation of a weekly trigger. This ensures that the data extraction and consolidation process runs automatically at specified intervals without manual intervention.

### Implementation steps
1. **Google drive integration**: the script is designed to work within Google Colab, utilizing the `gspread` library to interact with Google Sheets. Initially, it mounts the Google Drive to access the required folders and files.

2. **Library imports and setup**: essential libraries, such as `pandas` for data manipulation and `oauth2client` for authentication, are imported. The user must set up a Google Cloud project and authenticate access to the Drive files using a JSON credentials file.

3. **Folder iteration**: the script iterates through specified folders, which contain various types of documents, including:
   - Parliamentary bulletins
   - Autonomous bulletins
   - Parliamentary agendas

   During this iteration, the script checks each file’s last modified date. If a file has been updated after the specified cutoff date, it is marked for extraction.

4. **Data extraction and appending**: for each identified file, the relevant data is extracted and then appended to the appropriate section of the unified database sheet. This ensures that data from similar categories are grouped together, facilitating better organization and accessibility.

5. **Trigger setup**: the final component involves establishing a trigger that will automatically execute the script on a weekly basis. This eliminates the need for manual runs, ensuring that the database is continuously updated with the latest information.

### Conclusion
This project leverages automation to streamline the data extraction and consolidation process from Google Sheets. By focusing on modified files and implementing a systematic approach to data handling, it enhances efficiency and ensures that stakeholders have access to the most current data for analysis and decision-making.
