# Core CKAN Concepts

## Datasets and Resources
This section describes the way in which data and users are organized and displayed in CKAN.  The core concepts or “structures” 
used to organize data are Datasets, Resources, Organizations, and Groups. We also discuss Metadata, which is additional 
information about each dataset and resource.  These are discussed in the following sections. 1 Datasets and Resources In 
CKAN, a dataset is a collection of related data and metadata.  Each dataset may contain one or more resources, which are 
either files uploaded to CKAN, or links to data stored elsewhere.  A resource could be a PDF or Word report, a map, a 
data table, or something else.  Both datasets and resources have their own metadata.  For the CBWH site, the majority of
resources will be Excel files containing tables of various kinds of water monitoring data.  Typically, one monitoring 
station would correspond to one dataset in CKAN.  All data tables and reports pertaining to that station would be added 
as resources to its dataset. 

A dataset contains two things: 

1. Information or “metadata” about the data. For example, the title and publisher, date, what formats it is available in,
   what license it is released under, and so on.  CBWH uses a custom metadata schema, with metadata fields specific to 
   water monitoring, in addition to the standard CKAN metadata fields. 

2. A number of “resources”, which hold the data itself. Resources also have their own resource-level metadata, which is 
   independent from the dataset-level metadata.

![Datasets](/assets/dataset_view.png)

## Organizations
Each dataset is owned by an organization, which is a collection of users who belong to a common group.  This could be users 
from a First Nation, users from a specific government department, and so on.  The CBWH is expected to eventually have dozens 
of organizations. Each organization can have its own workflow and authorizations, allowing it to manage its own publishing 
process. A large organization can break up its data by department, allowing each department to be a separate organization 
within the CBWH.

Each organization can have a user assigned as an administrator. An organization’s administrator can add individual users 
to it, with different roles depending on the level of authorization needed.  Each dataset in CKAN belongs to only one organization.

A user in an organization with Editor permissions can create a dataset owned by that organization. By default, this dataset 
is initially private, and visible only to other users in the same organization.  Only logged-in users who are members of 
the dataset’s organization can see private datasets.  When it is ready for sharing outside the organization, it can be 
made public at the click of a button.  A Public dataset is visible to all users of the site.

### User Permission Levels in Organizations

Users added to an organization can have one of three roles:  Admin, Editor, or Member.

- *Admin*: 
  
    can view the organization’s private datasets, and all public datasets, can add, delete, and edit datasets, and 
  can add, edit, or delete members or organization.
  
  
- *Editor*:
    
    can view the organization’s private datasets, and all public datasets, and: create and delete datasets within the organization.

  
- *Member*: 

    can view the organization’s private datasets, and all public datasets

## Groups
Groups in CKAN does not refer to user groups.  A “group” in CKAN is really more of a data theme—it is typically used to 
group thematically-related datasets. Whenever you see Groups, think of Themes or Categories.  Groups are meant for the 
community of site users to collect related datasets together into themes such as Water Quality.

The Groups used by the CBWH will reflect the type of waterbody that a dataset is related to. The current groups are Climate, 
Groundwater, Lakes, Snow, Streams, Wetlands, and Glaciers. These groups are intended to have a 1:1 correspondence to the 
Data Type field in the custom metadata, although this relationship is not set in stone.


Note that a dataset can belong to more than one group, unlike organizations.

## Metadata
In CKAN, datasets have a default metadata schema, which is a set of fields with information describing the dataset. 
These include dataset title, summary, maintainer email, parent organization, and keywords, among others. 
The CBWH has been customized with additional metadata fields related to water monitoring data: Latitude, Longitude, Data 
Grade, Data Type, Data Collector, Start and End dates, and others.  The custom metadata schema is currently fixed, but it 
can be changed as needed. The list of keywords is restricted to a controlled vocabulary.  The Data Type field is categorical, 
and has a set of data types determined by Living Lakes to best meet the needs of the organizations that will be uploading data. 
The list of data types corresponds to the Groups in CKAN and also the available layers in the Map Search interface.

