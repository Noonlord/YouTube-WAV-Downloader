from os import walk
import os
import sys
link = sys.argv[1]
os.system("youtube-dl --extract-audio " + link)

vidID= link.split("=")[1]
print "VidID = " + vidID
mypath = "/home/pi/fmtransmitter/FM_Transmitter_RPi3"
f = []
for (dirpath, dirnames, filenames) in walk(mypath):
    f.extend(filenames)
    break
for i in range(0, len(f)):
        if ".opus" in f[i] and vidID in f[i]:
                vidName = f[i]
                print vidName
                cmdstr = "ffmpeg -i \"" + vidName + "\" -f wav -flags bitexact \"" + vidName[:-5] + ".wav"  + "\""
                print cmdstr
                os.system(cmdstr)
                os.remove(vidName)
