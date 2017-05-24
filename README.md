# vios_speechtotext
This is just a basic text to speech conversion software.

# Unzip the cmusphinx_final.zip file

Run

# bash g.sh

This will install the pocketsphinx5prealpha software to your pc.

Ignore the pc.wav and pc2.wav files for now
They are already converted to text by the bash g.sh command.

Now you need to upload a voice recording which should necessarily be a single-channel (monaural), little-endian, unheadered 16-bit signed PCM audio file sampled at 16000 Hz.

To convert mp3 to wav of desired specification do the following
#sox input.mp3 -c 1 -r 16000 -b 16  output.wav

To run pocketsphinx on a prerecorded file :
#pocketsphinx_continuous -lm language_model.lm -dict dictionary.dic -infile file.wav

To run live speech to text conversion :
#pocketsphinx_continuous -lm language_model.lm -dict dictionary.dic -inmic yes


If the number of commands you want to generate are small enough then create a corpus file. This file should have no digits, no symbols, only characters. Have a look at corpus.txt in your system.

Next go to http://www.speech.cs.cmu.edu/tools/lmtool-new.html and upload the clean corpus file and compile knowledge base. Download and unzip the files and now you can use the language model and dictionary compiled in pocketsphinx_continuos
