
LPE Build instructions:
```
git clone https://github.com/TEAMIFOR/Firmware.git
cd Firmware
git submodule update --init --recursive
./Tools/fix_headers.sh
make px4fmu-v2_default (if build errors show up remove problematic header files)
make px4fmu-v2_default upload
```
Possible Erros and fixes:
```
Firmware/src/lib/matrix/matrix/stdlib_imports.hpp                      delete line <cinttypes>
Firmware/src/modules/sensors/common.h                                  add #include "mathlib/mathlib.h"
Firmware/src/modules/navigator/geofence.h                              change #include <cfloat> to <float.h>
Firmware/src/modules/navigator/mission.h                               change #include <cfloat> to <float.h>
Firmware/src/modules/navigator/navigator_main.cpp                      change #include <cfloat> to <float.h>
Firmware/src/lib/ecl/validation/data_validator_group.cpp               change #include <cfloat> to <float.h>
Firmware/src/modules/vtol_att_control/vtol_type.cpp                    change #include <cfloat> to <float.h>
Firmware/src/modules/fw_pos_control_l1/FixedwingPositionControl.hpp    change #include <cfloat> to <float.h>
Firmware/src/modules/gnd_pos_control/GroundRoverPositionControl.hpp    change #include <cfloat> to <float.h> 
```
Simulation env setup instrucs:
```
make posix_sitl_lpe gazebo_iris_opt_flow
```

