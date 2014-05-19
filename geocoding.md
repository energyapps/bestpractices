## Batch Geocoding for Use in Tilemill

If you are creating a map with [Tilemill](www.mapbox.com/tilemill), or you just need a KML of a set of points, you can use [batchgeo.com](http://batchgeo.com/) to create a KML.

If you want transform that KML into a SHP, geojson, csv, etc, I'd recommend using [QGIS](http://www.qgis.org/en/site/).

### What you need

To begin, you need a csv or excel document with an address for each record. Not all address fields are required, but the more specific you can be with the address the more accurate the geocoding will be.

For instance:

 * Pennsylvania - Bad, will get you the center point of the state 
 * Lackawanna County, PA - Okay, will get you the center point of the county
 * Scranton, PA - Better, will get you the center point of Scranton, PA
 * 599 Costello Ct, Scranton, PA 18510 - Best, will get you precise location, if your address is correct

Batchgeo.com has provided a [sample template](http://batchgeo.com/excel_example.xls). You can add your own columns as well, or get rid of ones you don't need (email, URL, etc.)

### Geocoding

Once you have a spreadsheet with your records and addresses, you simply cut and paste your data into [batchgeo.com](http://batchgeo.com). Make sure to include a header row. (To you nerds, out there, your spreadsheet will show up as a tab-seperated value on the batchgeo, once you paste it.) 

Then click "Validate and Set Options"

Now you have to match each column to their respective item, for the addresses to search correctly.

Note that you can either have a single column with the full address (mapped to location/address), or you can have individual columns for address, city, state, zip, etc, mapped to their respective options.

Click "Make Map".

If any of the points are noticeably not in the correct location, you can drag the points to their correct location.

Select "Unlisted", put your email address in, and hit "Save Map"

On the resulting page, scroll to the very bottom, and select "Download Google Earth KML"

In Tilemill, you will be able to add the resulting KML file and style it accordingly.