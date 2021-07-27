# GNSS/IMU Open Data Set for Autonomous Driving
 If you would like to use the data set, please fill out [this form](https://forms.gle/w22wkHnyewGXhJN6A).
 A representative will contact you with the distribution address.<br>
 
 <b>This dataset is only available to users in Japan until it is ready to be used overseas. (2021/3/11)</b><br>
## System Description

<img src="car_2020_image.png" width="512">
<img src="car_image_across.png" width="512">
&emsp;This data was collected in the Odaiba area of Tokyo/Japan.<br>
&emsp;The data includes information on the following sensors.<br>
  
- <b>IMU</b>
  - Model: ADIS16475-2
  - Data rate: 50 Hz
  - Gyro bias Repeatability: 0.7 deg/s
  - Gyro In-Run Bias Stability: 2.5 deg/hr

- <b>Multiple GNSS receivers</b>
  - Model: u-blox F9P
    - Data rate: 5 Hz.
    - GNSS: BeiDou, Galileo, GPS / QZSS
    - GNSS Bands: B2I, E1B/C, L2OF, L2C, B1I, E5b, L1OF, L1C/A
    - Oscillator: TCXO
  - Model: Septentrio Mosaic-x5
    - Data rate: 5 Hz.
    - GNSS: BeiDou, Galileo, GLONASS, GPS / QZSS
    - GNSS Bands: E1C, L1OF, L1C/A, B2I, E5a, L2OF, L2C, L5, E5b
  - Model: Trimble Alloy (Geodetic GNSS receiver)
    - Data rate: 5 Hz.
    - GNSS: BeiDou, Galileo, GLONASS, GPS / QZSS
    - GNSS Bands: L5, B2I, E1B/C, L2OF, L2C, B1I, E5b, L1OF, L1C/A
- <b>Rover GNSS Antenna</b>
  - Model: Trimble Zephyr 3 Rover
- <b>CLAS receiver</b>
  - Model: AQLOC-Light
    - GNSS: Galileo, GPS / QZSS
    - GNSS Bands: L6, L2C, E5b, L1C/A, E1
- <b>Applanix POS LV</b> (high-grade RTK GNSS/INS integrated navigation system)
  - Model: POS LV 220
  - Data rate: 10 Hz.
  - Accuracy (RMS)
    - X, Y position: 0.02 m
    - Z position: 0.05 m
    - Roll and Pitch angle: 0.015 degree
    - True heading: 0.025 degree

## Data Format

- <b>GNSS</b>

  <b>Filename:</b><br>
  &emsp;Obserbation files of "ROVER" are "rover_ublox.obs", "rover_mosaic.obs" and "rover_trimble.obs".<br>
  &emsp;Obserbation file of "BASE" is "base_trimble.obs".<br>
  &emsp;Position of BaseStation was -3961903.8578, 3348993.2385, 3698211.3503 in the ECEF coordinates.<br>
  
  <b>RINEX VERSION:</b>&emsp;RINEX 3.02<br>
  
  <b>Cycle:</b><br>
  |  File Nmae  |  Cycle  |
  | ---- | ---- |
  |  rover_trimble.obs  |  5Hz  |
  |  rover_mosaic.obs  |  5Hz  |
  |  rover_ublox.obs  |  5Hz  |
  |  base_trimble.obs  |  1Hz  |
  
  <b>GNSS Satellites:</b>&emsp;GPS, GLONASS, Galileo, BeiDou, QZSS<br>
  
  &emsp;&emsp;Carriers, pseudoranges, dopplers, SNRs are includeed.(Exception: mosaic-x5 does not include dopplers)<br>
  
  
- <b>IMU</b>

  <b>Filename:</b>&emsp;imu.csv<br>
  <b>Data Description</b><br>
  
  |  Header  |
  | ---- |
  |  GPS TOW(s)  |
  |  GPS Week  |
  |  Angular rate X(rad/s)  |
  |  Angular rate Y(rad/s)  |
  |  Angular rate Z(rad/s)  |
  |  Acceleration X(m/s^2)  |
  |  Acceleration Y(m/s^2)  |
  |  Acceleration Z(m/s^2)  |
  |  Wheel velocity  |

- <b>CLAS</b>

  <b>Filename:</b>&emsp;rover_clas.l6<br>
  <b>Data Description:</b><br>
  &emsp;The L6 data was collected with [AQLOC-light](https://www.mitsubishielectric.co.jp/esg/aqloc/products/light/).<br>
  &emsp;The data is stored in the CLAS packets message.<br>
  
- <b>True Positions and Poses</b>

  <b>Filename:</b>&emsp;reference.csv<br>
  <b>Data Description:</b><br>
  &emsp;The true positions and poses were collected by POSLV220 with POSPAc(Postporcess).<br>
  
  |  Header  |
  | ---- |
  |  GPS TOW(s)  |
  |  GPS Week  |
  |  Latitude(deg)  |
  |  Longitude(deg)  |
  |  Ellipsoid Height(m)  |
  |  ECEF X(m)  |
  |  ECEF Y(m)  |
  |  ECEF Z(m)  |
  |  Roll(deg)  |
  |  Pitch(deg)  |
  |  Heading(deg)  |
  |  Velocity X (m/s)  |
  |  Velocity Y (m/s)  |
  |  Velocity Z (m/s)  |
  |  Acceleration X (m/s^2)  |
  |  Acceleration Y (m/s^2)  |
  |  Acceleration Z (m/s^2)  |
  |  Angular rate X (rad/s)  |
  |  Angular rate Y (rad/s)  |
  |  Angular rate Z (rad/s)  |
  
- <b>True Positions and Poses(Semi-dynamic corrected)</b>

  <b>Filename:</b>&emsp;semi-dynamic_corrected_reference.csv<br>
  <b>Data Description:</b><br>
  &emsp;The true positions and poses were collected by POSLV220 with POSPAc(Postporcess).<br>
  &emsp;The true positions and poses were corrected by Semi-dynamic.<br> 

## Dataset Description

### Data No.1
 <b>Date&emsp;2020/12/17</b><br>
 
  |    |  GPS Week  |  GPS TOW(s)  |
  | ---- | ---- | ---- |
  |  Start  |  2136  |  360000  |
  |  End  |  2136  |  362400  |
 
 <b>Environment:</b>&emsp;Odaiba/Tokyo Urban environment [[map](https://www.google.co.jp/maps/@35.6275683,139.7754449,14.75z?hl=ja)]<br>
 <img src="image_2020_run1.png" width="480">
***
### Data No.2 
 <b>Date&emsp;2020/12/17</b><br>
 
  |    |  GPS Week  |  GPS TOW(s)  |
  | ---- | ---- | ---- |
  |  Start  |  2136  |  368100  |
  |  End  |  2136  |  370440  |
 
 <b>Environment:</b>&emsp;Odaiba/Tokyo Urban environment [[map](https://www.google.co.jp/maps/@35.6275683,139.7754449,14.75z?hl=ja)]<br>
 <img src="image_2020_run2.png" width="480">
