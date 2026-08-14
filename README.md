# Mạch diều khiển động cơ DC MKE-M17 L9110 I2C Motor Driver Module

## Giới thiệu

## Giới thiệu

**Mạch điều khiển động cơ DC MKE-M17 L9110 I2C Motor Driver Module** là module điều khiển **2 động cơ DC công suất thấp 0.8A/kênh** như **TT Motor, N20 Motor** thông qua giao tiếp **I2C**. Module tích hợp **vi điều khiển 32-bit ARM Cortex-M0+** đảm nhiệm việc tạo PWM, điều khiển chiều quay, quản lý thời gian và giám sát điện áp nguồn motor, giúp vi điều khiển chính như **Arduino, ESP32, ESP8266, Raspberry Pi hoặc STM32** dễ dàng điều khiển động cơ chỉ thông qua hai tín hiệu **SDA và SCL**. 

Module sử dụng **2 IC L9110** làm mạch cầu H, hỗ trợ điều khiển độc lập hai động cơ với các chức năng:

* Điều khiển chiều quay thuận/ngược.
* Điều chỉnh tốc độ bằng PWM.
* Dừng từng động cơ hoặc cả hai động cơ.
* Điều khiển thời gian chạy của động cơ.
* Đọc điện áp nguồn motor.
* Thay đổi địa chỉ I2C.
* Cấu hình tần số PWM.
* Kết nối nhiều module trên cùng bus I2C.

**Mạch điều khiển động cơ DC MKE-M17 L9110 I2C Motor Driver Module** phù hợp cho các ứng dụng như **robot 2WD/4WD, xe điều khiển từ xa, robot dò line, robot tránh vật cản, xe thông minh, robot tự hành và các mô hình STEM**. Module hỗ trợ **logic 3.3–5VDC**, điện áp motor **6–9VDC**, phù hợp với nhiều nền tảng điều khiển phổ biến. 

> **Lưu ý:** MKE-M17 có dòng liên tục **0.8A/kênh** và dòng đỉnh **1.5A/kênh**, phù hợp nhất với các động cơ DC công suất thấp.

## Thông số kỹ thuật

