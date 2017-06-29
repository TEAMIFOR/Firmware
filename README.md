## PX4 Pro Drone Autopilot ##

project src github.com/px4/firmware

LPE Build instructions:

git clone https://github.com/TEAMIFOR/Firmware.git
cd Firmware
git submodule update --init --recursive
./Tools/fix_headers.sh
make px4fmu-v2_default (if build errors show up remove problematic header files)

make px4fmu-v2_default upload
