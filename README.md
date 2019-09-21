import RPi.GPIO as GPIO
GPIO.setmode(GPIO.BOARD)
GPIO.setup(7,GPIO.OUT)
GPIO.setup(8,GPIO.OUT)
GPIO.setup(9,GPIO.OUT)
GPIO.setup(10,GPIO.OUT)
window = tk()
window.title("Raspberry GUI Home Automation System")
window.geometry('800x600')
 
def relay1_on():
GPIO.output(7,True)
relay1_status.configure(text = "ON")
button_relay1.configure(command = relay1_off)
 
def relay1_off():
GPIO.output(7,Flase)
relay1_status.configure(text = "OFF")
button_relay1.configure(command = relay1_on)
 
def relay2_on():
GPIO.output(8,True)
relay2_status.configure(text = "ON")
button_relay2.configure(command = relay2_off)
 
def relay2_off():
GPIO.output(8,Flase)
Relay2_status.configure(text = "OFF")
button_relay2.configure(command = relay2_on)
 
def relay3_on():
GPIO.output(9,True)
relay3_status.configure(text = "ON")
button_relay3.configure(command = relay3_off)
 
def relay3_off():
GPIO.output(9,Flase)
relay3_status.configure(text = "OFF")
button_relay3.configure(command = relay3_on)
 
def relay4_on():
GPIO.output(10,True)
Relay4_status.configure(text = "ON")
button_relay4.configure(command = relay4_off)
 
def relay4_off():
GPIO.output(10,Flase)
relay4_status.configure(text = "OFF")
button_relay4.configure(command = relay4_on)
 
def cleanup():
GPIO.output(7,Flase)
 
GPIO.output(8,Flase)
GPIO.output(9,Flase)
GPIO.output(10,Flase)
 
relay1_status = Label(window, relief ="flat", width = 4)
relay2_status = Label(window, relief ="flat", width = 4)
relay3_status = Label(window, relief ="flat", width = 4)
relay4_status = Label(window, relief ="flat", width = 4)
 
button_relay1 = Button(window)
button_relay2 = Button(window)
button_relay3 = Button(window)
button_relay4 = Button(window)
 
button_relay1.configure(text="RELAY1",command=relay1_on)
button_relay2.configure(text="RELAY2",command=relay2_on)
button_relay3.configure(text="RELAY3",command=relay3_on)
button_relay4.configure(text="RELAY4",command=relay4_on)
 
relay1_status.configure(text="OFF")
relay2_status.configure(text="OFF")
relay3_status.configure(text="OFF")
relay4_status.configure(text="OFF")
 
button_relay1.grid(row=1,column=1,columnspan=1)
red_led_relay1.grid(row=1,column=2,padx=10)
 
button_relay2.grid(row=1,column=1,columnspan=1)
red_led_relay2.grid(row=1,column=2,padx=10)
 
button_relay3.grid(row=1,column=1,columnspan=1)
red_led_relay3.grid(row=1,column=2,padx=10)
 
button_relay4.grid(row=1,column=1,columnspan=1)
red_led_relay4.grid(row=1,column=2,padx=10)
 
 
atexit.register(cleanup)
window.mainloop()

