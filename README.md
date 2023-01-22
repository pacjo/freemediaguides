# FreeMediaGuides - preserve the information

## Extracting audio

### universal method - VLC and sndcpy

this allows for recording audio from android phone directly into pc with minimal noise

#### Android instructions:
  1. enable developer settings
  2. enable USB debugging
  3. agree for debugging when connecting device to PC

#### PC instructions:
  1. install VLC
  2. get latest release of [sndcpy](https://github.com/rom1v/sndcpy) (version with adb included)
  3. modify `sndcpy.bat`: </br>
    - set VLC file path in `if not defined VLC set VLC="C:\Program Files\VideoLAN\VLC\vlc.exe"` </br>
    - remove `-Idummy` from `%VLC% -Idummy --demux rawaud --network-caching=0 --play-and-exit tcp://localhost:%SNDCPY_PORT%` </br>
  4. run `sndcpy.bat`. Now you should have opened terminal and VLC
  5. start recording in VLC in `Playback` > `Record`
  6. connect your device and start playback
  7. finish recording. now you can close VLC and sndcpy window. your recorded file should be `C:\Users\<username>\Music`
