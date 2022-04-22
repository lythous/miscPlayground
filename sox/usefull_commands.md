```
sox -n -t waveaudio synth 1 sin 6k
```
Play 6k Hz tone with "waveaudio" audio device driver.  
<br/>

```
sox -n -t raw -r 48k -c 1 -b 8 sin.000 synth 1 sin 6000
```
Generate "sin.000" file to store 6k Hz audio tone in raw format.  
<br/>

```
sox -t raw -r 48k -b 8 -e signed-integer sin.000 -t waveaudio
```
Play raw formatted input file "sin.000" with "waveaudio" audio device driver.  
<br/>

