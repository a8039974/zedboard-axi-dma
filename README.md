zedboard-axi-dma
================

Demonstration project for the AXI DMA Engine on the ZedBoard

## Requirements

This project is designed for Vivado 2019.2. If you are using an older version of Vivado, then you *MUST* use an older version
of this repository. Refer to the [list of commits](https://github.com/fpgadeveloper/zedboard-axi-dma/commits/master "list of commits")
to find links to the older versions of this repository.

* Vivado 2019.2
* Vitis 2019.2
* [ZedBoard](http://zedboard.org "ZedBoard")

## Description

This project demonstrates the use of the AXI DMA Engine IP for transferring
data between a custom IP block and memory. A tutorial for recreating this project
from the Vivado GUI can be found here:

http://www.fpgadeveloper.com/2014/08/using-the-axi-dma-in-vivado.html

## Build instructions

To use the sources in this repository, please follow these steps:

1. Download the repo as a zip file and extract the files to a directory
   on your hard drive --OR-- Git users: clone the repo to your hard drive
2. Open Windows Explorer, browse to the repo files on your hard drive.
3. In the Vivado directory, you will find multiple batch files (*.bat).
   Double click on the batch file that is appropriate to your hardware,
   for example, double-click `build-zedboard.bat` if you are using the ZedBoard.
   This will generate a Vivado project for your hardware platform.
4. Run Vivado and open the project that was just created.
5. Click Generate bitstream.
6. When the bitstream is successfully generated, select `File->Export->Export Hardware`.
   In the window that opens, tick "Include bitstream" and "Local to project".
7. Return to Windows Explorer and browse to the Vitis directory in the repo.
8. Double click the `build-vitis.bat` batch file. The batch file will run the
   `build-vitis.tcl` script and build the Vitis workspace containing the hardware
   design and the software application.
9. Run Vitis and select the workspace to be the Vitis directory of the repo.
10. Connect and power up the hardware.
11. Open a Putty terminal to view the UART output.
12. In the Vitis, select `Xilinx Tools->Program FPGA`.
13. Click on the application and click the Run icon from the toolbar.

This project uses an example application for the AXI DMA that is located here:

`C:\Xilinx\Vitis\<version>\data\embeddedsw\XilinxProcessorIPLib\drivers\axidma_v<ver>\examples\xaxidma_example_sg_poll.c`

The Vitis build script creates an application and copies that source file into the application.
See the readme in the Vitis directory for more information.

## Troubleshooting

Check the following if the project fails to build or generate a bitstream:

### 1. Are you using the correct version of Vivado for this version of the repository?
Check the version specified in the Requirements section of this readme file. Note that this project is regularly maintained to the latest
version of Vivado and you may have to refer to an earlier commit of this repo if you are using an older version of Vivado.

### 2. Did you follow the Build instructions in this readme file?
All the projects in the repo are built, synthesised and implemented to a bitstream before being committed, so if you follow the
instructions, there should not be any build issues.

### 3. Did you copy/clone the repo into a short directory structure?
Vivado doesn't cope well with long directory structures, so copy/clone the repo into a short directory structure such as
`C:\projects\`. When working in long directory structures, you can get errors relating to missing files, particularly files 
that are normally generated by Vivado (FIFOs, etc).

## License

Feel free to modify the code for your specific application.

## Fork and share

If you port this project to another hardware platform, please send me the
code or push it onto GitHub and send me the link so I can post it on my
website. The more people that benefit, the better.

## About us

This project was developed by [Opsero Inc.](http://opsero.com "Opsero Inc."),
a tight-knit team of FPGA experts delivering FPGA products and design services to start-ups and tech companies. 
Follow our blog, [FPGA Developer](http://www.fpgadeveloper.com "FPGA Developer"), for news, tutorials and
updates on the awesome projects we work on.