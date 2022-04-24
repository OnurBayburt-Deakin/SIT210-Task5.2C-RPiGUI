#Import modules
import RPi.GPIO as GPIO
from tkinter import *


#Initialise GPIO pins
GPIO.setmode(GPIO.BOARD)
GPIO.setup(11, GPIO.OUT)
GPIO.setup(13, GPIO.OUT)
GPIO.setup(15, GPIO.OUT)


#Initialise the GUI
GUI = Tk()
GUI.title('Switch on LEDs')
defaultbg = GUI.cget('bg')


#Start program with LEDs off by default
GPIO.output(11, GPIO.LOW)
GPIO.output(13, GPIO.LOW)
GPIO.output(15, GPIO.LOW)


#Functions to control buttons and LEDs        
def red_click():
    red_button.config(bg = "yellow")
    green_button.config(bg = defaultbg)
    blue_button.config(bg = defaultbg)
    GPIO.output(11, GPIO.HIGH)
    GPIO.output(13, GPIO.LOW)
    GPIO.output(15, GPIO.LOW)

def green_click():
    green_button.config(bg = "yellow")
    red_button.config(bg = defaultbg)
    blue_button.config(bg = defaultbg)
    GPIO.output(13, GPIO.HIGH)
    GPIO.output(11, GPIO.LOW)
    GPIO.output(15, GPIO.LOW)

def blue_click():
    blue_button.config(bg = "yellow")
    red_button.config(bg = defaultbg)
    green_button.config(bg = defaultbg)
    GPIO.output(15, GPIO.HIGH)
    GPIO.output(11, GPIO.LOW)
    GPIO.output(13, GPIO.LOW)
    
def close():
    red_button.config(bg = defaultbg)
    green_button.config(bg = defaultbg)
    blue_button.config(bg = defaultbg)
    GPIO.output(11, GPIO.LOW)
    GPIO.output(13, GPIO.LOW)
    GPIO.output(15, GPIO.LOW)
    GUI.destroy()


#Create GUI buttons
red_image = PhotoImage(file = 'red.png')
red_button = Button(GUI, image = red_image, command = red_click)
green_image = PhotoImage(file = 'green.png')
green_button = Button(GUI, image = green_image, command = green_click)
blue_image = PhotoImage(file = 'blue.png')
blue_button = Button(GUI, image = blue_image, command = blue_click)
close = Button(GUI, text = 'Close', command = close)


#Align GUI buttons
red_button.grid(row = 0, column = 0, padx = 10, pady = 10)
green_button.grid(row = 1, column = 0, padx = 10, pady = 0)
blue_button.grid(row = 2, column = 0, padx = 10, pady = 10)
close.grid(row = 3, column = 0, padx = 20, pady = 10)


#Keep the window open until the 'Close' button is pressed 
mainloop()
