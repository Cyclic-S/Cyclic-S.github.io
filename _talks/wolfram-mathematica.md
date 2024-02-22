---
layout: archive
title: "Mathematica"
permalink: /talks/Mathematica
date: 2024-02-21
---

## Local Time in `city` by Mathematica.

<pre>
cityTime = 
  APIFunction[{"city" -> "City"}, ClockGauge[LocalTime[#city]] &, 
   "HTML"];
EmbedCode[CloudDeploy[cityTime]]
</pre>
<iframe src="https://www.wolframcloud.com/obj/intmath/cityTime" width="800" height="600"></iframe>

## Local GeoGraphics in `city` by Mathematica.

<pre>
cityL = APIFunction[{"city" -> "City"}, GeoGraphics[#city] &, 
   "HTML"];
EmbedCode[CloudDeploy[cityL]]
</pre>
<iframe src="https://www.wolframcloud.com/obj/intmath/cityL" width="800" height="600"></iframe>

<pre>
cityP = APIFunction[{"city" -> "City", 
    "province" -> "AdministrativeDivision"}, 
   GeoGraphics[{EdgeForm[Black], FaceForm[Red], Polygon[#province], 
      GeoMarker[#city]}, GeoScaleBar -> Automatic] &, "HTML"];
EmbedCode[CloudDeploy[cityP]]
</pre>
<iframe src="https://www.wolframcloud.com/obj/intmath/cityP" width="800" height="700"></iframe>