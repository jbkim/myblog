---
title: Delta 3D Printer – Delta segmentation
author: openmicrolab
type: post
date: 2016-07-26T02:35:16+00:00
url: /delta-3d-printer/
categories:
  - 3D Printer
tags:
  - Delta 3D Printer
  - Delta segmentation

---
<img loading="lazy" class="alignnone wp-image-3713" src="http://res.cloudinary.com/openmicrolab/image/upload/v1469500370/err_zbacua.png" width="642" height="328" />

Notice the chart shows the worst possible cases on a line in XY plane from a tower base to the opposite side of the build area. The chart looks so funny because the maximum speeds are defined for the carriage movement (not for the platform movement). About 10 cm from the tower base the speed limiting tower is switched.  
The errors happen because firmware uses linear approximation for function **sqrt(R^2-x^2)**. The tower position errors will result in errors in cartesian X, Y, Z coordinates. The nearer you are to a tower the more the tower error will contribute to the cartesian Z error. The more far away you are from a tower the more the error will contribute to the cartesian X/Y error. You see the worst case is about 10 cm from tower, and this will result to about 0.05 mm Z-error and 0.025 mm X/Y error. Add stepper errors of about 0.006 mm, slack in the system, and dynamic errors because of acceleration <-> flexibility.