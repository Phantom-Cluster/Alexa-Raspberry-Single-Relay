# Alexa Controlling Raspberry Power Relay (Single Channel Code)

Before Using this code, Keep in Mind  :

 * Make Sure Raspbian is install on Raspberry Pi
 * Run Sudo apt-get Update" and "Sudo apt-get install" before running any command
 * This Program is Completly Design on Python with Virtual WeMos
 


If You Accidently Fried Your Raspberry Pi or Relay Please Don't Blame Me.

You Need !
 * Raspberry Pi 3 or 2 
 * Power Relay
 * Power Adapter to Turn On Raspberry i Recommended 5v 2 Amp

And here's some code! where You Have to Make Changes :+1:

```javascript
 #TRIGGERS = {str(sys.argv[1]): int(sys.argv[2])}
    TRIGGERS = {"Lights": 52000}

    def act(self, client_address, state, name):
        print("State", state, "from client @", client_address)
        GPIO.setmode(GPIO.BOARD) ## Use board pin numbering
        GPIO.setup(int(7), GPIO.OUT)   ## Setup GPIO Pin to OUTPUT
        print("Alexa Recognise Lights")
        if state==True:
            GPIO.output(int(7), state) ## State is true/false
            print("Lights are Turned On:D, Alexa You Are Doing Great Job")
        else:
            GPIO.cleanup(int(7))
            print("Lights are Turned Off :( Saving Energy :D once Again Great Job")
        return True
```
In above Code Change (7) with your GPIO Pin number and "Lights" with Trigger Word.

You Only Need to Run RPi_name_port_gpio.py file to make this relay detect i recommended you to add this file with Startup so you don't need to run this File Every Single Time.

If You Are Looking for 8 Channel Relay Coding for Alexa, i Did it with Node MCU v3 [Check code on GitHub](https://github.com/Phantom-Cluster/echo)


