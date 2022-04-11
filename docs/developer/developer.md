# Water Hub Structure and Developing

## Water Hub Software Architecture

The Water Hub is a CKAN 2.9.5 instance that has various plugins for customization and various functionality.

The current styling and metadata schema can be found in the ckanext-waterhub repository in Github. Another custom plugin
created specifically for the CBWH is the ckanext-mapsearch, which provides the Map Search interface in the front-end.

Other plugins currently being used by the Water Hub:
- ckanext-datastore
- ckanext-scheming
- ckanext-geoview
- ckanext-pdfview
- ckanext-hierarchy

The Water Hub currently uses NGINX and UWSGI as a proxy and webserver. The Water Hub uses Solr as a search engine, and is 
hosted in an Ubuntu 20.04 LTS Virtual Machine with 30GB of disk space and 8GB of RAM

# Install the Water Hub for Development
The CBWH can be installed as an extention to a CKAN instance. Find below a general guide for installing a development CBWH.

1. Install Core CKAN following the [offical documentation](http://docs.ckan.org/en/2.9/maintaining/installing/install-from-source.html)
   

2. Install the necessary plugins:
    - [datastore](http://docs.ckan.org/en/2.9/maintaining/datastore.html)
    - [ckanext-scheming](https://github.com/ckan/ckanext-scheming)
    - [ckanext-geoview](https://github.com/ckan/ckanext-geoview)
    - [ckanext-pdfview](https://github.com/ckan/ckanext-pdfview)
    - [ckanext-hierarchy](https://github.com/ckan/ckanext-hierarchy)
    - [ckanext-CBWaterHub](https://github.com/CBWaterHub/ckanext-CBWaterHub)
    - [ckanext-mapsearch](https://github.com/CBWaterHub/ckanext-mapsearch)
    

3. Add the plugins to the ckan.ini file


4. Start ckan inside the virtual environment with the following code:
   
    - `cd /usr/lib/ckan/default/src/ckan`
   
    - `ckan -c /etc/ckan/default/ckan.ini run`
    
    -  ***NOTE***: *By default, CKAN will start on localhost port 5000, so make sure that if you don't want to expose that port to the internet,
    you have a firewall enabled.*

5. If CKAN starts normally and without errors, you can use this guide on [Deploying a source install](http://docs.ckan.org/en/2.9/maintaining/installing/deployment.html) 
   to open your development Water Hub to the internet for sharing.
   

# Contributing to the CBWH
The Water Hub team is currently developing a system for the online community to contribute to the Water Hub in the forms of
data, code, development, or any other help. To do so, please reach out to the [Water Hub Team](mailto:cbwaterhub@livinglakescanada.ca)
