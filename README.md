## Play StepMania 5.0.12 On a Raspberry Pi 400

<img src="https://i.imgur.com/aY1JXX7.jpg" width="600">

### Hardware

1. Raspberry Pi 400 kit with 32GB sd card for extra room for multiple song packs.
2. A ROCCAT - Juke Virtual 7.1 USB Stereo External Sound Card since the pi can't handle the audio play back.
3. Logitech - z533 Multimedia Speakers for a nice, boomy audio experience.
4. StepManiax Stage from <a href="https://shop.steprevolution.com/collections/frontpage/products/stepmaniax-stage-5th-generation">https://shop.steprevolution.com/collections/frontpage/products/stepmaniax-stage-5th-generation</a> or any pad of your choice.
5. Simfiles provided from <a href="https://zenius-i-vanisher.com/v5.2/simfiles.php?category=simfiles">https://zenius-i-vanisher.com/v5.2/simfiles.php?category=simfiles</a>

### Build & Install

1. Grab the latest source release from <a href="https://github.com/stepmania/stepmania/releases/tag/v5.0.12">https://github.com/stepmania/stepmania/releases/tag/v5.0.12</a>
2. Extract it somewhere and then enter into the Build folder.
3. Install these dependencies `sudo apt-get install cmake gcc g++ libmad0-dev libgtk2.0-dev binutils-dev git-core make libasound2-dev yasm libc6-dev libogg-dev libvorbis-dev libbz2-dev zlib1g-dev libjpeg8-dev libpng12-dev libxtst-dev libxrandr-dev libglew-dev libglu1-mesa-dev mesa-common-dev automake autoconf libva-dev libjack-dev`
4. Then run `cmake -G "Unix Makefiles" .. && cmake -DWITH_CRASH_HANDLER=0 -DWITH_SSE2=0 -DWITH_FULL_RELEASE=1 -DWITH_MINIMAID=0 ..`
5. Once done configuring run `make`
6. Upon completion you should now have a stepmania executable in the parent directory.
7. If you're using an external audio card then you may need to tell stepmania which sound device to use. You can change the device by opening ~/.stepmania-5.0/Save/Preferences.ini and modifying line 191 to say `SoundDevice=plughw:1,0`
8. Download all of your desired song packs and then drop them in the Songs folder where your stepmania executable resides. All songs should always be grouped in a folder. I group all my songs in folders by mix like "Dance Dance Revolution 2014, Dance Dance Revolution Extreme, etc."
