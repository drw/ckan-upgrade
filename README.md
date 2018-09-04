# ckan-upgrade

Detailed documentation:
https://docs.google.com/document/d/19NW1-0JQ8z8id2a4L1T9xdKXU9_YLyuXX4qooOY_NVs/edit


1) New spreadsheet view of data
The old spreadsheet view for uploaded tabular data has been replaced with the new DataTables view, as you can see for the 311 Data here:

http://wprdc.ogopendata.com/dataset/311-data

The old spreadsheet view had many annoying features, including truncation of column names and field values and a tendency to re-sort the table when you didn't want it to. 

The new DataTables view eliminates these problems and adds a neat Hide/Unhide Columns button. This allows a user who is viewing a table with many columns to temporarily hide uninteresting ones, making it easier to pare down a wide table to a few columns of interest for quick browsing.

Caveat: Most of the datasets don't have spreadsheet views yet, but that will be fixed when we do the final data migration.


2) New data uploader

The new data upload process for tabular data a) is faster, b) is less prone to failure*, c) makes it easy to set field types, which speeds up any usage of that data, and d) results in faster downloads (no more long waits to generate CSV files for the biggest tables).

* When you as a publisher upload a tabular data file (either CSV or Excel) through the web interface, the old CKAN tries to guess the field types. If it guesses wrong, the upload sometimes breaks in the middle. Our new CKAN instance will let you directly set the data types through the web interface; previously the only way to do that was to write an ETL job.


3) Integrated data-dictionary view
Below each DataTable view, you will see a view of the integrated data dictionary for the resource. This shows the name of each field, the type of data that CKAN has it stored as, and currently two other parameters: a human-readable label for the field and a catch-all description.

Here’s an example of what the integrated data dictionary might look like for a particular resource:

http://wprdc.ogopendata.com/dataset/allegheny-county-jail-daily-census/resource/70762439-ac19-424b-8a4b-dbe1b5d2c8ba


It's our hope that these changes will improve the experience of using the data portal and make it easier to use the data.

I've written up more detailed documentation on how uploading tabular data is different under the new CKAN, how the integrated data dictionary works, and our tentative thoughts on migrating to using integrated data dictionaries:
https://docs.google.com/document/d/19NW1-0JQ8z8id2a4L1T9xdKXU9_YLyuXX4qooOY_NVs/

The new replacement for data.wprdc.org is currently running at this URL:
http://wprdc.ogopendata.com

---

# Other advantages of the CKAN upgrade

We will be getting a geospatially-aware DataStore, that will be able to do geographic searches faster; we'll still need to do some work on individual datasets before they have this capability. We'll have an improved version of the harvester (which regularly grabs lots of GIS files from city and county ArcGIS servers), which should be more reliable.]
