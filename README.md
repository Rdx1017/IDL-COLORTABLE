# IDL-COLORTABLE

I have confused the pro 'loadct' cannot work in a right way for some days until i saw this doc.

When the case ---DEVICE, DECOMPOSED=0

      Set this keyword to 0 to cause color values to be interpreted as indices into a color lookup table.
      
      Such as :
          DEVICE, DECOMPOSED=0
          LOADCT, 7
          PLOT, INDGEN(10), COLOR=180
      
When the case ---DEVICE, DECOMPOSED=1

      Set this keyword to 1 to cause color values to be interpreted as 24-bit color specifications. 
      
      Such as :
          DEVICE, DECOMPOSED=1
          PLOT, INDGEN(10), COLOR='FF00FF'x      

      
## MAYBE THE INIT CASE IS DECOMPOSED = 1(for my computer).
