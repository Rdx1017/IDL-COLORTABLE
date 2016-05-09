# IDL-COLORTABLE

I have confused the pro 'loadct' cannot work in a right way for some days until i saw this help doc.

When the case ---DEVICE, DECOMPOSED=0

      Set this keyword to 0 to cause color values to be interpreted as indices into a color lookup table.
      
      Such as :
      
      ```
          DEVICE, DECOMPOSED=1, COLOR=1
          PLOT, INDGEN(10), COLOR='FF00FF'x
      ```
      
When the case ---DEVICE, DECOMPOSED=1

      Set this keyword to 1 to cause color values to be interpreted as 24-bit color specifications. 
      
      Such as :
      
      ```
          DEVICE, DECOMPOSED=0, COLOR=1
          LOADCT, 7
          PLOT, INDGEN(10), COLOR=180
      ```
      
## MAYBE THE INIT CASE IS DECOMPOSED = 0(for my computer).
