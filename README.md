## File list to be Provided

## TODO Check List

## Actions

- [x] Modify the BSP files to avoid the warning for redefine, check commit
      #7af42c2 for more details
- [x] Add "${workspace_loc:/${ProjName}/lab}" to the include path
- [x] Replace the libbluetooth.a library in the projects with the one provided
- [x] Remove the _gecko_bgapi_class_mesh_test_init();_ comment, then add below
      lines under it.
  ```c
  gecko_bgapi_class_mesh_sensor_server_init();
  gecko_bgapi_class_mesh_sensor_setup_server_init();
  ```
- [x] Add below lines to the app.c at the include paths area
  ```c
  #undef SUB_MODULE_NAME
  #define SUB_MODULE_NAME "app"
  #include "lab.h"
  ```
- [x] ?Add the self config function to the node initialized event.
  ```c
    self_config(pData);
  ```
- [] Remove the "ENABLE_LOGGING=1" from the Symbols setting
  ```

  ```

### Switch

- [x] Add "${workspace_loc:/${ProjName}/hardware/kit/common/bsp/thunderboard}" to
  include paths
- [x] Add "${workspace_loc:/${ProjName}/hardware/kit/common/drivers}" to include
  paths
- [] Add sensor server model and sensor setup model to DCD, instructions needed.

  - placeholder for instructions

- [x] Add the lc_sensor.c/h pair
  - [] Add the implementation for sensor sampling cause this shouldn't be part
    of the purposes of the training.
  - [] Add function prototype for sending the sensor messages to LC server
