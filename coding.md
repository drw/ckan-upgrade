As for the geocode extension it checks every 15 minutes for resources that have the field "Geocode Data" set to "Geocode" and the field "Geocoder" set to "Mapzen".

Then it geocodes the first 50000 rows of a resources based on a column labeled "streetAddress".0

The streetAddress column should contain complete addresses (eg: 1230 FEDERAL ST, PITTSBURGH, PA 15212).

The extension then creates a new resource with two new columns latitude and longitude.
