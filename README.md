## Presenter & Proctor

| Region | Presenter | Proctor 1 | Proctor 2 |
| ------ | --------- | --------- | --------- |
| APAC   | Kevin     | Steve     | -         |
| EMAR   | Kevin     | Badiss    | -         |
| AMER   | Steve     | Badiss    | -         |

## File list to be Provided

## TODO Check List

## Actions

- [x] Add sensor server and sensor setup server models to DCD.
  1. Open the \${PROJECT_NAME}.isc file.
  2. Click the Composition Data label and choose the Primary Element.
  3. Click the "+" button on the right of the "Bluetooth SIG Models" table to
     add
     - Sensor Server Model
     - Sensor Setup Model
  4. Save the file and click the "Generate" button on the top right corner.
- [x] Modify the BSP files to avoid the warning for redefine, check commit
      \#7af42c2 for more details
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

### Workaround

The smartphone app can't configure the sensor models if the node functionality
is set to "LC server". So, the node will bind the appkey(s) to the sensor server
model when new appkey added event is triggered.

- [x] add below line to _gecko_evt_mesh_node_key_added_id_ handler
  ```c
  on_appkey_added(&evt->data);
  ```
