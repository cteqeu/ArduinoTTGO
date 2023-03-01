# ArduinoTTGO

## Step 1
Collect sketch ino.bin file, bootloader.bin, partitions.bin and boot_app0.bin files  
## Step 2
Locate the esptool on your laptop, you can find this in the Arduino IDE messages when you upload a sketch to your TTGO board; for instance:   C:\\Users\\XXXXXXXXXXXXXXX\\AppData\\Local\\Arduino15\\packages\\esp32\\tools\\esptool_py\\4.5/esptool.exe  
## Step 3
Run command (sudo or admin may be needed)  

C:\\Users\\XXXXXXXXXXXXXXX\\AppData\\Local\\Arduino15\\packages\\esp32\\tools\\esptool_py\\4.5/esptool.exe 
--chip esp32 --port COM4 --baud 921600 --before default_reset --after hard_reset write_flash -z 
--flash_mode dio --flash_freq 80m --flash_size 4MB 
0x1000 ArduinoWiringTest595.ino.bootloader.bin 
0x8000 ArduinoWiringTest595.ino.partitions.bin 
0xe000 boot_app0.bin 
0x10000 ArduinoWiringTest595.ino.bin
