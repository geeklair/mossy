# Setup Home Assistant

[Home Assistant](https://www.home-assistant.io) calls itself a "*Open source home automation that puts local control and privacy first. Powered by a worldwide community of tinkerers and DIY enthusiasts. Perfect to run on a Raspberry Pi or a local server.*"

It's power is two fold.  First, it has "integrations" that link HASS to every kind of web server and smart device imaginable.  Second, it is running locally, in your house.  If your Internet goes down, all of your local automations continue to work just fine. 

## Download and Install HASS

It is possible to get a RPi4 image from Home Assitant that includes the OS *and* all the HASS software in one image.  That seems like cheating.  It also makes it harder to know what is being installed where, and how your platform was modified.  So for this path, we choose the install-hass-by-hand method.

As one tinker put it "I tried Hassbian and HASS.IO 3, but they left me feeling like I had taken over someone else’s computer after they’d installed, deleted, modified, and configured the OS and applications ... not a good place to start. I finally decided to load Raspbian, and HA myself, and that has worked well for me."


### Update your RPi4

The first step, is to update all your packages.  The core RPi OS that you installed probably has dozens of packages that can be updated, and should be updated for security reasons.

	ssh pi@ipaddress
	sudo apt-get update
	sudo apt-get upgrade -y
	
Ok.... that might take quite a while, but will give you a very up-to-date system.

Next, we have to fix the crazy oversight by the Debians that Emacs is not installed by default.

	sudo apt-get install emacs

Ok, now the world is better, and the remaining work can be started.

## Follow These Instructions

There are some excellent command line instructions for [installing HASS by hand](https://www.home-assistant.io/docs/installation/raspberry-pi/).

The only caveat was that Debian "Buster", which was the most recent Raspberry Pi OS updated to Python3.7.

So the command from the web page `python3.8 -m venv .` should be replaced with `python3.7 -m venv .`

Otherwise, all went well just following the manual install provided by home-assistant.io.

However... HASS support for Python 3.7 is deprecated, and support will end in December 2020.  So there are some work-arounds.... still investigating...

Places I'm looking:
	[Python3.8 back-port to Buster](https://community.home-assistant.io/t/home-assistant-core-python-3-8-backport-for-debian-buster/234859)
	
	[Run Home Assistant in a Docker container](https://www.home-assistant.io/docs/installation/docker/)
	

	
	
	
	