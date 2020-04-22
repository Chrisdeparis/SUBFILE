# SIMPLE SUBFILE

## Load All Subfile

In Load-All subfile all the records are written to the subfile buffer at once and then the data in the subfile loaded from the buffer.
   
In this case SFLSIZ should be at-least 1 greater than the SFLPAG.
   
If we are writing more records in the subfile buffer than the SFLSIZ declared and SFLSIZ<9999, then the SFLSIZ is extended to accommodate all records till the size of 9999. 9999 is the buffer limit.
   
In this case PAGEUP AND PAGEDOWN is taken care by system. SFLPAG should be less than SFLSIZ.
   
In load-All subfile if we do PAGEDOWN and then press ENTER on the page, by-default ENTER bring the display screen to the very first page irrespective of the current page number. To avoid this situation, we use file information data structure to get the current page RRN number and pass it to the SFLRCDNBR hidden field defined in the display file DDS.
