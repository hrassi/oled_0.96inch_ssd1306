the driver file for the i2c 0.96 inch oled is the ssd1306.py
i added the file ssd1306_graphics.py with it for more fonctions
like fill_circle, ect..
so the 2 files ssd1306.py and ssd1306_graphics.py should be uploaded
to the esp32

usage :

wire the oled vcc pin to the 3.3v pin of the esp
wire the oled gnd pin to the gnd pin of the esp
wire the oled scl pin to the gpio 22 of esp (default i2c)
wire the oled sda pin to the gipo 21 of esp (default i2c)
    
inside the ssd1306_graphics.py declare the width and heigh of the screen (ex: 128x64)
declare also the i2c pins and the i2c address of the oled ( default is usually 0x3c)

now in the main.py :
from ssd1306_graphics import GraphicsSSD1306

then create object : 
oled = GraphicsSSD1306()

then clear the screen with black pixels : 
oled.fill(0)

then use the folowing fonctions and after put oled.show()

oled.pixel(x, y, 1)         Turns on the pixel at (x, y)
oled.pixel(x, y, 0)         Turns off the pixel at (x, y)
oled.text("Hi", x, y, 1)    Writes text in white
oled.text("Hi", x, y, 0)    Writes text in black (erases)
oled.line(x0,y0,x1,y1,1)    Draws a line
oled.line(x0,y0,x1,y1,0)    Erases a line
oled.rect(x,y,w,h,1)        Draws a rectangle outline
oled.rect(x,y,w,h,0)        Erases rectangle outline
oled.fill_rect(x,y,w,h,1)   Draws filled rectangle
oled.fill_rect(x,y,w,h,0)   Erases filled rectangle
oled.circle(x,y,r,1)        Draws a circle
oled.circle(x,y,r,0)        Erases a circle
oled.fill_circle(x,y,r,1)   Draws filled circle
oled.fill_circle(x,y,r,0)   Erases filled circle