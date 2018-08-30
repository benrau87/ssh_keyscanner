# ssh keyscanner - search shodan for a given ssh hostkey fingerprint.

This tool has thee modes, currently. It can search given a public-key you provide it, use a known fingerprint or, it can fingerprint a host and search shodan for similar hosts.

It now has support for doing the keygrab over tor, and works on hidden services. This is useful for finding, uh, shittily configured ones.

## Howto:
The tool has 4 args, outlined below.   
* "-i", for target host. You must set either this, -l, -f, or -k
* "-f", for SSH Public Key file. You must set either this, -f, or -i.  
* "-k", for Finger Print that is known. You must set either this, -f, or -i.
* "-l", for lists of target hosts. Alternative to -i or -f.  
* "-d", for directories of keys. Not yet implemented!
* "-p", for target port. This defaults to 22.
* "-t", uses Tor for the SSH key grabbing. Good for Hidden Services ;)

You should also edit the script to put in your own [Shodan](https://www.shodan.io/) API key, as you can't have mine. You can probably just borrow someone elses, [as people leave them all over github](https://github.com/0x27/shodan_key_checker).

## Requirements
This tool depends on the following:  
[Paramiko](http://www.paramiko.org/)  
[sshpubkeys](https://github.com/ojarva/python-sshpubkeys)  
[shodan](https://github.com/achillean/shodan-python)  
[PySocks](https://github.com/Anorov/PySocks)  
You can get them with ```pip install -r requirements.txt``` or whatever. The rest should be stdlib.

You may need to run pip install six -upgrade 

Note: I only bothered testing on Kali


## Licence
[Licenced under the WTFPL][Licence]

## Changelog  
18-01-2015 (01:26): - Added Tor support on a whim. Completely untested, will get tested in the morning when I wake up.
30-8-2018  (11:50): - Add support for raw fingerprint with -k option.
