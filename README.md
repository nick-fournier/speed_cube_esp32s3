# TFT_eSP ESP-IDF Setup
The TFT_eSPI library has been updated by a user (dracir9) in pull request #1770 to enable
use with the ESP-IDF.

https://github.com/Bodmer/TFT_eSPI/pull/1770

The library author (Bodmer) does not use the ESP-IDF so will not be able to provide support!

There are two ways to configure the library either:

    manually enter the setup in menuconfig
    OR
    delete the KConfig file, select your LCD/board in the User_Setup_Select.h file, and run "idf.py reconfigure"

The following menuconfig instructions were posted by dracir9 as part of the pull request #1770:

https://github.com/Bodmer/TFT_eSPI/pull/1770#issuecomment-1096478997

In the above link the instructions include useful hyperlinks. The bare text of the
instructions is included below.

Steps to use:

  1.  Install ESP-IDF toolchain. The easiest way is to use VS Code and the ESP-IDF extension
      which handles most of the work automatically. Make sure to install version V4.4. From
      now on I'll assume that VS Code is being used.
 
  2.  Once ESP-IDF is installed open VS Code and press F1. Type ESP-IDF: New Project. Hit enter.
  
  3.  Enter your project name, directory and board (if not sure choose ESP32 chip (via ESP-PROG)).
      If your board is connected choose serial port. Leave ESP-IDF component directory blank and
      press Choose Template.
      
  4.  In the drop-down choose Extension and select Arduino-as-component. (This is not mandatory.
      You can try other templates if you want). This will create a blank project with a simple
      main source file in the "main" folder.
      
  5.  Now we have to add Arduino to your project. You can find the complete documentation here:
      https://github.com/espressif/arduino-esp32
      
      and here:
      https://docs.espressif.com/projects/arduino-esp32/en/latest/esp-idf_component.html
      
      I'll list two methods that I use most of the time:

      5.1. Press F1 and type ESP-IDF: Add Arduino ESP32 as ESP-IDF Component. This will
      automatically download and install the latest code from the arduino esp-32 repository.
      This is the easiest method but as it uses the latest code it may introduce compilation errors.

      5.2. Go to the Arduino esp-32 repository release page. Choose a version and find its "Assets"
      section. Download the source code file into "project directory/components". Extract the
      compressed file. This will create a folder called arduino-esp32-2.x.x. Rename it to arduino.
      This method is slightly more complex but ensures you choose a stable version.
      
  6.  Download the TFT_eSPI library into the components folder
  
  7.  Now open VS Code and load your project folder. Press F1 and type ESP-IDF: SDK Configuration
      editor (menuconfig). Alternatively press Ctrl+E, G or press the gear button in the bottom left
      corner.
      
  8.  This will open the project configuration menu. Navigate to the TFT_eSPI section and configure
      the library (TFT driver, pins, fonts, etc.).
      
  9.  Press F1 and type ESP-IDF: Build your project. Alternatively press Ctrl+E, B or click the
      build button in the bottom left corner.
      
 10.  Choose your port by typing ESP-IDF: Select port to use or with the button in the bottom left.
 
 11.  Upload your code with the lightning button in the bottom toolbar.
 
 12.  Enjoy!