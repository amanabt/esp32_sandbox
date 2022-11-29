### Build and Make using ESP CMake framework

- [ ] Creating the project
	- [ ] Run `. $HOME/esp/esp-idf/export.sh`  in your terminal to export all the necessary environment variables needed for running esp
	- [ ] Create a project from the default template by running the command

``` bash
idf.py create-project <project name>
```
- A directory with the same name as the project should be created.
- The project structure should look something like this
``` bash
├── CMakeLists.txt
└── main
    ├── CMakeLists.txt
    └── Prototype_3.c
```
- Where `Prototype_3.c` is out main file with the following code in it
``` C++
#include <stdio.h>

void app_main(void)
{

}
```

- [ ] Populate the `app_main` function as per your needs and save
- [ ] **Building the project**
	- [ ] Create and `cd` into a `build` directory inside the project root
		- [ ] Run `IDF_TARGET=<esp model> cmake ..`, where `<esp model>` can be any one of the following `esp32`  `esp32s2` `esp32c3`  `esp32s3` `esp32c2` `linux` `esp32h2` `esp32c6`
		- [ ] Then to build the binaries run `make -j8` (here change the number 8 depending on the number of threads on which you want to run make)
- [ ] **Flashing the project**
	- Run `ESPPORT=</dev/tty USB port> make flash`
- [ ] **Monitoring the serial output:** Run `screen /dev/ttyUSBx 115200` where `ttyUSBx` should be replaced with the name of the ESP serial port.