| Thông số                         | Giá trị                                  |
| -------------------------------- | ---------------------------------------- |
| **Product SKU**                  | `MKE-M17`                                |
| **Tên sản phẩm**                 | L9110 I2C Motor Driver Module            |
| **Driver cầu H**                 | 2 x L9110                                |
| **Vi điều khiển tích hợp**       | 32-bit ARM Cortex-M0+                    |
| **Điện áp hoạt đông**            | 5.0VDC                                   |
| **Điện áp cấp cho motor Vin**    | 6.0V ~ 9.0VDC                            |
| **Dòng liên tục / kênh**         | 0.8A                                     |
| **Dòng đỉnh / kênh**             | 1.5A                                     |
| **Tần số PWM**                   | 500Hz ~ 2000Hz                           |
| **Số kênh motor**                | 2                                        |
| **Giao tiếp điều khiển**         | I2C                                      |
| **Địa chỉ I2C mặc định**         | `0x40`                                   |
| **Khoảng địa chỉ I2C**           | `1 – 126`                                |
| **Cổng BLE**                     | Dùng kết nối Module Bluetooth điều khiển qua [APP Dabble](https://thestempedia.com/product/dabble/)  |
| **Module Bluetooth tương thích** | [MKE-M15-BLUETOOTH-UART-MODULE ](https://github.com/makereduvn/MKE-M15-BLUETOOTH-UART-MODULE)           |
| **Điện trở kéo lên I2C**         | 10kΩ trên SDA và SCL                     |
| **Bảo vệ nguồn motor**           | Diode chống ngược cực SS34               |
| **Ngõ ra Motor A**               | MA1, MA2                                 |
| **Ngõ ra Motor B**               | MB1, MB2                                 |
| **Điều khiển PWM**               | 0 – 255                                  |
| **Ứng dụng khuyến nghị**         | Xe 2WD/4WD mini, động cơ TT Motor, động cơ N20 |

## Giao diện phần cứng và chân kết nối

### Cổng I2C 
| Chân  | Chức năng                          |
| ----- | ---------------------------------- |
| `GND` | Nguồn âm 0VDC                      |
| `5V` | Nguồn dương 5VDC                    |
| `SDA` | I2C Data                           |
| `SCL` | I2C Clock                          |

Chân `SDA` và `SCL` được tích hợp điện trở kéo lên **10kΩ**.

### Cổng BLE
| Chân  | Chức năng |
| ----- | --------- |
| `GND` | Nguồn âm 0VDC     |
| `5V` | Nguồn dương 5VDC   |
| `RX`  | UART RX   |
| `TX`  | UART TX   |

Cổng này được thiết kế để kết nối với **[MKE-M15-BLUETOOTH-UART-MODULE ](https://github.com/makereduvn/MKE-M15-BLUETOOTH-UART-MODULE)** điều khiển qua [APP Dabble](https://thestempedia.com/product/dabble/).

### Ngõ vào nguồn động cơ
| Chân  | Chức năng                 |
| ----- | ------------------------- |
| `6-9V` | Nguồn dương motor, 6–9VDC|
| `GND` | Nguồn âm 0VDC             |

Đầu vào nguồn được bảo vệ chống đấu ngược cực bằng diode **SS34**.

### Ngõ ra nguồn động cơ
| Chân  | Chức năng |
| ----- | --------- |
| `MA1` | Motor A   |
| `MA2` | Motor A   |
| `MB1` | Motor B   |
| `MB2` | Motor B   |

## Jumper J1
Jumper J1 dùng để lựa chọn nguồn Module MKE-M17.
**J1 = OFF — Mặc định**
Nguồn cấp cho Module MKE-M17 hoạt động độc lập với nguồn cấp cho động cơ, khi đó chân 5V trên cổng I2C/BLE sẽ là chân nguồn Input 5VDC.
**#J1 = ON**
Nguồn cấp cho Module MKE-M17 hoạt động sử dụng nguồn cấp cho động cơ, khi đó chân 5V trên cổng I2C/BLE sẽ là chân nguồn Output 5VDC / Max 700mA.

## Nút nhấn chức năng SW1
MKE-M17 tích hợp một nút nhấn đa chức năng.

### Kiểm tra motor
Nhấn nút **1 lần** để chạy chương trình tự kiểm tra:
1. Motor A quay thuận.
2. Motor A quay ngược.
3. Motor B quay thuận.
4. Motor B quay ngược.

### Khôi phục cài đặt gốc
Nhấn và giữ nút khoảng **4 giây**.
Module sẽ:
* Xóa cấu hình trong EEPROM.
* Khôi phục địa chỉ I2C về mặc định `0x40`.

## Sơ đồ kết nối với Arduino Uno

Khi sử dụng Arduino Uno, đặt **J1 = OFF**.

| Arduino Uno | MKE-M17     | Chức năng          |
| ----------- | ----------- | ------------------ |
| `5V`        | `VCC`       | Nguồn logic        |
| `GND`       | `GND`       | Mass               |
| `A4`        | `SDA`       | I2C Data           |
| `A5`        | `SCL`       | I2C Clock          |
| Battery `+` | `Vin`       | Nguồn motor 6–9VDC |
| Battery `-` | `GND`       | Mass nguồn motor   |
| DC Motor 1  | `MA1 / MA2` | Motor A            |
| DC Motor 2  | `MB1 / MB2` | Motor B            |

Sơ đồ kết nối này được mô tả trong tài liệu MakerEdu cho cấu hình Arduino Uno + MKE-M17/MKE-M18.

## Hướng dẫn cài đặt thư viện Arduino

Có hai phương pháp cài đặt thư viện điều khiển MKE-M17.

### Phương pháp 1: Sử dụng thư viện MKE_ONE — Khuyến nghị

1. Mở **Arduino IDE**.
2. Chọn:

```text
Tools → Manage Libraries...
```

3. Tìm:

```text
MKE_ONE
```

4. Nhấn **Install**.
5. Khi Arduino IDE yêu cầu cài đặt các thư viện phụ thuộc, chọn **Install All**.
6. Arduino IDE sẽ tự động cài đặt thư viện:

```text
MakerEdu_I2C_MotorDriver
```

Sau khi cài đặt, chương trình mẫu MKE-M17 có thể được mở tại:

```text
File
→ Examples
→ MKE_ONE
→ Module
→ MKE_M17_I2C_Motor_L9110
```

### Phương pháp 2: Cài đặt trực tiếp Driver Library

Trong Arduino IDE:

```text
Tools
→ Manage Libraries...
```

Tìm:

```text
MakerEdu I2C Motor Driver
```

Sau đó chọn **Install**.

## Lập trình Arduino

### Khởi tạo thư viện

```cpp
#include <Wire.h>
#include <MKE_I2C_MotorDriver.h>

MKE_M17_MotorDriver motorDriver;

void setup() {
  Serial.begin(9600);

  // Khởi tạo I2C Master
  Wire.begin();

  // Khởi tạo MKE-M17 tại địa chỉ mặc định 0x40
  motorDriver.begin();
}

void loop() {
  // Motor A quay thuận với tốc độ 200/255
  motorDriver.motorA_CW(200);

  delay(1000);

  // Dừng tất cả motor
  motorDriver.stopAll();

  delay(1000);
}
```

> **Quan trọng:** `MKE_I2C_MotorDriver` không tự gọi `Wire.begin()` bên trong thư viện. Luôn gọi `Wire.begin()` trong `setup()` trước khi gọi `motorDriver.begin()`.

## C++ API

### Khởi tạo module

```cpp
motorDriver.begin();
```

Hoặc chỉ định địa chỉ I2C:

```cpp
motorDriver.begin(0x40);
```

Có thể chỉ định bus I2C khác:

```cpp
motorDriver.begin(0x40, Wire);
```

### Bảng API

| Hàm                              | Tham số                       | Mô tả                              |
| -------------------------------- | ----------------------------- | ---------------------------------- |
| `begin(address, wire)`           | `address`, `wire`             | Cấu hình địa chỉ I2C và bus I2C    |
| `motorA_CW(speed, duration_ms)`  | `speed: 0–255`, `duration_ms` | Motor A quay thuận                 |
| `motorA_CCW(speed, duration_ms)` | `speed: 0–255`, `duration_ms` | Motor A quay ngược                 |
| `stopMotorA()`                   | -                             | Dừng Motor A ngay lập tức          |
| `motorB_CW(speed, duration_ms)`  | `speed: 0–255`, `duration_ms` | Motor B quay thuận                 |
| `motorB_CCW(speed, duration_ms)` | `speed: 0–255`, `duration_ms` | Motor B quay ngược                 |
| `stopMotorB()`                   | -                             | Dừng Motor B ngay lập tức          |
| `stopAll()`                      | -                             | Dừng đồng thời Motor A và B        |
| `getVin()`                       | -                             | Đọc điện áp nguồn motor, đơn vị mV |
| `setAddress(newAddress)`         | `1–126`                       | Thay đổi và lưu địa chỉ I2C        |
| `getAddress()`                   | -                             | Đọc địa chỉ I2C hiện tại           |
| `getModuleId()`                  | -                             | Đọc mã loại module                 |
| `getFirmwareVersion()`           | -                             | Đọc phiên bản/ngày build firmware  |
| `setPwmFrequency(freq_hz)`       | `freq_hz`                     | Thiết lập tần số PWM               |
| `setPwmMA1(val)`                 | `0–255`                       | Điều khiển PWM trực tiếp MA1       |
| `setPwmMA2(val)`                 | `0–255`                       | Điều khiển PWM trực tiếp MA2       |
| `setPwmMB1(val)`                 | `0–255`                       | Điều khiển PWM trực tiếp MB1       |
| `setPwmMB2(val)`                 | `0–255`                       | Điều khiển PWM trực tiếp MB2       |

Tài liệu định nghĩa tốc độ motor theo thang **0–255**; tham số `duration_ms = 0` cho phép motor chạy liên tục, còn giá trị lớn hơn 0 sẽ tự động dừng sau thời gian tương ứng.

## Ví dụ 1: Điều khiển tốc độ và chiều quay

```cpp
#include <Wire.h>
#include <MKE_I2C_MotorDriver.h>

MKE_I2C_MotorDriver motorDriver;

void setup() {
  Serial.begin(9600);

  Wire.begin();
  motorDriver.begin();
}

void loop() {

  // Tăng dần tốc độ Motor A theo chiều thuận
  for (int speed = 0; speed <= 255; speed += 25) {
    motorDriver.motorA_CW(speed);
    delay(100);
  }

  delay(1000);

  // Dừng Motor A
  motorDriver.stopMotorA();

  delay(500);

  // Đảo chiều Motor A
  motorDriver.motorA_CCW(200);

  delay(1500);

  // Dừng tất cả motor
  motorDriver.stopAll();

  delay(2000);
}
```

## Ví dụ 2: Chạy motor theo thời gian định trước

MKE-M17 hỗ trợ lệnh điều khiển motor có thời gian chạy, giúp Master có thể gửi lệnh chạy motor mà không cần duy trì việc điều khiển PWM liên tục.

```cpp
#include <Wire.h>
#include <MKE_I2C_MotorDriver.h>

MKE_I2C_MotorDriver motorDriver;

void setup() {
  Serial.begin(9600);

  Wire.begin();
  motorDriver.begin();
}

void loop() {

  // Motor A chạy thuận ở tốc độ 180 trong 2.5 giây
  motorDriver.motorA_CW(180, 2500);

  // Motor B chạy thuận ở tốc độ 180 trong 2.5 giây
  motorDriver.motorB_CW(180, 2500);

  delay(4000);

  motorDriver.stopAll();

  delay(3000);
}
```

Tài liệu MakerEdu cũng mô tả cơ chế **PID Watchdog Safety**, trong đó Master có thể gửi lệnh định kỳ; nếu quá thời gian timeout mà không nhận được lệnh tiếp theo, motor sẽ được dừng an toàn.

## Ví dụ 3: Đọc điện áp pin

MKE-M17 cho phép đọc điện áp nguồn motor thông qua hàm `getVin()` với đơn vị **mV**.

```cpp
#include <Wire.h>
#include <MKE_I2C_MotorDriver.h>

MKE_I2C_MotorDriver motorDriver;

void setup() {
  Serial.begin(9600);

  Wire.begin();
  motorDriver.begin();
}

void loop() {

  uint32_t vin_mV = motorDriver.getVin();
  float vin_V = vin_mV / 1000.0;

  Serial.print(F("Battery Voltage: "));
  Serial.print(vin_V, 2);
  Serial.println(F(" V"));

  // Ngưỡng cảnh báo cho bộ pin 2S Li-ion
  // Dừng motor khi điện áp thấp hơn 6.6V
  if (vin_mV > 0 && vin_mV < 6600) {

    Serial.println(
      F(">>> WARNING: Low Battery! Stopping motors. <<<")
    );

    motorDriver.stopAll();

    while (true) {
      delay(1000);
    }
  }

  delay(1000);
}
```

## Sử dụng nhiều MKE-M17 trên cùng bus I2C

Mỗi MKE-M17 có thể được cấu hình một địa chỉ I2C khác nhau, cho phép nhiều driver hoạt động trên cùng một bus.

Ví dụ sử dụng hai MKE-M17:

```cpp
#include <Wire.h>
#include <MKE_I2C_MotorDriver.h>

MKE_M17_MotorDriver frontWheels;
MKE_M17_MotorDriver rearWheels;

void setup() {

  Wire.begin();

  // Module phía trước
  frontWheels.begin(0x40);

  // Module phía sau
  rearWheels.begin(0x41);

  // Điều khiển 4 động cơ chạy tiến
  frontWheels.motorA_CW(200);
  frontWheels.motorB_CW(200);

  rearWheels.motorA_CW(200);
  rearWheels.motorB_CW(200);
}

void loop() {
}
```

Cách cấu hình này cho phép xây dựng hệ thống **4WD sử dụng 2 module MKE-M17**, trong đó mỗi module điều khiển hai động cơ.

## Ví dụ 4: Robot Mecanum 4 bánh

Hai module MKE-M17 có thể được sử dụng để điều khiển robot Mecanum 4 bánh.

```cpp
#include <Wire.h>
#include <MKE_I2C_MotorDriver.h>

MKE_I2C_MotorDriver driverFront;
MKE_I2C_MotorDriver driverRear;

// FL = Front Left
// FR = Front Right
// RL = Rear Left
// RR = Rear Right

void set4Wheels(int fl, int fr, int rl, int rr) {

  (fl >= 0)
    ? driverFront.motorA_CW(fl)
    : driverFront.motorA_CCW(-fl);

  (fr >= 0)
    ? driverFront.motorB_CW(fr)
    : driverFront.motorB_CCW(-fr);

  (rl >= 0)
    ? driverRear.motorA_CW(rl)
    : driverRear.motorA_CCW(-rl);

  (rr >= 0)
    ? driverRear.motorB_CW(rr)
    : driverRear.motorB_CCW(-rr);
}

void setup() {

  Wire.begin();

  driverFront.begin(0x40);
  driverRear.begin(0x41);
}

void loop() {

  // 1. Di chuyển tiến
  set4Wheels(200, 200, 200, 200);
  delay(2000);

  // 2. Di chuyển ngang sang trái
  set4Wheels(-200, 200, 200, -200);
  delay(2000);

  // 3. Di chuyển ngang sang phải
  set4Wheels(200, -200, -200, 200);
  delay(2000);

  // 4. Xoay trái
  set4Wheels(-180, 180, -180, 180);
  delay(1500);

  // 5. Dừng
  set4Wheels(0, 0, 0, 0);
  delay(2000);
}
```

Đây là cấu hình được tài liệu MakerEdu sử dụng cho robot Mecanum 4WD với hai driver, mỗi driver điều khiển hai bánh.

## Lập trình với BBC micro:bit

MKE-M17 hỗ trợ **BBC micro:bit** thông qua lập trình block trên **Microsoft MakeCode**.

### Cài đặt Extension

1. Truy cập:

```text
https://makecode.microbit.org
```

2. Tạo **New Project**.
3. Chọn:

```text
Settings → Extensions
```

4. Nhập URL Extension:

```text
https://github.com/Khuuxuanngoc/makeCode_MKE_I2C_Motor_Driver_extension_test
```

5. Nhấn **Enter** để thêm Extension.

Extension hỗ trợ các bài học về:

* Điều khiển motor DC cơ bản.
* Chạy motor theo thời gian.
* Đọc điện áp pin và cảnh báo điện áp thấp.
* Lập trình robot 2WD.
* Lập trình robot Mecanum 4WD sử dụng 2 driver.

## Giao tiếp I2C cấp thấp

MKE-M17 có thể được điều khiển trực tiếp từ các nền tảng không sử dụng Arduino, chẳng hạn:

* ESP-IDF.
* Raspberry Pi Python.
* STM32 HAL.

### Gói dữ liệu Write

Mỗi gói lệnh có độ dài **6 byte**:

```text
[Region] [ModeID] [Payload MSB] [Payload Byte 2] [Payload Byte 1] [Payload LSB]
```

Trong đó:

```text
Region = 0x05
```

Dữ liệu sử dụng **Big-Endian**, byte có trọng số lớn nhất được truyền trước.

Đối với lệnh thông thường:

```text
payload = speed
```

Đối với lệnh chạy theo thời gian:

```text
payload = ((uint32_t)duration_ms << 16) | speed
```

### Trình tự đọc dữ liệu

1. Gửi gói Write 6 byte với ModeID cần đọc và `payload = 0`.
2. Chờ ít nhất **200µs**.
3. Thực hiện I2C Read với độ dài **4 byte**.
4. Ghép 4 byte nhận được thành số nguyên 32-bit theo Big-Endian.

### Bảng lệnh I2C

| ModeID | Command          | Type  | Payload                        | Chức năng               |
| -----: | ---------------- | ----- | ------------------------------ | ----------------------- |
|  `106` | `Set_MA_CW`      | Write | `(duration_ms << 16) \| speed` | Motor A quay thuận      |
|  `107` | `Set_MA_CCW`     | Write | `(duration_ms << 16) \| speed` | Motor A quay ngược      |
|  `110` | `Set_MA_STOP`    | Write | `0`                            | Dừng Motor A            |
|  `108` | `Set_MB_CW`      | Write | `(duration_ms << 16) \| speed` | Motor B quay thuận      |
|  `109` | `Set_MB_CCW`     | Write | `(duration_ms << 16) \| speed` | Motor B quay ngược      |
|  `111` | `Set_MB_STOP`    | Write | `0`                            | Dừng Motor B            |
|  `112` | `Get_VIN`        | Read  | `uint32_t (mV)`                | Đọc điện áp nguồn motor |
|  `104` | `Set_MOTOR_FREQ` | Write | `frequency_hz`                 | Thiết lập tần số PWM    |
|    `1` | `SetAddress`     | Write | `1–126`                        | Thay đổi địa chỉ I2C    |
|   `10` | `GetAddress`     | Read  | `uint8_t`                      | Đọc địa chỉ I2C         |
|    `2` | `Get_ID_Module`  | Read  | `3`                            | Đọc Device ID           |
|    `4` | `Get_FW_Version` | Read  | `uint32_t`                     | Đọc phiên bản firmware  |

Các ModeID và cấu trúc payload trên được lấy từ bảng **User Command Map** trong tài liệu kỹ thuật MKE-M17/MKE-M18.

## Điều khiển Bluetooth với MKE-M15 và Dabble

MKE-M17 có thể kết hợp với **MKE-M15 Bluetooth UART Module** để điều khiển robot thông qua ứng dụng **Dabble** trên smartphone.

### Kết nối phần cứng

Cắm MKE-M15 vào cổng BLE/UART:

```text
VCC
GND
TX
RX
```

Sau đó kết nối smartphone với MKE-M15 thông qua Bluetooth và mở module **Gamepad** trong Dabble.

### Điều khiển bằng Dabble Gamepad

| Điều khiển        | Chức năng                             |
| ----------------- | ------------------------------------- |
| `START`           | Kích hoạt điều khiển                  |
| `SELECT`          | Tạm khóa điều khiển motor             |
| `SQUARE`          | Phanh / Emergency Stop                |
| `UP`              | Hai motor chạy tiến                   |
| `DOWN`            | Hai motor chạy lùi                    |
| `LEFT`            | Rẽ trái                               |
| `RIGHT`           | Rẽ phải                               |
| `Analog Joystick` | Điều khiển tốc độ và hướng theo tỷ lệ |

Joystick analog sử dụng trục X/Y trong khoảng `-7.0` đến `+7.0`.

### Failsafe khi mất Bluetooth

Nếu:

* Mất tín hiệu Bluetooth.
* Module nằm ngoài phạm vi kết nối.
* Ứng dụng Dabble bị đóng.

MCU tích hợp trên MKE-M17 sẽ tự động **ngắt tín hiệu PWM và dừng toàn bộ motor**.

## Lưu ý khi sử dụng

> **⚠️ Quan trọng — Khởi tạo I2C**

Luôn gọi:

```cpp
Wire.begin();
```

trong `setup()` trước khi sử dụng:

```cpp
motorDriver.begin();
```

Có thể sử dụng:

```cpp
Wire.begin(SDA, SCL);
```

để cấu hình chân I2C tùy chỉnh hoặc:

```cpp
Wire.setClock(400000);
```

để sử dụng tốc độ bus I2C cao hơn khi phần cứng hỗ trợ.

> **⚠️ Cảnh báo — Nguồn motor**

Đối với **MKE-M17 (L9110)**, điện áp cấp cho motor phải nằm trong khoảng:

```text
6V – 9V DC
```

Không cấp điện áp vượt quá phạm vi quy định.

> **⚠️ Cảnh báo — J1**

Khi kết nối MKE-M17 với Arduino/ESP32 thông qua I2C, đặt:

```text
J1 = OFF
```

Đặc biệt khi sử dụng cùng **MKE-M15 Bluetooth module**, nguồn phải được cấp thông qua chân VCC của I2C Master theo hướng dẫn của MakerEdu.

> **⚠️ Cảnh báo — Motor Output**

Không được làm ngắn mạch các chân ngõ ra:

```text
MA1 / MA2
MB1 / MB2
```

## Khôi phục cài đặt gốc

Nếu không nhớ địa chỉ I2C hiện tại của module:

1. Nhấn và giữ nút `S1/SW1`.
2. Giữ khoảng **4 giây**.
3. Module sẽ xóa cấu hình EEPROM.
4. Địa chỉ I2C được khôi phục về:

```text
0x40
```

Phần cứng hiện tại không có LED riêng để báo trạng thái Factory Reset.

## Thư viện và tài nguyên

### Arduino

Thư viện tổng hợp:

```text
MKE_ONE
```

Driver:

```text
MakerEdu_I2C_MotorDriver
```

Header:

```cpp
#include <MKE_I2C_MotorDriver.h>
```

### Microsoft MakeCode

Extension:

```text
https://github.com/Khuuxuanngoc/makeCode_MKE_I2C_Motor_Driver_extension_test
```

MakeCode:

```text
https://makecode.microbit.org
```

### Module Bluetooth

Bluetooth UART Module tương thích:

```text
MakerEdu MKE-M15
```

Ứng dụng điều khiển:

```text
Dabble App
```

## Tóm tắt

**MKE-M17 MakerEdu I2C Dual DC Motor Driver L9110** là giải pháp điều khiển hai động cơ DC thông qua I2C, tích hợp MCU riêng để xử lý PWM, chiều quay, điều khiển theo thời gian và giám sát điện áp.

Với điện áp motor **6–9VDC**, dòng liên tục **0.8A/kênh**, hỗ trợ **2 kênh motor độc lập**, khả năng thay đổi địa chỉ I2C và kết nối nhiều module trên cùng bus, MKE-M17 phù hợp cho các dự án **robot 2WD/4WD, xe thông minh, STEM, Arduino, ESP32 và micro:bit**.

## Miễn trừ trách nhiệm

Sản phẩm là **bo mạch điều khiển/phát triển** được thiết kế phục vụ mục đích nghiên cứu, thử nghiệm, giáo dục và phát triển robot, không phải là một thiết bị hoàn chỉnh.

Trong trường hợp người dùng kết hợp MKE-M17 với các động cơ, pin, linh kiện, thiết bị hoặc phần mềm khác để tạo thành một hệ thống hoặc sản phẩm hoàn chỉnh, mọi chức năng, độ an toàn và tính phù hợp của hệ thống sau cùng thuộc trách nhiệm của người dùng.
