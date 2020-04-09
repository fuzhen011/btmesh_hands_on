## File list to be Provided

- thunderboard folder to copy to hardware/kit/common/bsp
- config folder to copy to hardware/kit/EFR32MG12_BRD4166A to replace the
  existing one
- lc_sensor.c/h

## TODO Check List

### Activities for both project

- [x] Replace the libbluetooth.a library in the projects with the one provided

### Light

- [x] Modify the BSP files to avoid the warning for redefine, check commit
      #7af42c2 for more details

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
