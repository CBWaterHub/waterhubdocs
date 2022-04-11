# Retrieving Data

We expect that there will eventually be a large number of datasets in the CBWH, which could make finding relevant data 
challenging. This section describes ways to carry out data searches, narrow results by filtering, download data, and 
query subsets of data.

## Searching for Data

There are several ways to search for data in the CBWH:

### 1. **Search By Map**
This is an entirely new feature, customized for the CBWH.  Click the Map Search link in the menu bar. This will bring up 
a map display with a legend.  The points on the map correspond to all datasets that have a latitude, longitude, and data 
type in their metadata.  One point is shown for each dataset, but a single dataset may contain multiple resources.  For 
example, a dataset for a water quality monitoring station at a fixed location might have a data table (resource) for each 
year of data collection.  The points that you see on the map are limited to those datasets that your user account can 
view.  For example, a private dataset in an organization that you are not a member of will not appear on the map.

As with most web maps, use the mouse to pan around and the mouse wheel to zoom in and out; there is also a zoom control 
at top right.  The map by default is zoomed to the Columbia River basin. There are buttons on the left to zoom to this 
extent, or to the full extent of all datasets.  The Layer Controller on the left shows the list of all data types in the 
datasets that you can view.  Use the check mark next to each data type to turn the layer on or off.  If a dataset has more 
than one data type, there will be a stack of points.  Use the layer controller to filter only the data types that you would 
like to see.

Clicking on a point on the map brings up a small pop-up with the dataset’s title and a link to the map. Clicking the 
link in the popup takes you to the dataset page.  If more than one dataset has the same latitude-longitude coordinate, 
the popup will contain links to all datasets at that coordinate.

![MapSearch](/assets/mapsearch.png)

### 2. **Browse Datasets**
Clicking the Datasets menu item takes you to the standard browser view of datasets.  You will see a list of datasets 
with a short description of each.  By default, these are sorted by Relevance, but if you have not entered any search 
keywords, the default arrangement is the same as Last Modified.  The Order By menu at the top-right has more options 
for sorting this list of datasets.  Datasets can be filtered on the left side of the page by Organizations, Groups, 
Tags, Formats or Licenses. Similar to the map search, you will only see those datasets that your user account has 
permission to view.

### 3. **Text Search**
The text box at the top of this view has a fairly good full-text search engine.  The indexing is based on significance 
of keywords in the document.  So, for example, if you search for “water quality,” results with that phrase in the title 
or near the beginning of the summary will appear highest in the list.

The following search operations may be used to perform more precise searches:

| Search Operator | Example    | Effect  |
| --------------- | ---------- |-------- |
| Minus (-)   |-columbia -estuary water quality  | Excludes Terms or phrases from the search. <br> In this example, the search returns datasets for the search water quality without the terms columbia or estuary in the returned results, which helps to exclude unwanted information. |
| Quotation Mark (" ")  | “water quality” | Makes an exact-match search of the quoted phrase. In this example, the search returns datasets that contain the whole quoted phrase water quality, which helps refine search results. |
| AND | Canal Flats AND water quality | Finds datasets related to multiple phrases. In this example, the search returns datasets that are related to both Canal flats and water quality, which helps narrow the search. |

*It is possible to combine the search operators to create more customized searches.*

### 4. Browse by Group
Categories are broad topics of interest used to group similar datasets and include Climate, Groundwater, Lakes, Snow, 
Streams, Wetlands, and Glacier. Some datasets are associated with more than one category.  Categories can be found at 
the bottom of the home page or under the Groups menu.

### 5. Browse by Organization
Click the Organization menu, then click on the organization of choice to see all public datasets belonging to the 
organization.  If you are a member of the organization, you will also see its private datasets.

## Filtering Search Results
After searching or browsing for datasets, you may wish to filter the list to further narrow the results. A search can be 
filtered by resource file format, group, organization, tag, or license, or any combination of these. Filters are found 
on the left side of the search page.

![filtering](/assets/filters.png){ align=right }

### Filtering by Format
Since resources can be provided in multiple formats, clicking on one format in the left panel will filter the results to 
show only datasets with resources distributed in that format. You may further filter the results by selecting additional 
formats; only datasets containing resources with both file formats selected will be returned.

### Filter by Group
Since datasets may be related to multiple collections/groups, clicking on one group will filter the results to show only 
datasets of that collection/category. However you may filter further to show those resources from the originally selected 
group that also fall into and one or more additional groups.

### Filter by Organization
Each dataset is linked to a single organization. While you can filter by organization, it is not possible to select a 
second organization filter, since datasets cannot belong to more than one organization.

