# RZ_A2M_Mbed_samples
This is a collection of sample programs that work on RZ/A2M boards.  
You can try Mbed OS for RZ/A2M with the following board.
- GR-MANGO


## Overview
Sample program files are located under the ``sample_programs`` folder.  
You can try each sample program by changing the following macro in``sample_select.h``.  
```cpp
#define SAMPLE_PROGRAM_NO  0
```

| No.| Program file                                                                          | Description                                                  |
|:---|:--------------------------------------------------------------------------------------|:-------------------------------------------------------------|
|  0 | [sample_00_led_rtc_analogin.cpp](sample_programs/sample_00_led_rtc_analogin.cpp)      | DigitalOut, InterruptIn, RTC, Timer and AnalogI              |
|  1 | [sample_01_flash_write.cpp](sample_programs/sample_01_flash_write.cpp)                | FlashAPI sample                                              |
|  2 | [sample_02_ssif_loop_back.cpp](sample_programs/sample_02_ssif_loop_back.cpp)          | SSIF loop back sample                                        |
|  4 | [sample_04_ssif_wav_playback.cpp](sample_programs/sample_04_ssif_wav_playback.cpp)    | SSIF wav playback sample (use USB memory or SD card)         |
|  7 | [sample_07_usb_func_serial.cpp](sample_programs/sample_07_usb_func_serial.cpp)        | USBSerial (CDC) sample [\*1]                                 |
|  8 | [sample_08_usb_func_mouse.cpp](sample_programs/sample_08_usb_func_mouse.cpp)          | USBMouse sample [\*1]                                        |
|  9 | [sample_09_usb_func_keyboard.cpp](sample_programs/sample_09_usb_func_keyboard.cpp)    | USBKeyboard sample [\*1]                                     |
| 10 | [sample_10_usb_func_midi.cpp](sample_programs/sample_10_usb_func_midi.cpp)            | USBMIDI sample [\*1]                                         |
| 11 | [sample_11_usb_func_audio_1.cpp](sample_programs/sample_11_usb_func_audio_1.cpp)      | USBAudio sample [\*1]                                        |
| 12 | [sample_12_usb_func_audio_2.cpp](sample_programs/sample_12_usb_func_audio_2.cpp)      | USBAudio and SSIF sample [\*1]                               |
| 13 | [sample_13_ether_http.cpp](sample_programs/sample_13_ether_http.cpp)                  | Ether HTTP sample                                            |
| 14 | [sample_14_ether_https.cpp](sample_programs/sample_14_ether_https.cpp)                | Ether HTTPS sample                                           |
| 16 | [sample_16_usb_func_msd_1.cpp](sample_programs/sample_16_usb_func_msd_1.cpp)          | USBMSD and FlashAPI sample [\*1]                             |
| 17 | [sample_17_usb_func_msd_2.cpp](sample_programs/sample_17_usb_func_msd_2.cpp)          | USBMSD and FlashAPI sample advanced version [\*1]            |
| 18 | [sample_18_mipi_drp_lcd.cpp](sample_programs/sample_18_mipi_drp_lcd.cpp)              | MIPI, DRP and LCD sample                                     |
| 19 | [sample_19_mipi_drp_diplayapp.cpp](sample_programs/sample_19_mipi_drp_diplayapp.cpp)  | MIPI, DRP and USBSerial (CDC) sample (use "DisplayApp") [\*1]|
| 20 | [sample_20_drp_dynamic_loading.cpp](sample_programs/sample_20_drp_dynamic_loading.cpp)| DRP Dynamic Loading Sample                                   |
| 21 | [sample_21_deep_standby_alarm.cpp](sample_programs/sample_21_deep_standby_alarm.cpp)  | Deep standby and RTC alarm sample                            |
| 22 | [sample_22_hdmi_disp_ssif.cpp](sample_programs/sample_22_hdmi_disp_ssif.cpp.cpp)      | HDMI output and SSIF wav playback Sample                     |
| 23 | [sample_23_mipi_hdmi.cpp](sample_programs/sample_23_mipi_hdmi.cpp)                    | HDMI output and MIPI Sample                                  |


