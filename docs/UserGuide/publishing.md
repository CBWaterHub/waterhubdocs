# Publishing Data
This section describes how to publish your data on the CBWH.  Note that you can only publish data if your account has 
Editor or higher permissions level.

## Preparing your Data
The CBWH includes a custom extension that automatically loads data from uploaded Excel and csv files, with field type 
detection, to an internal database within CKAN, called the Datastore.  The Datastore allows users to preview the contents 
of tabular data, extract a subset of that data using a query, and download data in other structured formats such as csv or 
JSON.  For more information on the CKAN Datastore, see: https://docs.ckan.org/en/2.8/maintaining/datastore.html.

## Structuring Tabular Data
The Datastore loading extension handles data in Excel and csv format, and is designed to be as flexible as possible.
There is no requirement for column names or types to match any pre-existing schema for water management data.
However, there are a number of restrictions that apply to the format and structure of tabular data.  It is impossible for 
the plugin to bypass these restrictions, so any table that does not match the following list of restrictions will not be 
loaded to the CKAN Datastore.  If this happens, the uploaded file will still be published in CKAN and be downloadable by 
authorized users, but the Datastore feature specifically will not be enabled for that table.  Please review the following 
restrictions prior to publishing your data.

- The excel or csv file must have a contiguous rectangular block of data (rows and columns) with a header row.  There must 
  be only one header row. There must not be a gap between the header row and the first row of data, even if this improves 
  human readability.  Multiple header rows embedded in the data table will cause all columns to be interpreted as text columns.
  Multiple blocks of data separated by gaps of blank cells will likely cause data loading to fail. Before loading an Excel 
  file, ensure that all hidden columns and rows are visible, and check for any issues with the structure of the table.
  
  
- Each column must contain only a single data type (such as integer, decimal number, text).  The data types must be simple, 
  and not composite.  For example, two columns Latitude and Longitude, each containing decimal numbers is OK. By contrast, 
  a single column containing a latitude-longitude coordinate will not be interpreted correctly.  Columns may contain null values, 
  with the following caveats: if using Excel, a null value is represented as an empty cell with no data at all, not a space character, zero, 
  underscore, a formula that evaluates to a blank cell such as =””, or any other data.  If using csv, a null value is 
  represented as a pair of commas with no space or quote marks between them: ,,  Any other representation of null in a csv 
  is likely to be interpreted as a text object, and cause the entire column to become a text field.
  
  
- Excel files must not have any graphs, pictures, comments, formulas, or other objects embedded in the data table.  Avoid 
  using merged cells anywhere in the file.
  
  
- The header row does not have to be on the first row, but there must be a header row somewhere in the file. You will 
  have to provide the Excel/csv row number of the header row when uploading your file; it cannot be reliably auto-detected, 
  and cases where the header row is not on the first row are sufficiently common that a default of assuming that the first 
  row is the header row is not sensible.  The header row number starts from 1 on the first row; it is not zero-indexed.  If you 
  leave the header row field blank, or enter an invalid row number, the file will be published as a resource in CKAN, but it 
  will not be loaded to the CKAN Datastore.
  

- The header row must contain only SQL-compatible column names, meaning only alphanumeric characters and underscores 
  (no spaces, brackets, commas, hyphens, or other special characters), and less than 63 characters long.  Internally, all
  column names will be converted to lowercase before loading the table to the Datastore. Note that this only applies to 
  the copy of the table that is loaded to the Datastore; the original column names in your csv or Excel file will remain as they 
  were when you uploaded the file.
  

- In CKAN, a resource can only have one table loaded to the Datastore.  If the Excel file has multiple spreadsheets, 
  only the first one will be imported in the Datastore.  However, the original Excel file will not be modified; if you 
  have multiple sheets in the uploaded file, they will remain unchanged when users download the original file.  If you 
  have an Excel file with multiple sheets that you want to have loaded in the Datastore, please copy each sheet to a new 
  Excel file, and create a new resource for each of these files.
  

## Creating a Dataset
On the CBWH site, on the Dataset page, click Add Dataset. If you do not see the Add Dataset button, your account does 
not have the access level required to create datasets.


This is a two-step process. In the first step, you will see a series of metadata fields, including basic fields like 
Title and Summary, along with others specific to water monitoring.  If you are creating a dataset for which some of these 
fields do not apply, simply leave them blank.  The metadata schema is designed to be inclusive of all possible data types 
that might be published by Living Lakes, so it is likely that some of the fields will be blank for every dataset you create.

### Upload and Wait for Publication
On the next page, either click Upload to upload a data file, or click Link to add a link to a dataset that is hosted on 
an external website.  If uploading a tabular data file, please be sure to enter the header row number.  Also be sure to 
correctly enter the format. The format can be detected from the file extension, but this is not always reliable.

If you upload an Excel or csv file with a header row defined, the Datastore loading extension will be triggered in the 
background, and will attempt to load your data to the Datastore.  While this is happening, the site will redirect you to 
the resource page for the file you just uploaded.  It is likely to take anywhere from a few seconds to many minutes before 
your data becomes available in the Datastore.  One of the metadata fields in the resource page shows the status of data 
loading.  This field will contain one of the following: an in-progress message, a completed message with the number of 
rows loaded, or an error message.  Once the process is complete, refresh the page to see your table in the datastore, 
which shows roughly the first 25 rows in a table embedded at the top of the resource page in CKAN.  If instead of the data 
table preview, you see the message “There are no views created for this resource yet” it means that the Datastore load failed 
for this table.  Scroll down to the Loading Status section below and there may be an error or status message.  If this still 
does not clarify the reason that data loading failed, please contact a site administrator.

### File Size Limit

There is an upload size limit of approximately 900MB per file.  If you need to upload files larger than this, please 
contact a site administrator to arrange an alternative data workflow. Please remember to be mindful with zip files that 
may cross the 900MB size, and contact us with any questions.  Generally, data in Excel will consume less space than the 
same data in csv format.