### Filter by Tag
Each dataset can have multiple keyword tags associated with it. You can filter search results by tags; as many tags as 
desired can be used as filters.

### Filtering by Licence
Datasets in the CBWH may have a license associated with them. Clicking on one of the license types will filter the results 
to only show datasets with that license.  Datasets without a license type are tagged as “License Not Specified.”

### Combining Filters
Datasets in the SSDC may have a license associated with them. Clicking on one of the license types will filter the results 
to only show datasets with that license.  Datasets without a license type are tagged as “License Not Specified.”

To clear selected filters, click the X next to the filters you wish to remove, either at the top of the search results page, 
or in the filters panel on the left side of the page.

### Other Filtering Tips
If you want to use a filter that is not listed, click on the “Show More …” button at the bottom of each filter category.
If the desired filter term still does not appear, add the topic of interest into the search bar.  The filters most related 
to the search topic should now appear in the list of filters.

## Accessing Data
Once you have found a resource of interest, you can download it from the CBWH.

### Download from the Dataset Page
Every dataset has an ID, which is a URL-friendly version of the name in lowercase.  You will see the dataset ID at the end 
of its url, for example a URL ending with /dataset/flow-data is the “dataset page” for the dataset “Flow Data.”  The easiest 
way to download data is by clicking the green Download button for data of interest.  This allows you to download the data 
in its original format (usually Excel, for the CBWH).  On the Explore drop-down menu, there are additional options. The 
Download option on this menu is the same action as the green Download button.  Preview brings you to a page where you can 
preview the data table (if the data is tabular) or file (preview is supported for PDF and common image formats).

![Download from Dataset View](/assets/resource_download.png)

### Download from the Resource Page
To open the Resource page, click the link for the name of the data file, in this example “Large file test.” This brings 
you to the resource page for a data file. If the data is tabular, and has been successfully loaded to the CKAN Datastore, 
you will see a preview of the first few rows of the table.  If the data is a PDF or image file, there will be a preview 
below. You can also download data from this page.  To do so, simply click the Download button near the top-right, avoiding
the down arrow at the right edge of this button.  If the data is tabular, you also have additional download options in 
different format, which can be accessed by clicking the down arrow at the right side of the button.  However, downloading
data in its original format is recommended.

![Download from Resource Page](/assets/download_format.png)

### Programmatic Data Access and Query
For tabular data, it is possible to query a subset of the data, instead of downloading the entire file at once.  This can 
be useful, for example, if you want only data collected within a certain date range, or only values that exceed some threshold.
In the CBWH, supported Excel files are automatically loaded into the CKAN Datastore.  The datastore supports querying data 
using a SQL query.  SQL querying is beyond the scope of this document, but tutorials and example queries are widely available 
online.  For more information about the CKAN Datastore, see: https://docs.ckan.org/en/2.8/maintaining/datastore.html.

#### Example Query
On the resource page for tabular data, you will see a green Data API button at the top-right. Querying can be done from 
your web browser, or from R, Python, or any other programming language that supports HTTP requests and JSON.  Results from 
queries against tables in the datastore are provided in the JSON format (see: https://en.wikipedia.org/wiki/JSON).

On the resource page for tabular data, you will see a green Data API button at the top-right.  Click this to see examples 
of querying in action.  Querying can be done from your web browser, or from R, Python, or any other programming language 
that supports HTTP requests and JSON.  Results from queries against tables in the datastore are provided in the JSON format 
(see: https://en.wikipedia.org/wiki/JSON).

For example:
https://data.cbwaterhub.ca/dataset/lardeau-river-nhlar02/resource/dd2d8d49-6d61-42b7-b695-0c81c2cdfa52

In this example, the resource ID is: dd2d8d49-6d61-42b7-b695-0c81c2cdfa52. When performing an SQL query, the resource ID 
is the SQL table name. In the database behind CKAN, the table “c730d8a6-997c-436c-8c9e-795f91588c0e” contains all of the
data (rows and columns) that was pulled from the uploaded Excel file. Below is a simple line to get the first 5 rows:

https://data.cbwaterhub.ca/api/3/action/datastore_search?resource_id=dd2d8d49-6d61-42b7-b695-0c81c2cdfa52&limit=5

You can use this url for various applications using your preferred programming language like Python or Javascript.

For sql queries, the CBWH datastore URL is: https://data.cbwaterhub.ca/api/3/action/datastore_search_sql?sql=

In general, you can run any SQL query on any table in the datastore.  Note that table and column names must be double quoted. 

![CKAN API](/assets/ckanapi.png)





