# Publishing of KML Files 

Google Maps [caches](https://developers.google.com/maps/documentation/javascript/kmllayer?csw=1#performance) KMLLayer files heavily for performance reasons. To reliably reflect changes that happened to KMZ files or styles, without waiting unknown amount of time for the caches to clear, is to create a new version folder on the hosting site and reference the new KMLLayers via the new version URLs.

The following steps outline the process of creating and packaging this folder to publish as a new version:

1. Extract original *.kmz files
2. Edit doc.kml from inside the original kmz file and update for styling as per info in StylesDoc.kml
3. Compress the updated doc.kml back into its kmz file (no sub-folders)
4. Create a new version's folder on the hosting site (e.g. YYYYMMDD)
5. Upload *all* files from this folder to the new version folder on the site
6. If StylesDoc.kml was to change, the previous two steps are needed even if it is the only file to change
7. Update URL references to KML layers in the solution (i.e. ControlAreaOverlay table) for new version, for example:
   + `http://www.hcms.mto.gov.on.ca/Content/kmz/20190920/Buf_General.kmz`
   + `http://www.hcms.mto.gov.on.ca/Content/kmz/20190920/Buf_Signs.kmz`
   + `http://www.hcms.mto.gov.on.ca/Content/kmz/20190920/PHM_Highway.kmz`

