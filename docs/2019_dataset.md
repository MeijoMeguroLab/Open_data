## 正式な記載内容は[英語版](https://github.com/MeijoMeguroLab/open_data/blob/main/docs/2019_dataset.md)を確認してください.

# 自律走行のためのGNSS/IMUオープンデータセット
 データセットのご利用をご希望の方は、[[こちら](https://forms.gle/w22wkHnyewGXhJN6A)]
 のフォームにご記入ください。担当者より配布先をご連絡させていただきます。
## システム/機材構成の説明

<img src="car_2019_image.png" width="512">
<img src="car_image_across.png" width="512">
&emsp;東京でのデータ収集のためのプラットフォームはトヨタのシエンタ(Sienta)です。<br>
&emsp;このプラットフォームには以下のセンサーが搭載されています。<br>

- <b>3D LiDAR</b>
  - Model: Velodyne HDL-32E
  - Vertical Field of view (FOV): +10~-30 degrees.
  - Horizontal Field of view (FOV): 360 degrees.
  - Ranging: max 80~100 meters.
  - Data rate: 10 Hz.
  - Channels: 32
  - Accuracy: ± 2 cm accuracy
  
- <b>IMU</b>
  - Model: ADIS16475-2
  - Data rate: 50 Hz
  - Gyro bias Repeatability: 0.7 deg/s
  - Gyro In-Run Bias Stability: 2.5 deg/hr

- <b>Multiple GNSS receivers</b>
  - Model: u-blox F9P
    - Data rate: 5 Hz.
    - GNSS: BeiDou, Galileo, GPS / QZSS
    - GNSS Bands: L2OF, L2C, E1B/C, B2I, E5b, L1C/A, L1OF, B1I
    - Oscillator: TCXO
  - Model: Trimble Alloy (Geodetic GNSS receiver)
    - Data rate: 10 Hz.
    - GNSS: BeiDou, Galileo, GLONASS, GPS / QZSS
    - GNSS Bands: L2OF, L2C, L5, E1B/C, B2I, E5b, L1C/A, L1OF, B1I
- <b>Rover GNSS Antenna</b>
  - Model: AT1675-540 GNSS Antenna (AeroAntenna Technology, Inc.)


- <b>Applanix POS LV</b> (high-grade RTK GNSS/INS integrated navigation system)
  - Model: POS LV 220
  - Data rate: 10 Hz.
  - Accuracy (RMS)
    - X, Y position: 0.02 m
    - Z position: 0.05 m
    - Roll and Pitch angle: 0.015 degree
    - True heading: 0.025 degree

## データフォーマット

- <b>GNSS</b>

  <b>ファイル名:</b><br>
  &emsp;移動局の観測ファイルは "rover_ublox.obs" と "rover_trimble.obs" になります.<br>
  &emsp;基準局の観測ファイルは "base_trimble.obs" になります.<br>
  &emsp;BaseStationの位置は、ECEF座標で -3961904.9530, 3348993.7578, 3698211.7553 になります.<br>
  
  <b>RINEX VERSION:</b>&emsp;RINEX 3.02<br>
  
  <b>取得周期:</b><br>
  |  ファイル名  |  周期  |
  | ---- | ---- |
  |  rover_trimble.obs  |  10Hz  |
  |  rover_ublox.obs  |  5Hz  |
  |  base_trimble.obs  |  1Hz  |
  
  <b>使用衛星:</b>&emsp;GPS, GLONASS, Galileo, BeiDou, QZSS<br>
  
  &emsp;&emsp;搬送波位相, 議事距離, ドップラー, SNR情報を含みます.<br>
  
- <b>IMU</b>

  <b> ファイル名:</b>&emsp;imu.csv<br>
  <b>データ説明</b><br>
  
  |  ヘッダー  |
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

- <b>LiDAR</b>

  <b>ファイル名:</b>&emsp;lidar.bag<br>
  <b>データ説明:</b><br>
  &emsp;LiDARのデータはVelodyne_driverを元に収集しています。<br>
  &emsp;Velodyne HDL-32Eを使用しました。データは velodyne_packets メッセージに保存されています。<br>
  
- <b>リファレンス</b>

  <b>ファイル名:</b>&emsp;reference.csv<br>
  <b>データ説明:</b><br>
  &emsp;位置と姿勢の真値は、POSLV220でPOSPAc(後処理)を用いて収集しました.<br>
  
  |  ヘッダー  |
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

## データセット説明

### 走行データ1
 <b>日付&emsp;2019/11/02</b><br>
 
  |    |  GPS Week  |  GPS TOW(s)  |
  | ---- | ---- | ---- |
  |  開始  |  2077  |  545460  |
  |  終了  |  2077  |  548370  |
 
 <b>環境:</b>&emsp;お台場 Sub-Urban environment [[map](https://www.google.co.jp/maps/@35.6275683,139.7754449,14.75z?hl=ja)]<br>
 <img src="image_run1.png" width="480">
***
### 走行データ2 
 <b>日付&emsp;2019/11/02</b><br>
 
  |    |  GPS Week  |  GPS TOW(s)  |
  | ---- | ---- | ---- |
  |  開始  |  2077  |  548488  |
  |  終了  |  2077  |  551002  |
 
 <b>環境:</b>&emsp;お台場 Sub-Urban environment  [[map](https://www.google.co.jp/maps/@35.6275683,139.7754449,14.75z?hl=ja)]<br>
 <img src="image_run2.png" width="480">
***
### 走行データ3
 <b>日付&emsp;2019/11/02</b><br>
 
  |    |  GPS Week  |  GPS TOW(s)  |
  | ---- | ---- | ---- |
  |  開始  |  2077  |  551105  |
  |  終了  |  2077  |  552679  |

 <b>環境:</b>&emsp;お台場 Sub-Urban environment [[map](https://www.google.co.jp/maps/@35.6343741,139.7892038,15.75z?hl=ja)]<br>
 <img src="image_run3.png" width="480">
