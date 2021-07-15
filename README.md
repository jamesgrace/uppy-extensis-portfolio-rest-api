# uppy-extensis-portfolio-rest-api
[Uppy JavaScript uploader](https://github.com/transloadit/uppy) integrated with the Portfolio REST API's default File Upload operation ( `defaultUpload` ).

#### Requirements :
* Extensis Portfolio version 3.6.3 ( _or greater_ ) licensed for the Portfolio API with Mobile Uploading enabled.
* Web Server ( _e.g. Microsoft IIS , Apache , etc._ ) with direct connectivity to the Extensis Portfolio instance.

#### Optional Requirements :
* Extensis Portfolio version 3.6.3 ( _or greater_ ) NetPublish Website published via the "Mobile Uploads" Catalog's "All Assets" Gallery.


## Portfolio Instance > Installation Procedure :

#### 1. PORTFOLIO SERVER VERSION
* Via the Portfolio Administration ( _:8091_ ) Web interface , verify the current version of your Portfolio instance and that the Portfolio API module has been activated.
  * Although the provided example may work on earlier Portfolio versions , Portfolio version 3.6.3 ( _or greater_ ) is recommended.

#### 2. MOBILE UPLOADING
* Via the Portfolio Administration ( _:8091_ ) Web interface , select "Global Settings" > "Mobile" and verify that "Enable Mobile Uploading" has been selected and that "Save mobile uploads to this folder" has been configured for a location with ample drive space.
* Via the Portfolio Administration ( _:8091_ ) Web interface , select "Catalogs" and verify that the "Mobile Uploads" Catalog is listed.
  * Note that it is not necessary for indivudal Users to speifically be granted membership to the "Mobile Uploads" Catalog as Uploading via defaultUpload is permitted to all existing Users regardless of Catalog membership.

#### 3. API TOKEN
* Via the Portfolio Administration ( _:8091_ ) Web interface , select Users and either take note of an existing API Token or create a new API Token.

#### 4. MOBILE UPLOAD TESTING
* Using the Extensis Portfolio Flow app ( [Android](http://play.google.com/store/apps/details?id=com.extensis.portfolio.uploader) / [iOS](https://itunes.apple.com/us/app/portfolio-flow/id731629362?mt=8) ) , verify that files are uploading properly to the target Portfolio instance's Mobile Uploads Catalog.

#### 5. MOBILE UPLOADS NETPUBLISH WEBSITE
* Using the Portfolio Web Client select the "Mobile Uploads" Catalog > "All Assets" Gallery and then Publish a NetPublish Website.
  * Recommended NetPublish Site Builder choices :
    * Security > "No Login Required" selected.
    * Details > Set Metadata Fields > "Filename" , "IPTC - Title" , "IPTC - Instructions" , "IPTC - Event" , "Keywords" , and "Description" selected.

## Web Server > Installation Procedure :

#### 1. WEBSITE FILES
* Copy the `index.html` , `portfolio4.css` , and `favicon.ico` files over to an appropriate sub-folder ( _typicaly located directly beneath the Web Server's document "root" path_ ).

#### 2. WEBSITE FILE MAINTENANCE
* The HTML and CSS files should be viewed , edited , and maintained using a standard programmer's text editor :
  * Windows :point_right: Notepad++ ( _https://notepad-plus-plus.org_ ).
  * Macintosh :point_right: Atom ( _https://atom.io/_ ).

#### 3. REQUIRED WEBSITE FILE CONFIGURATION
* **`index.html`** : verify that the `PORTFOLIO_SERVER` ( _e.g. `https://portfolio.example.com:9443`_ ) and `API_TOKEN` ( _e.g. `TOKEN-1abc2def-...`_ ) global variables are properly defined.

#### 4. OPTIONAL WEBSITE FILE CONFIGURATION
* **`index.html`** : verify that the `RESULTS_NETPUBLISH` global variable value matches the Mobile Uploads NetPublish Website URL ( _e.g. `https://portfolio.example.com:8095/mobile_uploads`_ ).
  * Note that this will allows uploaders to view transfers ( _post-upload_ ).
* **`portfolio4.css`** : verify that the various CSS color value selections align with approved corporate branding standards and modify if necessary.
* **`favicon.ico`** : verify that the included favicon aligns with approved corporate branding standards and replace if necessary.


