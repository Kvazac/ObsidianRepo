
| Part                   | QTY.  | Price     | Weight, g | Nm. PWR draw | Dmns.                | Details                         | Link                                                                                                                                               | Buy     |
| ---------------------- | ----- | --------- | --------- | ------------ | -------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| Radio                  | 1     | ---       | 9.1       | ///          | 24 x 43 x            | 433 MHz E220 Ebyte \| TX - 200B | [E220](file:///C:/Users/Kvazac/AppData/Local/Temp/MicrosoftEdgeDownloads/382d0d91-50b7-46eb-8849-74c851c59a9a/E220-900T30D_UserManual_EN_v1.0.pdf) | no      |
| Rasberry Pi Zero W     | 1     | 18.5      | 46        | 4 W          | 85 x 56 x 19         | ///                             |                                                                                                                                                    | yes     |
| GY-91                  | 1     | ---       | 1.5       | 3.63 mW      | 20.4 x 14 x 3.5      | 10 DoF                          | ---                                                                                                                                                | no      |
| GY-BMP280              | 2     | ---       | ///       | 3.70 mW      | 11.5 x 15 x 2.6      | Temp & Pressure                 | ---                                                                                                                                                | no      |
| Rolling shutter camera | 1     | 35.80     | 4         | 1.25 W       | 25 x 25 x 11.5       | No IRF, 66 hFoV, 47 vFoV        | [camera HD V3](https://www.anodas.lt/en/raspberry-pi-camera-hd-v3-12mpx-original-raspberry-pi-camera)                                              | yes     |
| L76K GPS               | 1     | ---       | 14        | 0.1 W        | ///                  | ---                             | ---                                                                                                                                                | no      |
| ~~Servo~~              | ~~1~~ | ~~~8.70~~ | ~~9~~     | ~~~2W~~      | ~~32.5 x 12 x 27.3~~ | ~~~0.1 Nm required~~            | ~~[Servo FS90MG](https://www.anodas.lt/en/servo-feetech-fs90mg-micro-en)~~                                                                         | ~~yes~~ |
| Battery                | 2     | 9.5       | 46        | ---          | 65 x 18.3r           | NCR18650B 3000 mAH, 3.6V        | [Akumuliatorius](https://www.anodas.lt/akumuliatorius-18650-li-ion-samsung-inr18650-30q-3000mah)                                                   | yes     |
| 5V regulator           | 1     | 2.9       | 6         | ///          | 30 x 17 x 14         | DC-DC converter MP1584EN        | [DC/DC wide voltage input module7](https://www.anodas.lt/en/dc-dc-wide-voltage-input-module-adjustable-2v-24v-to-5v-28v-2577)                      | yes     |
| Adafruit 4554          | 1     | 27.90     | ///       | ///          | 25.7 x 17.7 x 4.6    | 9 DoF                           | [ICM-20948 9DoF](https://www.anodas.lt/en/icm-20948-9dof-3-axis-accelerometer-gyroscope-and-magnetometer-i2c-spi-qwiic-adafruit-4554)              | yes     |
| 11.2 pF cap            | 2     | 0.10      | 0.87 mg   | ---          | ///                  | 10 pF                           | [Hitano Keraminis kondensatorius A](https://www.lemona.lt/keraminis-kondensatorius-10pf-100v-np0-5.html)                                           | yes     |
| 21 nH inductor         | 2     | ---       | ///       | ---          | 5 x 3r               | 20 nH                           | ///                                                                                                                                                | no      |
____
#### System specification estimate

| Power Cnspt. | Weight | Capacity | Lifetime | Turn Radius | Descent Rate | Wing Aspect Ratio | $$$ |
| ------------ | ------ | -------- | -------- | ----------- | ------------ | ----------------- | --- |
| 7.507 W      | ///    | 6 Ah     | 4.62 h   | 20 m        | 3:10         | 3:1               | /// |
___
#### Parachute dimensions

| Aspect               | Val.:                        |
| -------------------- | ---------------------------- |
| Width (chord)        | 0.18 m                       |
| Lenght (span)        | 0.55 m                       |
| Rigging angle        | $5\degree$                   |
| No. inlet cells      | 7                            |
| Inlet height         | 0.14 m                       |
| Inlet width          | 0.078m                       |
| Travel ratio [V:H]   | 3:10                         |
| Line length          | 0.33 m                       |
| Airfoil shape        | NASA LS(1)-0417              |
| No. suspension lines | 12                           |
| Line diameter        | 0.5-1 mm Dyneema® or Kevlar® |

| HT03-V3-433 Pin | Function           | Raspberry Pi GPIO Pin |
| --------------- | ------------------ | --------------------- |
| VCC             | Power supply (5 V) | 5V Rail               |
| TX              | Transmit Data      | Pin 10 (GPIO15, RXD)  |
| RX              | Receive Data       | Pin 8 (GPIO14, TXD)   |
| CTS             | Clear to Send      | Pin 11 (GPIO17)       |
| RTS             | Request to Send    | Pin 13 (GPIO27)       |
| GND             | Ground             | GND Rail              |

RocketMan

gps

| Function | Pin    |
| -------- | ------ |
| TX       | GPIO23 |
| RX       | GPIO8  |

To Do
- [ ] Mission statement
	- [ ] Flight trajectory control
	- [ ] Terrain mapping 
		- Video or LiDar
- [ ] Team assembly
	- [-] Programing 
	- [-] Electronics engineering & 3D modelling
	- [x] Networking & Funding
		- communicative 
		- knows basics in electronics, programming and physics
		- knows what passes for informative and visually appealing
-   Needs & Wishes
	- Requirements
		- $m = 350g, r = 33mm, h = 115mm$
		- [x] Pressure sensor
		- [x] Temperature sensor
		- [ ] Radio communication
			- Test for 1.5 km
		- [ ] Physical locator (beeper, light or something)
		- [ ] Battery life - min 4h (non primed)
		- [x] Power button
	- The Wants
		- Sensor capabilities
			- [x] Dual pressure & temperature recording
			- [ ] Visual feed
			- [ ] Velocity curve 
				- [ ] Maybe extra accelerometer required - ask niko
			- [ ] High bitrate communication
			- [x] GPS location
				- [ ] GUI - Map
			- [x] 3D orientation representation
				- [ ] Gyroscope
				- [ ] Magnetometer
				- [ ] Accelerometer
			- [ ] Ambient Light based priming
				- [ ] Or physical pin based priming
		- Battery life of 6h (non primed) and at least ant hour (operational)
		- Active / autonomic control
			- [ ] In flight trajectory control based on a radio beacon
				- [ ] Servo actuators to tilt the parachute
			- [ ] Kalman filter
				- [ ] GPS-barometer altitude estimation
				- [ ] Stabilized 3D orientation based on mag, acc, gyro\
		- Error handling mechanism
			- [ ] Data packet loss during radio communication
			- [ ] DIV/0 errors
		- Graphical User Interface
			- [ ] 2D map
			- [ ] Velocity graph
			- [ ] Altitude graph (error margin included)
			- [ ] Temperature graph (error margin included)
			- [ ] 3D Orientation representation 
			- [ ] Distance estimate based on a radio beacon
			- [ ] Data packet loss ratio
			- [ ] Sat State report {No con > Idle > Primed > In Operation}
				- Include {Landed} state > initiate physical locators
	- Parts list
		- [ ] 10/9 DoF sensor array
		- [ ] Hbee radio module

Laba, prieš kurį laiką aš ir mano draugė Viltė Sapožnikovaitė turėjome susitikimą su Donatu Miklušiu, tuo metu labai įdomiai pasikalbėjome ir išgirdome įdomių istorijų apie jo patirtį su ESA. 

Taip išėjo, kad pavyko prieš porą savaičių nuvykti iki ESTEC per atvirų durų dieną ir taip pat truputi atnaujinti kontaktus ir mūsų ESA maniją. Ta nata susimastėme, kad norėtume išgirsti ir jūsų istoriją: kaip atrodė jūsų kelias į ESA, kas jus motyvavo, ką tokie studentai kaip mes galėtume padaryti ir t.t. Todėl mąstėme galbūt kada turėtumėte laiko skambučiui per Zoom, kad galėtume gyvai pasikalbėti?