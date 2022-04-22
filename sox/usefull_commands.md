# Some usefull commands to pipe a program to sox and working with raw audio format
---
```
sox -n -t waveaudio synth 1 sin 6k
```
Play 6k Hz tone with "waveaudio" audio device driver.  

---

```
sox -n -t raw -r 48k -c 1 -b 8 sin.000 synth 1 sin 6000
```
Generate "sin.000" file to store 6k Hz audio tone in raw format.  

---

```
sox -t raw -r 48k -b 8 -e signed-integer sin.000 -t waveaudio
```
Play raw formatted input file "sin.000" with "waveaudio" audio device driver.  

---

```
./tone6k.exe | sox -t raw -r 48k -b 8 -e signed-integer - -t waveaudio
```
Play output of ./tone6k.exe  
Here is C code of tone6k:
```
#include <stdio.h>
#include <math.h>

int main(void) {
	double d;
	char i = 0;
	while (1) {
		d = ((double) i)/4*M_PI;
		printf("%c", (int) (127*sin(d)));
		i++;
		if (i==8) i=0;
	}
	return 0;
}
```
