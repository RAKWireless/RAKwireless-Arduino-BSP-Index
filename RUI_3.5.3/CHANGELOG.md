## [Unreleased] - 2022-11-24
  
### Added

### Changed

### Fixed

## [3.5.3] - 2022-11-24
  
### Added

### Changed
- Change power saving mode to used STOP1 for RAK3172 and RAK3172-sip to fix UART1 could not trigger system wake up
- Change UART1 used HSI Clock for RAK3172 and RAK3172-sip to fix UART1 could not trigger system wake up

### Fixed
- Fixed UART1 could not trigger system wake up

## [3.5.1] - 2022-9-2
  
### Added
- Support RAK3401
- Add AT+BOOTVER

### Changed
- RUI-557: Full BW set for LoRa
- RUI-629: Class C high power consumption
- RUI-632: To support all ADC, not only ADC1, ADC2
- RUI-661: [DEV]Enable ADC3/ADC4/ADC
- RUI-690: Adding AT cmds in system level & Bootloader/ Application need to add AT cmds function.
- LCTT timer optimization processing, during operation, only one LCTT timer runs
- Disable detect UART/I2C pin for going into boot mode
- Disable AT+LPM=2
- Disable Scheduler for all model
- Release AT commnad version 1.5.7
- Release API version 3.2.2

### Fixed
- RUI-554: RAK3172 UART baudrate support 2400 bps
- RUI-635: [Doxygen_ATCMD] According to Doxygen AT+PSF range is 5~12,but I run "AT+PSF=5" response " AT_PARAM_ERROR"
- RUI-639: [AT_CMD] After ATZ, RX2FQ should keep the last validated setting.
- RUI-640: [AT_CMD] Input the long data at once, UART will lose data.
- RUI-651: at+join=1:0:10:5 does not retry to connect after the first trial
- RUI-652: [AT_CMD] After the baud rate is set to 4800, it can not be restored to 115200.
- RUI-663: [ClassB] The device failed to receive beacon when AT+LPM=1
- RUI-667: [AT_CMD] Preamble Length = {5-65535}, "AT+P2P=470MHz:7:20000:0:65550:14" should return AT_PARAM_ERROR
- RUI-668: [AT_CMD] "AT+PRECV=?" and "AT+RMVMULC=?", Command without query should return AT_PARAM_ERROR
- RUI-685: [AT_CMD] "AT+ADDMULC=" Input incorrect parameters should not be written successfully.
- RUI-703: [LCTT] If AT+LPM=1 by default, the LCTT test fails
- RUI-709: [AT+CMD]AT+SLEEP causes the device to crash
- RUI-732: [Bootloader]RAK3172 Entering AT Command in Boot mode will print twice AT not support
- RUI-740: [Lora]RAK4631 ClassC cannot receive downlink data
- RUI-735: PC detects that the device name of RAK3401 is "Rak4631 Serial COM"
- RUI-739: System_Serial_Lock example compile fail

## [3.5.0] - 2022-07-15

### Added
- Support RAK5010.
- RUI-145: [DEV] Implementation on Scheduler API for RAK3172
- Add AT+TIMEREQ.
- Add AT+DEBUG.
- Add AT+LPM.
- Add Wire1 instance for Arduino Wire library.
- For RAK4630/RAK5010, add AT+BLEMAC.
- Add AWS MQTT SSL example.
- Add RUI3-Power-Test example.

### Changed
- Enhance SPI master performance.
- Open the source of UHAL layer.
- Optimize LINK ADR logic,reject LINK ADR when ADR is closed
- Optimizing logical processing for querying multicast groups
- Use timer for Smart Farm example.
- Add delay 10s for BLE Configuration example, or user can't see the logs.
- RUI-630: [Doc]add AT+VER=?can read that the device is in Boot mode

