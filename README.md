## This patch provides layered output for the pdf() graphics device.

+ **./add_pdf_layers_2.16.0.diff** - This is a patch for R v2.16.0 (Unsuffered Consequences)
+ **./add_pdf_layers_r61733.diff** - This is a patch for the top of the development tree as of 23/01/2013
(revision 61733)

### to install:

    cd [R-root]
    patch -p1<add_pdf_layers_xxx.diff

As of yet there is no automated test to check for proper 
function of the layers in pdf().

### To use: 

    >pdf("file/name", onepage=TRUE)
    >plot(a figure)       #layer 0 (background)
    >plot(another figure) #layer 1 (foreground)
    >[continue...]
    >dev.off()

Layers will render as expected in viewers such based on poppler
and such, also in Adobe reader products.

In Adobe professional products (CS# etc) the layers will appear 
as analogous clipping groups.
