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


## Local GeoGraphics in `city` by Mathematica.

<pre>
cityL = APIFunction[{"city" -> "City"}, GeoGraphics[#city] &, 
   "HTML"];
EmbedCode[CloudDeploy[cityL]]
</pre>


<pre>
cityP = APIFunction[{"city" -> "City", 
    "province" -> "AdministrativeDivision"}, 
   GeoGraphics[{EdgeForm[Black], FaceForm[Red], Polygon[#province], 
      GeoMarker[#city]}, GeoScaleBar -> Automatic] &, "HTML"];
EmbedCode[CloudDeploy[cityP]]
</pre>


## FactorInteger

<pre>
func = APIFunction[{"x" -> "Integer"}, FactorInteger[#x] &, "HTML"];
EmbedCode[CloudDeploy[func]]
</pre>


## Integrate

<pre>
int = APIFunction[{"function" -> "Expression", 
    "variable" -> "Expression", "lowerLimit" -> "Real", 
    "upperLimit" -> "Real"}, 
   Integrate[#function, {#variable, #lowerLimit, #upperLimit}] &, 
   "HTML"];
EmbedCode[CloudDeploy[int]]
</pre>


## Factor

<pre>
fac = APIFunction[{"polynomial" -> "Expression"}, 
   Factor[#polynomial] &, "HTML"];
EmbedCode[CloudDeploy[fac]]
</pre>
