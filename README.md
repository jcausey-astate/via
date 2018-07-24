# \[My fork of the\] VGG Image Annotator

VGG Image Annotator (VIA) is an image annotation tool that can be used to define 
regions in an image and create textual descriptions of those regions. VIA is an 
open source project developed at the [Visual Geometry Group](http://www.robots.ox.ac.uk/~vgg/) 
and released under the BSD-2 clause license. This work is supported by EPSRC programme grant 
Seebibyte: Visual Search for the Era of Big Data ([EP/M013774/1](http://www.seebibyte.org/index.html)).
Visit the [VGG software page](http://www.robots.ox.ac.uk/~vgg/software/via/) for more details.

## Differences in this Fork:
This fork mainly adds the *width* and *height* of the original image to the output metadata in
both JSON and CSV format.  The CSV header is thus changed from the original version:

    filename,file_size,file_attributes,region_count,region_id,region_shape_attributes,region_attributes

to this version:

    filename,file_size,width,height,file_attributes,region_count,region_id,region_shape_attributes,region_attributes

and the JSON annotation format has the additional fields `width` and `height`
associated with every image file.

**Caveat**

Because the width and height cannot be obtained until the image is rendered into 
the DOM, these fields may be set to the string "NA" for any image that has not 
been annotated yet in the viewer.  Thus, the valid values for `width` and `height` are
integers or "NA".

## Features:
  * based solely on HTML, CSS and Javascript (no external javascript libraries)
  * can be used off-line (full application in a single html file of size &lt; 400KB)
  * requires nothing more than a modern web browser (tested on Firefox, Chrome and Safari)
  * supported region shapes: rectangle, circle, ellipse, polygon and point
  * import/export of region data in csv and json file format


## Downloads
See http://www.robots.ox.ac.uk/~vgg/software/via/

## Docs
 * User Guide : this can be accessed from the menubar "Help -> Getting Started"
 * [VIA Software page @ VGG](http://www.robots.ox.ac.uk/~vgg/software/via/)
 * [VIA Wikipedia page](https://en.wikipedia.org/wiki/VGG_Image_Annotator)

## Developer Resources
For development, [via.js](https://gitlab.com/vgg/via/blob/develop/via.js) 
contains the Javascript source code and 
[index.html](https://gitlab.com/vgg/via/blob/develop/index.html) contains the 
HTML and CSS. The shell script [scripts/pack_via.sh](scripts/pack_via.sh) 
packs the VIA application into a single and standalone application file 
[via.html](https://gitlab.com/vgg/via/blob/develop/via.html) containing the 
Javascript, HTML and CSS.

 * Source code: [VGG Image Annotator @ develop branch](https://gitlab.com/vgg/via/blob/develop)
 * [Source code documentation](https://gitlab.com/vgg/via/blob/develop/CodeDoc.md)
 * Unit Tests : see files inside `tests/` folder

The [Quality Assessment](https://gitlab.com/vgg/via/blob/develop/QualityAssessment.md) 
page describes the guidelines to ensure the quality of VIA application, source 
code and its documentation.

Software bug reports and feature requests should be 
[submitted here](https://gitlab.com/vgg/via/issues/new) (requires gitlab account).
For all other queries, please contact [Abhishek Dutta](mailto:adutta@robots.ox.ac.uk).

## License
VIA is an open source project released under the 
[BSD-2 clause license](https://gitlab.com/vgg/via/blob/master/LICENSE).

## Author
[Abhishek Dutta](mailto:adutta@robots.ox.ac.uk)  
Aug. 31, 2016

Changes in this fork by:
[Jason L Causey](https://jasoncausey.net)
July 24, 2018