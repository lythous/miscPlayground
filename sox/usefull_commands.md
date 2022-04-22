'''
sox -t raw -r 48k -b 8 -e signed-integer sin.000 -t waveaudio
'''
play raw input file "sin.000" with audio device "waveaudio"
