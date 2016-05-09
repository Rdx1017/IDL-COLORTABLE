#IDL loadct

##DEVICE Procedure

###DECOMPOSED
**(PS, WIN, X, Z)**

Set this keyword to control how color values are interpreted when using displays with decomposed color (TrueColor or DirectColor visuals). This keyword has no effect on indexed-color devices, which generally specify color using 8 bits per pixel.

Set this keyword to 1 to cause color values to be interpreted as 24-bit color specifications. IDL interprets the specified value as three 8‑bit color values, where the least-significant 8 bits contain the red value, the next 8 bits contain the green value, and the most-significant 8 bits contain the blue value. For example, the following lines draw a plot in purple on a device capable of rendering 24-bit color:

DEVICE, DECOMPOSED=1, COLOR=1
PLOT, INDGEN(10), COLOR='FF00FF'x
Here, the color value 'FF00FF'x is hexadecimal notation for the RGB triple [255,0,255].

Note: Unlike IDL object graphics, IDL’s direct graphics devices do not accept RGB triples as color specifications. Hexadecimal notation is generally the easiest way to specify 24-bit color values to direct graphics devices.

Set this keyword to 0 to cause color values to be interpreted as indices into a color lookup table. IDL interprets the least-significant 8 bits of the color value as the color table index. This setting allows users with decomposed color displays to use IDL programs written for indexed-color displays without modification.

DEVICE, DECOMPOSED=0, COLOR=1
LOADCT, 7
PLOT, INDGEN(10), COLOR=180
Here, the color value 180 is interpreted as an index into color table 7 (Red-Purple). Note that specifying COLOR='0000B4'x would produce the same result, since B4 is the hexadecimal notation of decimal 180.

In older versions of IDL, color index values higher than !D.N_COLORS-1 were clipped to !D.N_COLORS-1 in the higher level graphics routines. In some cases, this clipping caused the exclusive-OR graphics mode to malfunction with raster displays. This clipping has been removed. Programs that incorrectly specified color indices higher than !D.N_COLORS-1 will now probably exhibit different behavior.

The value of the DECOMPOSED keyword remains in effect until changed or until the IDL session ends. Use the GET_DECOMPOSED keyword to DEVICE to retrieve the current value.