## About custom boot loaders
This sample uses ``custom bootloader`` ``revision 5``, and you can drag & drop the "xxxx_application.bin" file to write the program. Please see [here](https://github.com/d-kato/bootloader_d_n_d) for the detail.  
### How to write program
When using ``DAPLink``, please use ``xxxx.bin`` as following.  
1. Connect the ``micro USB type B terminal`` to the PC using a USB cable.
2. You can find the ``MBED`` directory.
3. Drag & drop ``xxxx.bin`` to the ``MBED`` directory.  
4. When writing is completed, press the reset button.  

When using ``custom bootloader``, please use ``xxxx_application.bin`` as following.  
1. Connect the ``USB type C terminal`` to the PC using a USB cable.  
2. Hold down ``USB0`` and press the reset button.  
3. You can find the ``GR-MANG`` directory.  
4. Drag & drop ``xxxx_application.bin`` to the ``GR-MANGO`` directory.  
5. When writing is completed, press the reset button.  

**Attention!**  
For the first time only, you need to write a ``custom bootloader`` using ``DAPLink``.  

## Development environment
You can use ``Mbed CLI (CUI)`` or ``Mbed Studio (GUI)``. Choose your preferred development environment.  


### When using Mbed CLI (CUI)
You can use ``GCC``, ``Arm Compiler 5``, ``Arm Compiler 6`` and ``IAR``. A license is required to use a compiler other than the ``GCC`` compiler.  
Information of Mbed CLI that includes install&quick start guide is as the following.  
[Installation](https://github.com/ARMmbed/mbed-cli/blob/1.8.3/README.md#installation)  

How to import and build this sample  
```
$ cd <projects directory>
$ mbed import https://github.com/d-kato/RZ_A2M_Mbed_samples
$ cd RZ_A2M_Mbed_samples
$ mbed compile -m <TARGET> -t GCC_ARM --profile debug
```

Set the following to ``<TARGET>``.  
- GR-MANGO beta version : ``GR_MANGO``  

See [About custom boot loaders](#about-custom-boot-loaders) for program writing.  
See [How to debug using e2studio](#how-to-debug-using-e2studio) for debugging.  


### When using Mbed Studio (GUI)
You can use ``Arm Compiler 6`` included with Mbed Studio for free.  
Information of Mbed Studio that includes install&quick start guide is as the following.  
[Installation](https://os.mbed.com/studio/)  

How to import and build this sample  
![](docs/img/how_to_use_mbed_stusio_1.png)  
![](docs/img/how_to_use_mbed_stusio_2.png)  
![](docs/img/how_to_use_mbed_stusio_3.png)  
**Attention!** : When using the GR-MANGO, select "Target" box to ``GR_MANGO``. When using the RZ/A2M Evaluation Board Kit with HyperFlash boot, select "Target" box to ``RZ_A2M_EVB_HF``.  
![](docs/img/how_to_use_mbed_stusio_4.png)  


**Attention!**  
You can not debug using Mbed Studio. Use only for build purposes. Debug the elf file created by Mbed Studio using e2studio.  

See [About custom boot loaders](#about-custom-boot-loaders) for program writing.  
See [How to debug using e2studio](#how-to-debug-using-e2studio) for debugging.  


## Terminal setting
If you want to confirm the serial communication the terminal soft on your PC, please specify the below values.  
You can change the baud rate by ``platform.stio-baud-rate`` of ``mbed_app.json``.  

|             |         |
|:------------|:--------|
| Baud rate   | 115,200 |
| Data        | 8bit    |
| Parity      | none    |
| Stop        | 1bit    |
| Flow control| none    |

## How to debug using e2studio
Download [e2studio 7.4.0 or lator](https://www.renesas.com/eu/en/products/software-tools/tools/ide/e2studio.html), and install. (Debugger : J-Link Base)  
Connect the J-Link to your board.  
![](docs/img/how_to_debug_using_e2studio_1.png)  
![](docs/img/how_to_debug_using_e2studio_2.png)  
![](docs/img/how_to_debug_using_e2studio_3.png)  
![](docs/img/how_to_debug_using_e2studio_4.png)  
![](docs/img/how_to_debug_using_e2studio_5.png)  
![](docs/img/how_to_debug_using_e2studio_6.png)  
![](docs/img/how_to_debug_using_e2studio_7.png)  
![](docs/img/how_to_debug_using_e2studio_8.png)  
![](docs/img/how_to_debug_using_e2studio_9.png)  
![](docs/img/how_to_debug_using_e2studio_10.png)  
