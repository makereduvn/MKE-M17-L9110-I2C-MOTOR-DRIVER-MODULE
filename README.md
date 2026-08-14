# Mạch diều khiển động cơ DC MKE-M17 L9110 I2C Motor Driver Module

## Giới thiệu

## Giới thiệu

**Mạch điều khiển động cơ DC MKE-M17 L9110 I2C Motor Driver Module** là module điều khiển **2 động cơ DC công suất thấp 0.8A/kênh** như **TT Motor, N20 Motor** thông qua giao tiếp **I2C**. Module tích hợp **vi điều khiển 32-bit ARM Cortex-M0+** đảm nhiệm việc tạo PWM, điều khiển chiều quay, quản lý thời gian và giám sát điện áp nguồn motor, giúp vi điều khiển chính như **Arduino, ESP32, ESP8266, Raspberry Pi hoặc STM32** dễ dàng điều khiển động cơ chỉ thông qua hai tín hiệu **SDA và SCL**. 

Module sử dụng **2 x IC L9110** làm mạch cầu H, hỗ trợ điều khiển độc lập hai động cơ với các chức năng:

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
| **Product SKU**                  | MKE-M17                                |
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
| **Module Bluetooth tương thích** | [MKE-M15-BLUETOOTH-UART-MODULE ](https://github.com/makereduvn/MKE-M15-BLUETOOTH-UART-MODULE)        |
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

## Sơ đồ kết nối

| MCU | MKE-M17     | Chức năng          |
| ----------- | ----------- | ------------------ |
| `5V`        | `5V`       | Nguồn dương 5VDC   |
| `GND`       | `GND`       | Nguồn âm 0VDC      |
| `SDA`        | `SDA`       | I2C Data           |
| `SCL`        | `SCL`       | I2C Clock          |

| Ngoại vi | MKE-M17     | Chức năng          |
| ----------- | ----------- | ------------------ |
| DC Motor 1  | `MA1 / MA2` | Motor A            |
| DC Motor 2  | `MB1 / MB2` | Motor B            |
| Battery `+` | `6-9V`      | Nguồn motor 6–9VDC |
| Battery `-` | `GND`       | Nguồn âm 0VDC   |

### Jumper J1
Jumper J1 dùng để lựa chọn nguồn Module MKE-M17.

**J1 = OFF — Mặc định**
Nguồn cấp cho Module MKE-M17 **hoạt động độc lập với nguồn cấp cho động cơ**, khi đó chân 5V trên cổng I2C/BLE sẽ là chân nguồn **Input 5VDC**, sử dụng trong trường hợp muốn tách biệt phần cấp nguồn giữa Mạch điều kiển động cơ và bo mạch chủ MCU.

**J1 = ON**
Nguồn cấp cho Module MKE-M17 **hoạt động sử dụng chung nguồn cấp cho động cơ**, khi đó chân 5V trên cổng I2C/BLE sẽ là chân nguồn **Output 5VDC / Max 700mA**, sử dụng trong trường hợp muốn tận dụng nguồn cấp cho mạch điều khiển động cơ để cấp nguồn cho bo mạch chủ MCU hoặc **[MKE-M15-BLUETOOTH-UART-MODULE ](https://github.com/makereduvn/MKE-M15-BLUETOOTH-UART-MODULE)**.

### Nút nhấn chức năng SW1
MKE-M17 tích hợp một nút nhấn đa chức năng.

**Kiểm tra motor**
Nhấn nút **1 lần** để chạy chương trình tự kiểm tra:
1. Motor A quay thuận.
2. Motor A quay ngược.
3. Motor B quay thuận.
4. Motor B quay ngược.

**Khôi phục cài đặt gốc**
Nhấn và giữ nút khoảng **4 giây**.
Module sẽ:
* Xóa cấu hình trong EEPROM.
* Khôi phục địa chỉ I2C về mặc định `0x40`.

## Hướng dẫn cài đặt bộ thư viện

### Sử dụng với Arduino Uno / Vietduino Uno / ESP32
- Trong **Tools / Library Manager**, tìm và cài đặt bộ thư viện tổng hợp **"MKE_ONE" by MakerEdu.vn**
- Mở chương trình mẫu tại **File / Examples / MKE_ONE / Module / MKE_M17_I2C_L9110**
- Cấu hình board mạch tương ứng là **Arduino Uno / ESP32**, chọn đúng cổng **COM Port** của mạch và nhấn **Upload** để nạp chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân SDA và SCL của Sensor với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

### Sử dụng với Micro:bit (kéo thả khối)

- Khởi động [Microsoft MakeCode](https://makecode.microbit.org/) và **Import** chương trình theo đường link sau: `https://github.com/makereduvn/mke_m17_i2c_l9110_microbit/`
- Kết nối mạch Micro:bit và **Download** chương trình.
- Cấp nguồn 5VDC cho mạch, kết nối chân SDA và SCL của Sensor với chân điều khiển được khai báo trong chương trình.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

Nếu bắt đầu tự án mới cần cài đặt Extension **MKE_ONE_MICROBIT** trên [Microsoft MakeCode](https://makecode.microbit.org/) theo [hướng dẫn tại đây](https://github.com/makereduvn/MKE_ONE_MICROBIT). Sau khi cài đặt thành công, các khối lệnh của Extension **MKE_ONE_MICROBIT** sẽ xuất hiện trong danh sách block và sẵn sàng để sử dụng.


## Bộ thư viện MKE_I2C_MotorDriver

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

> **Quan trọng:** `MKE_I2C_MotorDriver` không tự gọi `Wire.begin()` bên trong thư viện. Luôn gọi `Wire.begin()` trong `setup()` trước khi gọi `motorDriver.begin()`.

### Ví dụ 1: Điều khiển động cơ chạy, đảo chiều quay và dừng

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
  // Motor A quay thuận với tốc độ 200
  motorDriver.motorA_CW(200);

  delay(1000);

  // Motor A quay nghịch với tốc độ 200
  motorDriver.motorA_CCW(200);

  delay(1000);

  // Dừng tất cả motor
  motorDriver.stopAll();

  delay(1000);
}
```

### Ví dụ 2: Chạy motor theo thời gian định sẵn

MKE-M17 hỗ trợ lệnh điều khiển motor chạy theo thời gian định sẵn, giúp Master có thể gửi lệnh chạy motor mà không cần duy trì việc điều khiển PWM liên tục. Ngoài ra còn tích hợp cơ chế **PID Watchdog Safety**, trong đó Master có thể gửi lệnh định kỳ, nếu quá thời gian timeout mà không nhận được lệnh tiếp theo, motor sẽ được dừng an toàn.

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

### Ví dụ 3: Đọc điện áp pin

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

### Ví dụ 4: Sử dụng nhiều Module MKE-M17 trên cùng bus I2C

Mỗi Module MKE-M17 có thể được cấu hình một địa chỉ I2C khác nhau, cho phép nhiều driver hoạt động trên cùng một bus.

Ví dụ sử dụng hai Module MKE-M17:

```cpp
#include <Wire.h>
#include <MKE_I2C_MotorDriver.h>

MKE_M17_MotorDriver frontWheels;
MKE_M17_MotorDriver rearWheels;

void setup() {

  Wire.begin();

  // Module phía trước, sử dụng địa chỉ mặc định 0x40
  frontWheels.begin(0x40);

  // Module phía sau, cần đổi sang địa chỉ 0x41 bằng hàm đổi địa chỉ trước đó để không trùng lặp
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

Cách cấu hình này cho phép xây dựng hệ thống **4WD sử dụng 2 module MKE-M17**, trong đó mỗi module điều khiển 2 động cơ, tổng điều khiển 4 động cơ độc lập.

### Ví dụ 5: Điều khiển Robot 4 bánh Mecanum

Hai Module MKE-M17 có thể được sử dụng để điều khiển Robot 4 bánh Mecanum.

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

## Giao thức Truyền nhận I2C Chuẩn (Raw Protocol)

Dành cho lập trình viên sử dụng trên các nền tảng khác như ESP-IDF (C), Raspberry Pi (Python smbus2), STM32 HAL:

### Định dạng Gói Ghi (Master → Slave)
- Độ dài cố định: 6 bytes
- Cấu trúc: [Region (0x05)] [ModeID (1 byte)] [Payload MSB] [Payload Byte 2] [Payload Byte 1] [Payload LSB]
- Thứ tự byte: Big-Endian (Byte trọng số cao truyền trước).
- Quy tắc Payload:
  - Lệnh cơ bản: payload = speed (0–255).
  - Lệnh có hẹn giờ: payload = ((uint32_t)duration_ms << 16) | (uint32_t)speed.

### Trình tự Đọc Dữ liệu (Master ⇄ Slave)
- Gửi gói Write 6 byte với ModeID cần đọc (payload = 0).
- Tạo độ trễ tối thiểu 200 μs (delayMicroseconds(200)) để Slave MCU chuẩn bị dữ liệu.
- Gửi lệnh I2C Read đọc 4 bytes (requestFrom(address, 4)).
- Ghép 4 bytes nhận được thành số nguyên 32-bit Big-Endian.

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

## Điều khiển Bluetooth với MKE-M15 và Dabble

Module MKE-M17 có thể kết nối trực tiếp với **[MKE-M15-BLUETOOTH-UART-MODULE ](https://github.com/makereduvn/MKE-M15-BLUETOOTH-UART-MODULE)** để điều khiển độc lập qua [APP Dabble](https://thestempedia.com/product/dabble/) mà không cần MCU.

### Sơ đồ kết nối

| MKE-M17 | MKE-M15     | Chức năng          |
| ----------- | ----------- | ------------------ |
| `GND`       | `GND`       | Nguồn âm 0VDC      |
| `5V`        | `5V`       | Nguồn dương 5VDC    |
| `RX`        | `TX`       | Chân giao tiếp UART |
| `TX`        | `RX`       | Chân giao tiếp UART |

> **Quan trọng:** Ở chế độ này Jummper J1 cần được thiết lập là **J1 = ON**, khi đó nguồn cấp cho Module MKE-M17 **hoạt động sử dụng chung nguồn cấp cho động cơ**, chân 5V trên cổng BLE sẽ là chân nguồn **Output 5VDC / Max 700mA** cấp nguồn cho bo mạch **[MKE-M15-BLUETOOTH-UART-MODULE ](https://github.com/makereduvn/MKE-M15-BLUETOOTH-UART-MODULE)**.

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

## Kích thước sản phẩm
![MKE-M17 I2C_L9110](/extras/MKE-M17_1.jpg)

## Hình ảnh sản phẩm
![MKE-M17 I2C_L9110](/extras/MKE-M17_2.png)
![MKE-M17 I2C_L9110](/extras/MKE-M17_3.png)

## Miễn trừ trách nhiệm
Sản phẩm này là bo mạch phát triển được thiết kế phục vụ cho mục đích nghiên cứu, thử nghiệm và học tập, không phải là một thiết bị hoàn chỉnh. Trong trường hợp người dùng kết hợp mạch này với các linh kiện, thiết bị hoặc phần mềm khác để tạo thành một hệ thống hoặc sản phẩm hoàn chỉnh, mọi chức năng và tính phù hợp của sản phẩm sau cùng đều thuộc trách nhiệm của người dùng.
