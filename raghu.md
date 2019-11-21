<!----- Conversion time: 1.756 seconds.


Using this Markdown file:

1. Cut and paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β17
* Thu Nov 21 2019 04:31:45 GMT-0800 (PST)
* Source doc: https://docs.google.com/open?id=1nHFM-HUsHAX7irusz8FDA6aPdr87GDYMN6b3GR7DVWE
----->



## Instructions to run the BLE application on NUCLEO board



1. Access to two git repositories
    1. [https://bitbucket.org/pp_wiced/pp_new/src/master/](https://bitbucket.org/pp_wiced/pp_new/src/master/)
    2. [https://bitbucket.org/pp_wiced/pp_dev/src/master/](https://bitbucket.org/pp_wiced/pp_dev/src/master/)  
1. In pp_new repository, checkout  to [wwd_port_nucleo_boards](https://bitbucket.org/pp_wiced/pp_new/branch/wwd_port_nucleo_boards) branch.  Go to the folder ~/pp_new/pp_sdk/libraries and the run below command  to create a soft link to pp_libraries

    ```
    $ ln -s   ~/pp_dev/pp_libraries
    ```


1. Create a soft link to ARM GNU GCC compiler. Download the toolchain if not present from the below link:

    [https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)

2. Download latest Cypress WICED SDK. Go to pp_new/pp_sdk and then give the following command to create a soft link to bluetooth directory in WICED SDK:

    ```
    $ ln -s ~/43xxx_Wi-Fi/libraries/drivers/bluetooth
    ```


3. Go to pp_new/pp_sdk and run the below build command:

     		`$make PLATFORM=NUCLEO_L496`



1. Follow the below table to connect the wires from NUCLEO board to Murata usd-m.2 adapter. 

    Refer below document to understand jumper connections in Murata board. 


    [https://drive.google.com/file/d/14fHdt3veI7jF4vHgTB2N96CU1flLIgzT/view?usp=sharing](https://drive.google.com/file/d/14fHdt3veI7jF4vHgTB2N96CU1flLIgzT/view?usp=sharing) 


<table>
  <tr>
   <td rowspan="2" >
S.NO
   </td>
   <td colspan="4" >NUCLEO BOARD
   </td>
   <td colspan="3" >1DX MODEL 
   </td>
  </tr>
  <tr>
   <td>PORT
   </td>
   <td>
   </td>
   <td>Connector 
   </td>
   <td>Pin 
   </td>
   <td>
   </td>
   <td>Connector 
   </td>
   <td>pin
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td> PA0
   </td>
   <td>CTS
   </td>
   <td>CN10
   </td>
   <td>29
   </td>
   <td>RTS
   </td>
   <td>J8
   </td>
   <td>3
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>PA1
   </td>
   <td>RTS
   </td>
   <td>CN10
   </td>
   <td>11
   </td>
   <td>CTS
   </td>
   <td>J8
   </td>
   <td>4
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>PA2
   </td>
   <td>TXD
   </td>
   <td>CN10
   </td>
   <td>13
   </td>
   <td>RXD
   </td>
   <td>J9
   </td>
   <td>2
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>PA3
   </td>
   <td>RXD
   </td>
   <td>CN9
   </td>
   <td>1
   </td>
   <td>TXD
   </td>
   <td>J9
   </td>
   <td>1
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>PA4
   </td>
   <td>DEV-WAKE
   </td>
   <td>CN7
   </td>
   <td>17
   </td>
   <td>DEV-WAKE
   </td>
   <td>J9
   </td>
   <td>8
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>PA5
   </td>
   <td>HOST-WAKE
   </td>
   <td>CN7
   </td>
   <td>10
   </td>
   <td>HOST-WAKE
   </td>
   <td>J9
   </td>
   <td>6
   </td>
  </tr>
  <tr>
   <td>7
   </td>
   <td>PB0
   </td>
   <td>REG-ON
   </td>
   <td>CN10
   </td>
   <td>31
   </td>
   <td>REG-ON
   </td>
   <td>J9
   </td>
   <td>4
   </td>
  </tr>
  <tr>
   <td>8
   </td>
   <td colspan="2" >VCC
   </td>
   <td>CN8
   </td>
   <td>7
   </td>
   <td>VCC
   </td>
   <td>J7
   </td>
   <td>2
   </td>
  </tr>
  <tr>
   <td>9
   </td>
   <td colspan="2" >GND
   </td>
   <td>CN8
   </td>
   <td>11
   </td>
   <td>GND
   </td>
   <td>J7
   </td>
   <td>6
   </td>
  </tr>
</table>




*   In the Murata board, the jumper J11 should be removed if connected.
*   In header J1, jumper needs to be placed in pins 1 and 2.
1. Downloading the binary to the board is of two types:

    **Method 1:**


    Once the board is connected to your system, it will be detected as a drive(like pendrive). Copy the app.bin from build folder to this drive.


    Board will reset automatically.


    **Method 2:**


    Go to OpenOCD executable directory and give the below command. Download OpenOCD if not present from below link:


[https://sourceforge.net/projects/openocd/files/openocd/0.10.0/](https://sourceforge.net/projects/openocd/files/openocd/0.10.0/)



    1. `$ openocd  -f scripts/interface/stlink-v2-1.cfg -f scripts/target/stm32l4x.cfg -c init -c targets -c "reset halt"`
    2. Downloading using gdb:

        Open another terminal, go to the build directory, and run the following command.


	


```
    $ arm-none-eabi-gdb -ex " file app.elf" -ex "tar rem :3333"
```



    At the gdb prompt, give the load command as below:

			`(gdb) load`


    After loading, to run the program, physically reset the board by pressing reset button.



1. Open minicom to get the console and type the commands. 

    ```
    pp_cli> help

    pp_cli> ble_start
    ```


1. Download the BLE scanner application in android mobile that is available in Play store. Open the application and scan for BLE devices. Connect to HELLO. Then we get the list of services available.

<!-- Docs to Markdown version 1.0β17 -->
