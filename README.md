## Description:
This is a very simple program that drives an 8x8 LED Matrix. If you try the code without modifying it, by default it counts from 
1 to 3 with a 1 second delay (for 4MHz clock). To make it more useful you'll have to create more MATRIX_SET_X subroutines, one for each character you want to display. 

## Configuration:
The program by default uses PORTB for the LED Matrix rows and PORTC for the columns. The method we use to achieve 
the character displaying is called row scanning (you can google it for more details). 

For this to work first you have to load the row registers with the data you want to display, to do this you simply 
call a MATRIX_SET_X subroutine. Currently the code has only three MATRIX_SET_X subroutines for displaying the characters 
'1', '2' and '3', but it is very easy to create your one. You can just copy and paste one of these three and change some bits. 
If you want to contribute to this project by creating more characters please let me know. I have also found a usefull Windows program that makes
it easy to design characters on LED Matrix you can find it [here](https://web.archive.org/web/20140819053200/http://www.avrprojects.info/files/files/Matrix-Display-designer.zip).

Second, you have to display the character to the LED Matrix by using the MATRIX_WRITE subroutine. 
In order to been able to actual see the result you have to keep displaying the character on the LED 
Matrix for a period of time, in order for the human eye to have the chance to see it. I have created a subroutine 
named MATRIX_WRITE_1S that does this for 1 second, but you can create your own if you want. You can also modify this subroutine 
in order you to pass the delay with a register, but I made it just 1 second to keep it simple. 

##Hardware Support:
To make this to work first you need an 8x8 LED Matrix, no any fancy serial LED Matrices just a simple with regular LEDs. 
And because I know you don't want to buy it, it is very easy to create your own. The schematic 
is very simple just google LED Matrix Schematic and you will find out.

Second, you will need a 16Fxxx PIC with at least two ports with 8 bits each.

The delays are based on a 4MHz crystal, 
if you want to use an higher speed you may have to modify the delays, with a lower speed you will just have a 
slower response unless you modify the delays.
