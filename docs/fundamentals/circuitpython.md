# Set up CircuitPython
Use Python on Microcontrollers!

While not installed by default, the USB Nugget supports flashing with CircuitPython, a beginner-friendly programming language for microcontrollers based on Python maintained by Adafruit.

!!! warning "WARNING!"
    This will erase your current USB Nugget installation, and you'll need to update your USB Nugget again before using it as a USB attack platform

## Set up the bootloader to enable USB support
To set up CircuitPython on the S2 Nugget, navigate here: https://circuitpython.org/board/lolin_s2_mini/

Go to the section that says “Install, Repair, or Update UF2 Bootloader” and click the purple “Download bootloader ZIP” at the bottom.

Plug board into a USB port on your computer using a data/sync cable. Make sure it is the only board plugged in, and that a charge-only cable is not being used.

Press and hold down the BOOT or 0 button, press and release the RESET or RST button, and then release the BOOT button.

In the Chrome browser, navigate to: https://adafruit.github.io/Adafruit_WebSerial_ESPTool/

Select 460800 Baud from the pull-down menu (top-right).

Click Connect (top-right).

Select the COM or Serial port from the pop-up window.

After successful connection, click Erase.

After successful erase, click any Choose a file…, then locate and select the combined.bin file unzipped earlier.

After successfully choosing combined.bin, click Program.

After the TinyUF2 firmware update is complete, press the RESET button on the board. A new drive BOOT should be visible in your file browser.

## Install CircuitPython
Go back to https://circuitpython.org/board/lolin_s2_mini/ and download the .UF2 file for the latest stable version of CircuitPython.

Once the .UF2 file downloads, drag and drop it into the drive that appears when you plug in your S2 Nugget.

This should automatically install CircuitPython on your S2 Nugget!

## Programming in CircuitPython
Download and install Mu Editor from here: https://codewith.mu/

Open Mu editor and select CircuitPython editing mode.

Name your file code.py, this will be automatically run each time the board boots.

Save your code to the board, it will automatically re-run your code each time you save changes to it.

To add files, drag and drop them from your computer to the board

### Using the NeoPixel
In Mu Editor, create a new file, name it “code.py”, and save it to your CIRCUITPY drive.

Copy or download the following script into your file: https://github.com/RetiaLLC/S2-Nugget/blob/main/NeoPixelTest_CircuitPy_Nugget.py

At the bottom of the script (on lines 55-58), uncomment the function you’d like to test.

You can choose from:

1. SetAll(r,g,b) Uncomment this to test setting all neopixels to a single color (set your own values)
2. RandomColor() Uncomment this to test setting all neopixels to random colors
3. VividColor() Uncomment this to test setting all neopixels to vivid random colors using some math
4. RandomChase() Uncomment this to test creating a racing animation for neopixel strips or rings

### Reading WiFi Packets
To try out Wi-Fi packet parsing, download the Wifi_Deauth_Detector_Example.zip file here: https://github.com/RetiaLLC/S2-Nugget/blob/main/Wifi_Deauth_Detector_Example.zip

Unzip the .ZIP file, and drag and drop the contents into your CircuitPy board, overwriting the existing /lib folder and code.py

Open Code.py to see the code under the hood, otherwise the code should run and detect deauth packets with a shocked anime face.

### Controlling the screen
To try loading a bitmap on the screen, download the OLED Bitmap example here: https://github.com/RetiaLLC/S2-Nugget/blob/main/OLED_Bitmap_Example.zip

Unzip the .ZIP file, and drag and drop the contents into your CircuitPy board, overwriting the existing /lib folder and code.py

You can drag and drop black and white .BMP images that are 128X64 onto your board and display them by changing the file path in code.py

### HID Attack Examples
The S2 Nugget supports HID attacks! You can pretend to be a keyboard or mouse to send keystrokes or control mouse movements.

To try out the HID attack examples, download the ZIP file here: https://github.com/RetiaLLC/S2-Nugget/blob/main/HID_Attack_CircuitPython_Examples.zip

Unzip the .ZIP file, and drag and drop the contents into your CircuitPy board, overwriting the existing /lib folder and code.py

You’ll find 3 examples, which include:

- MacOS_HID_Payload - Pretends to be a keyboard, when inserted into MacOS computer, opens a terminal window and injects a payload. Currently set to “curl parrot.live” which makes a dancing parrot appear. Uses the screen on the S2 Nugget to show the status of the payload.
- Simple_HID_Payload - Bare-bones HID payload to inject keystrokes, currently set for MacOS to “curl parrot.live” which makes a dancing parrot appear.
- Screen_Mouse_Jiggler - Turns the S2 Nugget into a mouse jiggler. When the right button is pressed, the mouse is moved randomly. On screen instructions.
- Simple_Mouse_Jiggler - Bare-bones mouse jiggler with no screen or neopixel indicator

You can easily add payloads for your own operating system! For more CircuiptPython HID documentation, see here: https://circuitpython.readthedocs.io/projects/hid/en/latest/

To run an example, make a copy of the script and rename it “code.py”, overwriting the old “code.py” file.

Your S2 Nugget will automatically reload and run the current code.py script.

You can find a full written guide to flashing here: https://circuitpython.org/board/lolin_s2_mini/

Once you have CircuitPython installed, check out our supported project on our CircuitPython GitHub repository.
