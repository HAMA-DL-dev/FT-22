## FOURTOR,  E-Formula Student Team at Hanyang Univ ERICA campus
<p align="center">
<img src="https://github.com/HAMA-DL-dev/FT-22/blob/64bb92614b4bfcdb47568e86b827a70eea782b26/assets/2022%20team%20FOURTOR.jpg" width="640" height="458">
</p>

This repository describes SW and motor system of E-formula of FOURTOR, FT-22 <br>
The repo contains code, image and configuration file related to above <br>
For more description, you can visit our team page  <br>

## Link
- [Team page](https://cafe.naver.com/fourinwheelmotor)
- [Instagram](https://www.instagram.com/fourtor_hanyang_erica/)
- [Notion for SW team](https://www.notion.so/ECU-for-2022-KSAE-58f490e7761d48bcbadd27ff839be4b7)

## System

<p align="center">
<img src="https://github.com/HAMA-DL-dev/FT-22/blob/e5e4e89bdf81dd31018656f4f53cc7d268217e8e/assets/system%20diagram.jpg" width="585" height="960">
</p>

### HW 
- motor : ME1302 PMAC motor
- motor controller : SEVCON GEN4 72V/80V 720A
- microcontroller : STM32F4 NUCLEO-F446RE, Arduino Uno
- ETC : MCP2515, NTC, ST-22

### SW
``` 
├── STM32F4/
|   ├── CAN
|   |   ├── CANopen
|   |   └── CANSPI
|   ├── UART
|   └── I2C
└── Arduino/
    ├── BMS (main.c)
    ├── Linduino
    ├── LT_I2C
    ├── LT_SPI
    ├── LTC681x
    └── LTC6811
    
```
## BMS : Battery Management System

<img src="https://github.com/HAMA-DL-dev/FT-22/blob/e5e4e89bdf81dd31018656f4f53cc7d268217e8e/assets/voltage%20output.jpg" width="480" height="408">

BMS is essential component of EV <br>
It monitors state of charge (SOC) but also detect temperature balance of cell <br>
If BMS detects any abnormality, this system shutdowns all of electrical system of vehicle <br>
The conditions under which whole electrical systme is cut off are as follows 
```
1. A voltage at serial line of battery cell has over volatage or under volatage of a cell based on its spec sheet
2. Temperature exceeds 60C° or under -20 C°
3. Over current at parallel line of battery cell
```

## DVT software 
![DVT software](https://github.com/HAMA-DL-dev/FT-22/blob/e5e4e89bdf81dd31018656f4f53cc7d268217e8e/assets/DVT%20software.jpg)

Our driving system consists of motor and motor controller <br>
The manufacturer of controller provides configuration SW tool for SevconGen4 <br>
We design a control system of motor using this