### Fixed
- RUI-335: EU868 CLASS A +EVT:SEND_CONFIRMED_FAILED
- RUI-392: [UART] UART transmission takes a lot of time.
- RUI-508: [Firmware] Buffer overflow condition occurs inside service_lora_lstmulc function
- RUI-490: Variable overflow problem for "last_dlink_data_size" parameter
- RUI-489: Inside At_Restore function, else if (ret = -UDRV_BUSY) only has one equal operator
- RUI-488: [RUI API] service_lora_trssi(int16_t *rssiVal) function returns pointer
- RUI-480: [Firmware] There is only one equal operator inside if statement
- RUI-479: [Firmware] There is only one equal operator inside if statement
- RUI-456: [RUI_API] When IO_1 is triggered, just WakeUP and then continue Sleep again
- RUI-491: [BLE] Compared to BLE SPEC, the range of advertising intervals is too different.
- RUI-493: [BLE] Advertise Tx Power set functional fail.
- RUI-503: [RUI API] api.ble.uart.start() will system crash
- RUI-492: [BLE] Advertise interval set functional fail.
- RUI-515: [BLE] Setting up Advertising data will crash if there is no pre-action.
- RUI-446: no analogOversampling function on rak3172(rak5811)
- RUI-433: no analogOversampling function on rak4631(rak5811)
- RUI-533: [RUI API] [SensorHub] After Uploading Data for a while, connect USB debug port to PC and crash happened.
- RUI-439: The program will get stuck at 100 lines on rak3172(rak1901)
- RUI-458: [RUI_ATCMD]Baud rate is not saved after power failure
- RUI-517: [BLE] BLE_Beacon_Custom_Payload example program note error
- Fix LoRa P2P example's bug.
- RUI-428: Parameter problem of the analogReference() function on rak3172(rak19006)
- RUI-427: Parameter problem of the analogReference() function on rak4631(rak19006)
- RUI-471: api.system.sleep.lora(10000); puts everything into sleep. Loop() is not continuing after call
- RUI-459: [RUI_ATCMD]AT+LOCK and AT+PWORD can be queried, inconsistent with the document,and the return value of AT+LOCK is not standard
- RUI-460: [RUI_ATCMD]The AT+SLEEP range is incorrect
- RUI-457: [RUI_ATCMD]AT+APM=1 should be return AT_PARAM_ERROR(AT+APM/AT+ATM/ATZ/ATR/AT+BOOT)
- RUI-514: [NBIOT]BG96 AT Command cannot be used. The NBIOT function cannot be tested
- RUI-477: [RUI API] To modify txpower with “api.ble.settings.txPower.set(power)” in beacon mode is not work.
- RUI-454: [RUI_API] RUI3 - RAK5010 Doxygen LPS22HB / pressure (MIKKIBAR) error ,it should be pressure(MILLIBAR)
- RUI-453: [RUI_API] Undefined reference to `rak1901::deinit()'
- RUI-436: rak2305 needs to add delay before it can run normally on rak4631
- RUI-432: "SERIAL_PORT_HARDWARE "is not defined on rak4631(rak5802)
- RUI-424: The default band for low-frequency nodes is 4
- RUI-390: [SPI] SPI transmission takes a lot of time.
- RUI-379: classC ABP mode sends AT+JOIN=1:0:7:5 is reported AT_ERROR
- RUI-516: [BLE] The api.ble.settings.broadcastName.get() will fail after setting the advertising data.
- RUI-513: [BLE] Advertising set Advertising data to Complete Local Name fail.
- RUI-570: When there is Code in the Void loop, the device will sleep automatically.
- RUI-597: [RUI API] About RAK5010, can't use RUI API to get BG96's response.
- RUI-595: [NBIOT]5010 Maximum number of sent bytes supported
- RUI-591: [NBIOT] Example RAK5010_Access_HTTP_Server commmand "AT+QHTTPREADFILE=" always response ERROR:730
- RUI-583: [NBIOT] BG96 bg96_write funtion appears unknown "⸮"
- RUI-581: [classB]AT+CLASS=? B:S3 status display error
- RUI-579: Because powering on BG96 is slow, we have at least 60s time to keep it on. However, every activity on AT command should restart the 60s timer.
- RUI-577: RAK5010 naming is not correct in Arduino IDE
- RUI-571: [NBIOT] BG96 command cannot be used after baud rate is changed
- RUI-569: [NBIOT]BG96 command? will return ATCELL: Send a command to LTE module
- RUI-558: The behavior of RAK4631, RAK5010 and RAK3172 is inconsistent when they reboot after entering boot mode.
- RUI-550: [classB]Sending data during beacon search returns AT_BUSY_ERROR, device stuck
- RUI-549: [classB]AT_ERROR is reported when data is sent in ClassB mode
- RUI-547: [classB]The device in ClassB mode cannot receive downlink data
- RUI-546: [classB] Pingslot Open window does not print PS:Done
- RUI-544: [AT+CMD]AT command return 'AT_ERROR' should be 'AT_PARAM_ERROR'
- RUI-442: The code compiles properly, downloads to Core and doesn't execute on rak3172(rak14000)
- RUI-430: rak18000 compiler error::PDM.h: No such file or directory on rak4631
- RUI-429: rak12500 UART interface cannot communicate properly on rak4631
- RUI-407: Beacon search failed to print twice +EVT: BC FAILED (zengtao 643)
- RUI-402: [RUI API] Execute RAK12500 Official Uart example, it prints an error value and is not a search step
- RUI-596: RAK3172 randomly goes into boot mode when production or testing
- RUI-637: [Doxygen_ATCMD] Send Long Packet Data with hexadecimal "ABCDEF" should be work.
- RUI-617: ATCELL+QFUPL is too hard to use.

## [3.4.2] - 2022-05-18

### Added

### Changed
- RUI-345: TX1 used as recovery pin causes problems on RAK3172/RAK4631 if a module is used that uses RX1/TX1
  - Add a new way to enter DFU mode: double clicking on reset button.
  - Remove button DFU mechanism that is triggered by UART1 TX pin.
- Enable NFC.
- Use single bank DFU instead of dual bank DFU to prevent factory default & user data being erased.

### Fixed
- RUI-377: AT+SLEEP command not working if AT+PRECV=0 is used.
- RUI-347: [RUI API]If join network fails, the join packet is not sent again, even if api.lorawan.join is called again.
- Fix I/O interrupt for RAK3172
- RUI-405: Arduino BSP to support right code size after compilation
- RUI-391: Arduino BSP reports wrong code size after compilation
- Fix BLE crash after single clicking reset button.
- Fix an issue that RAK12007 could not be displayed
- Fix AT command permission of non-writable AT commands.

## [3.4.1] - 2022-05-14

### Added
- Add RUI3-Sensor-Node example.

### Changed
- The maximum clock of SPI master is changed from 8MHz to 32MHz.
- Change RUI BLE API name from api.ble.customer.xxx to api.ble.custom.xxx because "customer" is typo.
- Force RUI sleep API to go back to sleep on any interrupt until the specified time period passed by.

### Fixed
- Fix erasing user config accidentally by RAK3172 bootloader.
- RUI-377: AT+SLEEP command not working if AT+PRECV=0 is used.
- RUI-372: Missing dtostrf declaration
- RUI-239: [Dev]Refine the checksum mechanism of user configuration for RAK4631
- RUI-371: RAK3172 Battery Measurement without AT+CLIVER command issue

## [3.4.0] - 2022-05-08

### Added
- Support AS923-2/AS923-3/AS923-4.

### Changed
- If AT+PRECV=65534 is typed, the device will be set as RX mode until AT+PRECV=0 is typed.
- If api.lorawan.precv(65534) is called, the device will be set as RX mode until api.lorawan.precv(0) is called.
- If AT+PRECV=65533 is typed, the device will be set as RX mode, but still can do TX without typing AT+PRECV=0.
- If api.lorawan.precv(65533) is called, the device will be set as RX mode, but still can do TX without calling api.lorawan.precv(0).
- Enhance LoRa/LoRaWAN examples.
- Temporarily disable NFC feature for RAK4630.

### Fixed
- Fix Arduino compatibility issues about I2C/SPI/UART/GPIO.
- For RAK4630, fix AT+SLEEP crash issue.
- Fix small input value issue of AT+SLEEP/api.system.sleep.all()/api.system.sleep.cpu()
- RUI-239: [Dev]Refine the checksum mechanism of user configuration for RAK4631
- RUI-334: BLE disconnect issue when over DFU upgrades
- Workaround api.system.battery.get() by looking up a mapping table.

## [3.3.1] - 2022-05-03

### Added

### Changed
- Don't do GPIO de-initialization when sleeping.

### Fixed
- For RAK4631, delay 20 ms before calling pm_init().

## [3.3.0] - 2022-04-29

### Added
- Support NFC when RUI3 SDK is used to customize firmware.
- Add api.ble.stop().
- Add api.system.timer.create()/api.system.timer.start()/api.system.timer.stop().

### Changed

### Fixed
- Bug #838: ble stop, crash

## [3.2.0] - 2022-03-24

### Added
- Support RAK3372.
- Integrate low power UART with AT+SLEEP.
- Support AT+ALIAS
- Support AT command permission change.
- AT+CHS supports EU868.
- Add AT+CW command.
- Add api.system.flash.get()/api.system.flash.set().

### Changed
- Add low power mode for RAK3372.
- Enable LoRa class B for RAK3372.
- Enhance AT+CERTIF command for LCT.
- AT command format change:
  - Don't use space in the output response format
  - No data type in the async event.
  - Use ":" for in/output format and "," to dived different groups or sub-groups
  - command name must show at the begging of every response.
  - remove the redundancy such as space and string, which is not the value.
  - make every response in a single line.
- Rewrite Arduino Interrupt example.
- Change Serial2 to be Serial for RAK3172-E example.
- Remove BLE dependent code from System Powersave example.
- Enhance power-consumption of Smart Farm example.
- For RAK3172, use RAM2 to avoid RAM shortage.
- Remove the wrong design about wakeup source pin.
- Assign WB_IO1 as another wakeup source for System Powersave example.
- Optimize the power consumption of Smart Farm example.
- Update variant.h for RAK4630/RAK3172/RAK3172-SiP
- For RAK4631, Rewrite GPIO driver as event based driver.
- For RAK4631, Add workaround in UDRV Powersave for Smart Farm example.
- Use a compilation flag to turn off Transparent Mode.
- Remove 5s delay in all the examples.
- Remove LED operation in Smart Farm example.
- Refine Smart Farm example to avoid program stuck in some condition.
- For RAK4630, add one more UART console for it.
- For RAK4630, disable NFC by default.
- Remove RF test related RUI API.
- Add AT command max length restriction.
- Simplify the BLE UART example.
- Disable FS related RUI API by default.
- Add example annotation. Indentation modification.

### Fixed
- Bug #663: US915 at+chs join process and return AT_ERROR
- Bug #667: RAK4631 US915/AU915 AT+CHS: Single Channel Mode doesn't work
- Bug #668: [RAK3172] [DailyBuild.44] DUT uplnik in unexpected channels (US915)
- Bug #670: [RAK3172] [DailyBuild.44] DUT response to confirmed downlink messages from unknown NS
- Bug #639: RX2 and RXC abnormal in DR 10~13
- Bug #645: DUT use confirmed uplink message type to response [Fpending = 1] and [Confirmed downlink] events.
- Bug #675: [RAK3172] [DailyBuild.49] After change RX2 frequency by "RXParamSetupReq", downlinks via RXC will be failed.
- Bug #669: [RAK3172] [DailyBuild.44] During processing continuous confirmed downlink, +BC: FAILED (259) message appears
- Fix Smart_Farm example:
    - Fix the wrong usage of api.lorawan.rx2dl.get() because of unit change.
    - Remove BLE dependent code from Smart Farm example, so it can be compiled successfully on RAK3172-E.
- Fix typo and refine RAKUnifiedApi.h.
- Fix RAK3372 I2C can't change frequency.
- Bug #678: [RAK3172][DailyBuild.60] Downlink via RX_B didn't work.
- Bug #512: AnalogRead() return should be 0~1023
- Fix timer bug inside LoRaMacNode
- Bug #680: [RAK3172][DailyBuild.60] In class B, while uplink event engaging into beacon reserved period, DUT console return 'AT_ERROR'.
- Bug #671: [RAK3172] [DailyBuild.44] Can't pass LCTT test cases
- Bug #541: After manually enter DFU Mode, uploading firmware failed
- Bug #681: [RAK3172] [beta 1] API mode的payload長度超過13bytes無法接收 
- Bug #682: [RAK3172] [beta 1] Sometimes, the response handler was not invoked
- For RAK4630, rewrite UDRV/UHAL RTC to support wakeup by LoRa.
- For RAK3172, fix UHAL ADC bug that causes flash cannot be accessed anymore.
- For RAK3172, fix the crash caused by long at command input
- Bug #634: "JOIN FAILED (3)" appeared in continuous join events
- For RAK4630, fix LoRa downlink cannot work anymore if api.system.setup() is called.
- Fix can't print floating point issue for Arduino IDE.
- Fix hard-coding in all examples.
- Fix variant.h according to RAK5005-O page of online document center.
- For RAK4630, fix RX sensitivity issue by powering on antenna switch.
- Bug #622: AT+BFREQ command return unexpected beacon frequency
- For RAK4630, reduce the power consumption by disable LoRa interrupt.
- Fix multi-line input problem.
- Fix the ambiguity caused by the default value of api.system.sleep().
- Fix AT Command buffer size for RAK3172.
- Bug #708: BLE Uart cant modify ADV_NAME
- Bug #713: BLE ADV name have error code
- Bug #714: BLE System crash
- Fix SDK can't be decompressed for Visual Studio.
- Bug #728: [HW:RAK3172] Unexpected power consumption result after remove CH340 from DUT
- Bug #683: AU915 CLASSA OTAA AT+CHS with AT_ERROR issue
- Fix NFC examples can't compile on Arduino IDE
- Bug #727: [HW:RAK3172SIP] Use Serial with Arduino IDE to do FW upgrade (rc1.76 to rc1.76), after re-powering join procedure shows TX timeout message
- Fix Custom ATCMD example's ATCMD permission.
- Bug #700: NFC received lack NLEN(2Bytes) and not type 4/2 tag(t2t/t4t) config?
- Bug #736: [HW:RAK3172][api.system.sleep.setup()] wake-up from powersaving mode, system will stop if there is any input from serial_1.
- Bug #749: [HW:RAK3172][Arduino Example: Arduino_Interrupt] attachInterrupt() fail
- Bug #750: [HW:RAK3172][Arduino Example: Arduino_Interrupt] board crashe when use IO2
- Bug #742: arduino export binary can't run
- Bug #696: Arduino IDE export Hex file no bootload
- Bug #737: [HW:RAK3172][Serial.lock()] we can only lock a serial which is in AT CMD mode, but doxygen does not show it.
- Bug #738: [HW:RAK3172][Serial.lock()] when we lock a serial port, both two serial ports will be locked, and we can unlock both of them from either serial ports
- Bug #745: [HW:RAK4631] System_Powersave crash
- Bug #660: US915 CLASS C with ABP mode when disable gateway frame-counter issue
- Bug #730: [Document error][Serial.readBytesUntil()] Serial.begin(11500, CUSTOM_MODE)
- Bug #731: [Document error][Serial.readBytesUntil()] if (Serial.available > 0) {
- Bug #732: [HW:RAK3172][Serial.readBytesUntil()] Get inputs form win11 teraterm, the API returns without matching either the terminator character or the length.
- Bug #695: RuiV3 release not support NFC
- Fix all the wrong usage of fallback handler in UHAL UART.
- Fix RF test related AT+CW/AT+TRSSI/AT+TTONE/AT+TTX/AT+TRX/AT+TCONF/AT+TTH/AT+TOFF.
- Fix AT+PWORD when password length is less than 8.
- Fix AT+PRECV in API mode: Check network working mode before executing commands.
- Fix unable to exit P2P receiving mode normally.
- Bug #769: [ATCMD]2.16_AT+ALIAS: 'AT+ALIAS=中' will cause 'AT_ERROR' and empty previous value.
- Bug #778: [ATCMD]6.8_AT+LPSEND : out of range input of “<port>” and “<ack>” field, expected return is “AT_PARAM_ERROR”, but get “OK
- Bug #779: [ATCMD]6.9_AT+RETY : out of range input than the upper bound, expected return id “AT_PARAM_ERROR”, but get “AT_ERROR”
- Bug #784: [ATCMD]7.8_AT+RX1DL: The value range of AT+RX1DL (AT+RX2DL) in ATCMD DOC is 1~14 (2~15), however, the LoRaWAN SPEC defines the range = 1~15 (2~16).
- Bug #767: The serial port defaults to CUSTOM_MODE in Arduino, but not in RUI
- Bug #742: arduino export binary can't run
- Bug #696: Arduino IDE export Hex file no bootload
- Bug #747: [HW:RAK3172][Arduino Example: Arduino_Advance_IO] Compile error
- Bug #748: [HW:RAK3172][Arduino Example: Arduino_Digital] Compile error
- Bug #751: [HW:RAK3172][Arduino Example: Arduino_Serial] Serial is not re-enabled after executing Serial.end(). Unable to upload later.
- Bug #752: [HW:RAK3172][Arduino Example: Arduino_Time] delayMicroseconds() cause the board to crash
- Bug #753: [HW:RAK3172][Arduino Example: LoRaWan_P2P] Board crash when run example
- Bug #763: [HW:RAK4631][Arduino Example: System_FS] Com port disappear
- Bug #755: [HW:RAK3172][Arduino Example: System_ATCMD_Permission] API CHANGE_ATCMD_PERM can not use in AT+DEVADDR, AT+NETID, AT+HWID
- Bug #740: LoRa & BLE system crash
- Bug #764: Serial.readString function compile error
- Bug #754: [HW:RAK3172][Arduino Example: System_Serial_Lock] api.system.pword.set(password) is not working
- Bug #775: [ATCMD]4.3_AT+BAUD: Perform 'AT+BAUD=921600', then perform 'ATZ', DUT operate in [Baud Rate 115200] after 'ATZ', however, 'AT+BAUD=?' will return 921600.
- Bug #782: [ATCMD]7.1_AT+ADR: Input 'ATZ' -> wait 10 seconds -> Input 'ADR=? -> wait 200ms -> Input 'AT+ADR=1' will return 'AT_ERROR'
- Fix FSK mode parameter range
- Bug #773: [ATCMD]4.2_AT+PWORD: 'AT+PWORD=中' will cause 'AT_ERROR'.
- Bug #757: P2P AT+PBR & AT+PFDEV AT_PARAM_ERROR and SW stuck issue
- Bug #778: [ATCMD]6.8_AT+LPSEND : out of range input of “<port>” and “<ack>” field, expected return is “AT_PARAM_ERROR”, but get “OK”
- Bug #808: [RAK4631] AT+NWM=0 Fail
- Bug #793: [RAK4631] AT+NWM=0 Fail
- Bug #772: [ATCMD]4.1_AT+LOCK: After lock ATCMD port by 'AT+LOCK=', then re-power DUT, DUT would be in un-locked status.
- Fix using wrong linker script problem for Arduino IDE.
- Fix the hang issue of Smart Farm example that is built by Arduino IDE.
- Fix naming inconsistency of UART_MODE.


## [3.1.0] - 2021-12-20

### Added
- Support Button DFU via UART1 TX pin.

### Changed
- Change AT+MASK behavior from 8 to be 8+1 for US915/AU915.
- Remove power-consuming auto hello mechanism.
- Change the behavior of AT+JN1DL/AT+JN2DL/AT+RX1DL/AT+RX2DL
- Change the default port of transport mode from 130 to 1.
- Change the output format of AT+LTIME.
- Change the output format of LoRaWAN asynchronous event.
- Change AT+DEUI to be AT+DEVEUI. Besides, change AT+DADDR to be AT+DEVADDR.
- Modify AT+SN/AT+FSN/AT+FACTORY design.
- Change transparent mode AT command from AT+PAM to ATD.
- Remove the command name in all the reply content.
- Change the delimiter of AT command from ',' to ':'.
- Modify AT CMD handler of AT+JN1DL/AT+JN2DL/AT+RX1DL/AT+RX2DL/AT+RX2FQ for API mode.

### Fixed
- Bug #637: AT+LSTMULC will cause un-recoverable/un-stoppable print event
- Bug #627: RX2 parameter may not be updated by NS via RXParamSetReq.
- Bug #626: Over-length uplink frame will cause unexpected uplink event
- Bug #621: Join process was stopped while 500kHz channels were all disabled.
- Fix can't wakeup from external wakeup source problem.
- Bug #628: DUT won't actively trigger a uplink event after receiving a confirmed downlink message.
- Fix AT+BUILDTIME
- Bug #512: AnalogRead() return should be 0~1023

## [3.0.0] - 2021-10-25

### Added
- Provide RF test AT commands
    - AT+TRSSI
    - AT+TTONE
    - AT+TTX
    - AT+TRX
    - AT+TCONF
    - AT+TTH
    - AT+TOFF
    - AT+CERTIF
- Support AT+FSN
- Add api.lorawan.precv() for one-time P2P receiving.
- Enhance nRF52840 bootloader: 1. Add ATR command in bootloader to restore factory default. 2. Typing "rui" within 1s after POR can enter DFU mode to recover a dead system.
- Add a mechanism for factory to flash the default keys & IDs.
- BLE Beacon API change:
    - Add api.ble.beacon.ibeacon.power.set(param)
- Add an example for analog API.
- Add an example for LoRaWAN OTAA.
- Add an example for LED breathing.
- Add AT+LPSEND.
- Add api.lorawan.registerRecvCallback()
- Add api.lorawan.registerJoinCallback()
- Add api.lorawan.registerSendCallback()
- Add low power design for AT+AUTOSLEEP.
- Add api.lorawan.dcs.set()
- Add api.lorawan.addmulc()/api.lorawan.rmvmulc()/api.lorawan.lstmulc()
- Support API mode and operating mode switching.
- Support BLE pairing.
- Support NFC
- Support spiffs filesystem.
- Support FSK in LoRaWAN P2P mode.
- Support encryption in LoRaWAN P2P mode.
- Add example code into RUIv3 SDK.
- Add AT+SLEEP command.
- Add AT+RETY command.
- Support Arduino standard library - SPI.
- Add AT+TTH/AT+TTX/AT+TRX/AT+TCONF.
- Support upgrading bootloader by nrfutil.
- Add AT+RETY/AT+LPSEND/AT+ARSSI/AT+LINKCHECK/AT+NWM/AT+PFREQ/AT+PSF/AT+PBW/AT+PCR/AT+PPL/AT+PTP/AT+P2P/AT+PSEND/AT+PRECV/AT+ENCRY/AT+ENCKEY.
- Implement Serial.printf().
- Add AT+CHS/AT+CHE/AT+ARSSI/AT+BGW
- AT+BAUD/AT+HWMODEL/AT+HWID AT commands.
- AT+CHE AT command.
- Support transparent mode.
- Support recovery mode. (Add CLI into RUI v3 bootloader.)
- Add AT+MASK AT command.
- Add AT command AT+RECV.
- Add asynchronous event log for Class A/B/C Downlink.
- Add asynchronous event log for join process.
- Support customized AT command registration.
- Support read/write private user data from/to flash.
- Support LoRaWAN Class B mode for WisBlock RAK4631
- Support LoRaWAN multicast group for WisBlock RAK4631
- Create a unified driver layer (UDRV) for all RAK hardware products
- Support WisBlock Sensor RAK1901/RAK1902/RAK1903/RAK1904/RAK1906/RAK1910
- Compatible with Arduino API
- Add proprietary RUI API for BLE/LoRaWAN
- Enhance power consumption in sleep mode for WisBlock RAK4631
- Upgrade to Nordic SDK 17.0.2 with BLE stack S140 7.2.0
- Support BLE Configuration/Beacon service/UART service/Customized service for WisBlock RAK4631
- Support Arduino IDE/Visual Studio IDE for WisBlock RAK4631
- Support DFU over USB/BLE/UART for WisBlock RAK4631
- Support LoRaWAN Class A/C mode for WisBlock RAK4631
- Support AT commands over USB/BLE/UART


### Changed
- Remove api.ble.setting.advertiseSlow.get()/api.ble.setting.advertiseSlow.set()/api.ble.setting.advertiseFast.get()/api.ble.setting.advertiseFast.set()
- Change the delimiter of AT+ARSSI=? from ',' to ':'
- Rename all the examples
- Change the default setting of AT+DCS to be 1.
- Remove AT+PRECV=? because it is an one-time function, just like AT+SLEEP.
- Update LoRaWan_P2P example
- Update LoRaWan_Class_B example
- Rearch API mode: 1. Remove Src & Dst fields. 2. Change the order of Flag & Frame Type fields. 3. Use the number of set bits as checksum instead of CRC32.
- Rearch example folders.
- Temporarily remove AT+AUTOSLEEP(AT+LPM) command.
- BLE Beacon API change:
    - Change api.ble.beacon.payload(byte array) to api.ble.beacon.ibeacon.uuid.set()
    - Split api.ble.beacon.majorminor(param1, param2) into api.ble.beacon.ibeacon.majo.set(param) & api.ble.beacon.ibeacon.minor.set(param)
- Change the default setting of LoRaWAN confirm mode to be ON.
- Modify BLE UART example to support AT CMD.
- Remove api.system.flash.get() & api.system.flash.set().
- Modify the class RAKBleService to support customized 128-bit BLE UUID.
- Add asynchronous event for AT+CFM.
- Redesign API mode:
    - Always reply return code even if the request is write/execution and result is OK.
    - Don't support AT? anymore because its output is for human, but not for machine.
- Remove '#include "Arduino.h"' in every example.
- Add api.ble.beacon.custom.payload.set() to support customized payload for BLE Beacon.
- Remove sensor examples from SDK
- Remove BLE HID from SDK
- Remove AT+DELBONDS
- Remove api.lorawan.recv()
- Set the default value of AT+CFM to be off.
- Rewrite delay function to avoid wasting MCU time.
- Reduce bootloader size and align the start address of bootloader with legacy RAK4631 bootloader.
- Separate AT+BUILDINFO into 2 AT commands AT+BUILDTIME & AT+REPOINFO.
- Change the design of serial lock AT+LOCK & AT+PWORD.
- Enhance the design of AT+MASK/AT+CHE/AT+CHS to fix coexistence issue.
- Serial.begin() will only supports unsigned integer baudrate.
- Enhance customized AT command registration.
- Change AT+NWKID to AT+NETID because it describes network identifier (NetID) of 3 octets, rather than another network identifier (NwkID) of 7 bits.
- Change the unit of AT+JN1DL/AT+JN2DL/AT+RX1DL/AT+RX2DL from milli-seconds to seconds.
- Add AT_BUSY_ERROR handling for AT+BAND, AT+MASK & ATR.
- Refine LoRaWAN initializaiton flow to reduce flash writing.
- Remove AT+JN2DL= & AT+RX2DL= commands because jn2dl=jn1dl+1 & rx2dl=rx1dl+1.
- Change AT command output format.
- Change the behavior of AT+NJM/AT+SEND/AT+ADR/AT+PNM.
- Rename the AT command AT+RESTORE to ATR.
- Support Arduino library instead of built-in sensor API.


### Fixed
- Bug #529: 868Mhz CLASS B OTAA "at+bfreq" format is not correct
- Bug #606: P2P at+ppl should get AT_PARAM_ERROR instead of AT_ERROR
- Bug #613: [AT COMMAND]Continuous input AT+JOIN will cause AT_ERROR
- Bug #509: Can't begin again after Serial.end()
- Fix AT+LPSEND bugs: 1. wrong return code 2. 512 bytes limitation
- Bug #598: Arduino Application Scenario with SmartFarm issue
- Bug #536: 868Mhz CLASS B OTAA / ABP mode dowlink with pgslot issue
- Fix ClassB multicast group default value
- Bug #453: lorawan nwm.set not working
- Bug #601: RUI API arssi cannot receive value
- Fix AT+BGW can't work issue.
- Bug #584: [API Mode] ATCMD handler's execution command to ATZ, ATDFU, ATR, AT+BOOT, not response frame and no function also
- Bug #571: [API Mode] command ID 32:AT+CLASS set value {BCD:0|1|2} mismatch with get return value {ASCII:A|B|C}
- Bug #583: [API Mode] at+recv=? could not get the latest received data
- Bug #561: 868 OTAA Class C, set appkey during join will get AT_ERROR
- Bug #581: [API Mode] : ATCMD handler for PSF, PCR, PTP command response frame's byte-order of payload length is incorrect
- Bug #582: [API mode] ATCMD Handler AT+PPL=? command ID get value error
- Bug #572: [API Mode] command ID 35:AT+JN1DL and 36:AT+JN2DL input/output length improper, it should be 1 bytes, but not 4 bytes as now
- Add the default multicast group parameters for default B mode
- Bug #570: 868 ABP when gateway set rx2dr to 4, end device can not receive downlink
- Fix min()/max()/yield()
- Fix api.lorawan.addmulc()/api.lorawan.rmvmulc()/api.lorawan.lstmulc()
- Tune the base current for one-time sleep (5uA) & auto sleep (20uA).
- Bug #538: 915Mhz CLASS B OTAA/ABP issue
- Bug #548: P2P Preamble Length setting 2 or 65535 will not receive message
- Bug #549: P2P show receive error when receive second p2p message
- Bug #565: LoRa Auto-Join Failed will cause system hang
- Bug #540: [BLE SCANNER] CONSOLE端顯示廣告有標頭無內容
- Fix the usage of byte array in BLE examples.
- Fix the byte order of AT+DADDR
- Fix AT+AUTOSLEEP can't work when changing its setting from zero to non-zero.
- Fix duplicated LoRaWAN RX data logs.
- Fix AT+CHE/AT+CHS bugs.
- Fix CFlist for AT+CHS when the band is AU915 US915.
- Bug #521: at+cfm=0 send a confirmed uplink
- Bug #508: Multicast can not receive message after change Freq.
- Bug #507: Multicast downlink message print multiple times
- Bug #509: Can't begin again after Serial.end()
- Bug #444: lorawan multicast C++ warpper not implement
- Bug #448: lorawan arssi C++ warpper not implement
- Bug #506: 868Mhz ClASS B description of S0/S1/S2/S3 state
- Bug #527: atr do not reset multicast list
- Create two instance of HardwareSerial that is Serial4 (USB) & Serial6 (BLE)
- Fix api.lorawan.ver().
- Fix api.lorawan.arssi()
- Fix ABP downlink bug.
- Fix AT+LINKCHECK & AT+SNR & AT+RSSI bugs.
- Fix the input range of periodicity.
- Fix the input range of AT+PWORD: Forbid zero length password.
- Fix the maximum number of argument of AT+CHE.
- Fix the input range of AT+SEND to be 2-500 digits.
- Fix write part of AT+DCS
- Fix Arduino Wire library implementation to be compatible with Adafruit libraries.
- Bug #450: lorawan jn1dl, rx1dl RUI-API can input number > 15
- Bug #453: lorawan nwm.set not working
- Bug #452: RUI-API restore default not implement
- Bug #451: api.lorawan.band.get() return value not as same as at+band
- Bug #447: CLIVER, APIVER C++ warpper not implement
- Add parameter sanity check for AT+PGSLOT.
- Fix api.lorawan.ver.get().
- Fix api.lorawan.join() always failure issue.
- Fix the wrong unit of api.lorawan.jn1dl.set()/api.lorawan.jn1dl.get()/api.lorawan.jn2dl.get()/api.lorawan.rx1dl.set()/api.lorawan.rx1dl.get()/api.lorawan.rx2dl.get().
- Enhance Arduino compatibility.
- Fix api.lorawan.ver.get().
- Fix api.lorawan.dr.set().
- Fix the wrong mask value when input AT+MASK=0.
- Fix the typo of api.lorawan.nwskey to be api.lorawan.nwkskey.
- Bug #417: P2P AT+PCR coding rate issue are asymmetric
- Bug #418: P2P part of all descriptions
- Fix AT+BAT always display 0.0 issue.
- Bug #410: JN2DL/RX2DL against the spec
- Bug #411: at+baud is not working properly and return AT_PARAM_ERROR
- Fix DR10 - DR13 issues of LoRaWAN multicast feature.
- Fix Nordic softdevice assertion failed issue.
- Bug #406: at+jn1dl, at+rx2dl input range only 0-15
- Bug #407: at+multicast issue
- Fix hardware watchdog timeout after software reset issue.
- Fix USB enumeration failure issue after calling api.system.sleep.all().
- Bug #402: can not input too many command at same time
- Bug #404: rx1dl should be the same as gateway setting after connected to gateway in OTAA mode
- Bug #403: rx1dl, rx2dl, jn1dl, jn2dl should be ranged in 0-15
- Bug #390: at+class can only setting once ( A ---> C ---x---> A)
- Fix the format of AT+ADDMULC.
- Fix system stability issue caused by ATZ command.
- Fix LoRaWAN multicast downlink message.
- Bug #397: at+rx2fq show at error if input ramdomly
- Bug #393: at+rx2dr error code not as same as document
- Bug #400: at+adr default value not same as document
- Fix AT+RX2DR command.
- Bug #394: at+band default value 4 switch to 5 will show at error
- Bug #395: at+band switch to 2 and then can not switch to other band
- Bug #388: get the random number after setting devaddr (at+daddr)
- Bug #389: at+send error code not as same as document
- Bug #390: at+class can only setting once ( A ---> C ---x---> A)
- Bug #392: AT+DR range should be 0-7 not 0-5
- Bug #391: AT+DR=asdfklaskjdf can accept
- Bug #396: at+txp set 8-15 will show at error in eu868
- Bug #399: device address not as same as gateway in ABP mode
- Bug #397: at+rx2fq show at error if input ramdomly
- Bug #398: command atdfu should rename to at+boot
- Bug #393: at+rx2dr error code not as same as document
- Fix Class A/B/C downlink.
- Bug #377: Arduino IDE verify code will encounter error until open log function
