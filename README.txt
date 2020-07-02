# CODASReader
Python library to read CODAS files and convert them to ASCII or use directly in Python.
For information on the CODAS file format visit https://www.dataq.com/resources/techinfo/ff.htm
or view the document in this folder.

A CODAS file can be read by initializing a new CODASReader object, giving the file location / name as an argument.
The header of the file will then be read automatically (this is the default, can be changed if so desired) and stored in the object.
The header must always be read first before reading other parts of the file or accessing information from it.
The CODASReader class includes separate functions to read the file's ADC data section and the trailer.
When reading the ADC data, the channels that should be read, as well as the time frame can be passed on as optional arguments.
The readADC function also includes a saveMemory mode which is turned on by default.
This reads and stores the data as a 16 bit integer and saves the scaling factor for each channel separately.
It is completely lossless and it is neccessary for reading large files at once.

After reading the different sections of the CODAS file, information from the header can be printed or returned using the respective functions.
Information that can be otained this way include:
  Number of acquired channels
  Start time and date of data acquesition
  End time and date of data acquesition
  Duration of data acquesition
  Channel information from the header
  Sample rate

The class also supports printing the header and the trailer of the file to the console.
The ADC data can be saved as a csv file with a custom header to the sepcified file location using saveADCToCSV().

The class is entirely compatible with packed and HiRes files as described by CODAS file format document.

The CODASReader.py file can also be run from the comman line using command line arguments.
The file header and file trailer are read automatically from the specified file location.
The command line arguments allow limited access to the api including:
  Print header
  Print trailer
  Print start time of acquesition
  Print duration of acquesition
  Print number pf acquired channels
  Print sampling rate
  
Additionally the ADC data can be read and save to a csv file.
Using additional arguments, the channels that should be read, the time frame, the name of the csv file and a custom header for the file can be specified.