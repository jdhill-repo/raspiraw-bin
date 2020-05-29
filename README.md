# raspiraw-bin
Raspiraw binaries

Raspiraw-bin contains the pre-compiled raspiraw binaries for use with the INDI PiCamera driver. They were compiled on a Raspberry PI 3 with the Raspbian OS from the source from https://github.com/6by9/raspiraw. Raspiraw-bin has been tested on both Rasbian and Mate (Astroberry) for the Raspberry Pi.

---------------------------------------------------------------------------------------------------------

# Install

To install, simply clone this repo, run the setup script, add the raspiraw-bin directory to the $PATH, and reboot with the commands below in a terminal:

	cd ~

	git clone https://github.com/jdhill-repo/raspiraw-bin.git

	cd raspiraw-bin

	sudo ./setup

	echo 'PATH=~/raspiraw-bin:$PATH' >> ~/.bashrc

	sudo reboot now

---------------------------------------------------------------------------------------------------------

# Test

To test the install enter the commands below in a terminal:

	cd ~/raspiraw-bin

	camera_i2c

and you should get a result similar to

	setting GPIO for board revsion: a22082
	Raspberry Pi3/Pi3+
	Set state of 133 to 1
	     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
	00:          -- -- -- -- -- -- -- -- -- -- -- -- -- 
	10: 10 -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
	20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
	30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
	40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
	50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
	60: -- -- -- -- 64 -- -- -- -- -- -- -- -- -- -- -- 
	70: -- -- -- -- -- -- -- --                         


---------------------------------------------------------------------------------------------------------

# Note

If raspiraw-bin is cloned to a directory different than instructed above, you will need to modify the camera_i2c script. Change line 113 of camera_i2c (~/raspiraw-bin/rpi3-gpiovirtbuf s 133 1) to include the full directory of where rpi3-gpiovirtbuf is located.

sudo nano camera_i2c

	change

	~/raspiraw-bin/rpi3-gpiovirtbuf s 133 1

	to

	/[directory of raspiraw-bin]/rpi3-gpiovirtbuf s 133 1

