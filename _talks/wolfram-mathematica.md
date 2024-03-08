---
layout: archive
title: "Mathematica"
permalink: /talks/Mathematica
date: 2024-02-21
---
# Mathematica CloudDeploy APIFunction.

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

## FactorInteger

<pre>
func = APIFunction[{"x" -> "Integer"}, FactorInteger[#x] &, "HTML"];
EmbedCode[CloudDeploy[func]]
</pre>
<iframe src="https://www.wolframcloud.com/obj/intmath/FactorInteger" width="800" height="600"></iframe>

## Integrate

<pre>
int = APIFunction[{"function" -> "Expression", 
    "variable" -> "Expression", "lowerLimit" -> "Real", 
    "upperLimit" -> "Real"}, 
   Integrate[#function, {#variable, #lowerLimit, #upperLimit}] &, 
   "HTML"];
EmbedCode[CloudDeploy[int]]
</pre>
<iframe src="https://www.wolframcloud.com/obj/intmath/integrate" width="800" height="1210"></iframe>