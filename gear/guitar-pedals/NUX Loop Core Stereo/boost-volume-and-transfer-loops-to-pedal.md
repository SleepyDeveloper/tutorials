# Boost loop volume and transfer to pedal

Have you ever recorded a loop only to find the volume too low? 
Did max out the loop volume, but your guitar is still drowning out the loop?
This tutorial will teach you how to boost the volume of your loop using [FFMPEG](https://ffmpeg.org).

**Prerequisites** 

* Record a loop with your [Loop Core Studio](https://www.nuxaudio.com/loopcorestereo.html)
* Install [FFMPEG](https://ffmpeg.org).

**1.** First you'll need to connect the loop pedal to your computer. You'll need a 
USB-C cable to plug into the Loop Core Stereo. Depending on your computer you'll
either need a USB-C to USB-A, or USB-C to USB-C cable.

**2.** Find the loop you need to boost.

The Loop Core Stereo has 99 storage slots. When connected to your computer you'll find 
numbered folders corresponding to each storage slot preceeded by a '0'. Each loop is 
saved as a **.WAV** file. These files are also named after its slot preceeded by a 'W'. 
For example, the loop stored in slot 50 is named **W055.WAV** and found in the **050** 
folder. 

Once you've located the file, you can copy it to your computer by dragging it to the 
desktop.

**3.** Boost the volume

Now that you have saved the loop, it's time to use FFMPEG to boost the volume. From 
the command line navigate to the folder where you saved your loop file. 

You will find the basic syntax for adjusting the volume below.

```
$ ffmpeg -i <input_file> -af volume=<volume_level> <output_file>
```

* *-i <input_file>* - The input file
* *-af* - This stands for audio filter. Ffmpeg supports multiple filters.  Use the 
*volume* filter to change the volume. You can raise and lower the volume. Using a 
whole number will multiple the volume by that amount. Set `volume=10` to 10x the volume.
* *<output_file>* - The output file. Since you'll be creating a new file, you'll be
able compare before and after.

**IMPORTANT** The Loop Core Stereo only supports 44.1 kHz 32-bit Stereo floating WAV files. By default, ffmpeg will
use 16-bit encoding. You'll need to set `-acodec pcm_f32le` to use 32-bit floating. To be safe, you can make sure
ffmpeg creates a 44.1 kHz audio file with `-ar 44100`. With these things in mind you will find the updated syntax below.


```
$ ffmpeg -i <input_file> -af volume=<volume_level> -acodec pcm_f32le -ar 44100 <output_file>
```

To boost loop number 50's volume 10x, fun the following command.

```
$ ffmpeg -i W050.WAV -af volume=10 -acodec pcm_f32le -ar 44100 W050-new.WAV
```

Now that that's done, take a listen to both files. Is your new file louder? If so, you're ready to move the file back to your Loop Core Stereo. If not, try changing the `volume` parameter.

**4.** Transfer the file to the Loop Core Stereo

Following the same naming convention, find the folder corresponding to the file you just ehanced. 

W050-new.WAV goes into the 050 folder.

Once you've transfered the file, you'll need to delete the previous one, and rename your file to match the W0[0-9][0-9].WAV format.

Now you're ready to disconnect and test.

**5.** Disconnect the Loop Core Stereo

1. Dismount the NUX LOOPER from your computer. 
2. Disconnect the usb cable. 

**6.** Test your newly volume boosted loop

Select the loop you just updated. If the number is **RED** then you've done everything correctly. If it's **WHITE** then something went wrong (is the filename correct? Is the file 44.1 KHz 32-bit?)

## Conclusion

Congratulations! You can now use ffmpeg to make audio adjustments. It's also a great tool for video! You can re-encode videos, extract the audio into a seperate file that you can encode into mp3, wav, etc. You also know how to encode audio into Core Loop Stereo compatible files. 

If you found this tutorial useful, please star this repo. Please follow me on Twitter [@SleepyDeveloper](https://x.com/sleepydeveloper). You can also find me on Youtube @ [SleepyDeveloper Tutorials]()

## Extra Credit

Do you have a video that has some audio that you'd like to loop and play along with? Use ffmpeg to:

1. extract the audio
1. clip the audio file to the segment you want
1. encode the file to 44.1 kHz 32-bit Stereo floating
1. name the file after the loop slot you want it to be
1. transfer the loop your Core Loop Stereo
1. Enjoy your jam session 
