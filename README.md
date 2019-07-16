# UnityBluetoothtoArduino
Stage 4 of SUTD Capstone 45 Pico Musical Engineering Installation project.<br/>
Refer to the following [link](https://youtu.be/EubplCl5Q8s) for a demo.

Unity directly reads the corresponding text file and sends the notes to play to an Arduino via Serial communication.

Bluetooth communication between Unity and Arduino: https://assetstore.unity.com/packages/tools/network/bluetooth-le-for-ios-tvos-and-android-26661
This plugin only works for Android and iOS devices and not PC.

The Arduino script requires you to set up an electronic circuit with 25 LEDs/solenoids/etc as shown in the video. Ensure they are wired to the corresponding pin numbers as in the Arduino file. An Arduino MEGA was used for this project as it has enough number of pin holes.

2 octaves, fully chromatic scale is used to form 25 notes as shown below.
<img width="436" alt="midirange" src="https://user-images.githubusercontent.com/23626462/61297441-d77fdb80-a80e-11e9-857d-ced140331160.PNG">

Steps for uploading Arduino:
1. Wire the Arduino circuit containing HM10 Bluetooth module and solenoids.
2. Connect to your Arduino and upload the sketch in Arduino folder. 
3. If you run into TimeOut error, try the following:
  a. Ensure RXTX is disconnected during upload
  b. Ensure you have set the COM Port under Tools
  b. Click the reset button on the Arduino.

Steps for deploying on Android devices [deploy on Windows PC]:
3. Open the Jukebox project under Build folder in Android Studio.
4. Connect to your Android phone, enable USB Debugging options and Bluetooth & run application on the device.

For iOS devices [deploy on Mac PC]:
3. [to be updated]

To add new songs to the playlist:
1. Run Part 1 of https://github.com/ValereneGoh/MiditoArduino to convert to midi to interpretable text format files.
2. Add the text file to the folder under Assets > Scripts > txt.
3. Open Unity and manually create a new CD player and holder for the new song via the Prefab folder.

Test Scale under `Assets > Scripts > txt`:
1. After connecting, run the first item in the playlist to test connectivity of solenoids. It should play the full chromatic scale of 25 notes.
