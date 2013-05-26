Open Street Map Import Toolkit
==================

Open Street Map Importing and mechanical edits toolkit. 

There is a lot of software spread here and there for doing mechanical edits and imports of Open Street Map data. The goal of this repository is to collect the best scripts written by myself and others to present a complete toolkit.

Please read and follow the import guidelines here, here, and here!

- http://wiki.openstreetmap.org/wiki/Import/Guidelines
- http://wiki.openstreetmap.org/wiki/Mechanical_Edit_Policy
- http://wiki.openstreetmap.org/wiki/Automated_Edits_code_of_conduct

Uploading
------------------

 - upload/osm2osc.py - Many of the utilities that convert external data to OSM write out an .osm file. However, only .osc files can be uploaded. This simply utility converts .osm to .osc. This is basically unmodified from the version on OSM SVN.

 - upload/osmsplit.py - Breaks up a large .osc file into smaller files. The OSM API has a 50,000 element limit for a single change set. In practice, the change sets should be kept much smaller, around 10,000 elements. Therefor, before uploading, large .osc files need to be broken up. The generated .osc files are self contained without cross dependencies. They can be uploaded in any order. If your .osc files are self contained, it is trivial to recover from an upload error.

 - upload/osmupload.py - Uploads a set of .osc files into a server that supports the OSM API. This is a heavily modified version of the upload.py script that is hosted on the OSM SVN server. It keeps a log of the uploads, supports testing uploads to the development server, does not use "chunks", so that each .osc file upload is atomic, allows comment and source tags on the change set to be pulled from files, will not double upload a file, and will try hard to always close out a change set if an error occurs. The log holds the change set ids, so it is possible to review an already completed upload.



