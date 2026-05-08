# 📺 OLED Bitmap & Animation Generator

Alat berasaskan web untuk menukar imej, GIF, dan video kepada kod tatasusunan (array) C++ yang serasi dengan skrin OLED SSD1306 (128x64). Sesuai untuk projek Arduino, ESP32, dan projek sistem terbenam (embedded) yang lain.

## ✨ Ciri-Ciri Utama
* **Sokongan Video & GIF**: Ekstrak bingkai (frames) secara automatik untuk dijadikan animasi.
* **4 Mod Dithering**: Termasuk Floyd-Steinberg dan Bayer untuk kualiti visual terbaik pada skrin 1-bit.
* **Kawalan Langsung**: Laraskan *brightness*, *contrast*, *threshold*, dan *scaling* secara *real-time*.
* **Output Automatik**: Menghasilkan fail `.h` (data bitmap) dan `.ino` (kod Arduino) yang sedia untuk digunakan.

---

## 🔌 Skema Pendawaian (Wiring)

Projek ini dioptimumkan untuk skrin **OLED I2C (SSD1306)**.

### 1. ESP32 (DevKit V1)
| OLED Pin | ESP32 Pin |
| :--- | :--- |
| **VCC** | 3.3V |
| **GND** | GND |
| **SCL** | GPIO 22 |
| **SDA** | GPIO 21 |

### 2. Arduino Uno
| OLED Pin | Arduino Uno Pin |
| :--- | :--- |
| **VCC** | 5V / 3.3V |
| **GND** | GND |
| **SCL** | A5 |
| **SDA** | A4 |

---

## 📚 Library Diperlukan
Sila pasang library berikut melalui **Library Manager** di Arduino IDE:
1. `Adafruit_SSD1306`
2. `Adafruit_GFX_Library`

---

## 🛠️ Tutorial Penggunaan

### Langkah 1: Jana Kod di Web
1. Buka fail `index.html` pada pelayar web.
2. Muat naik fail gambar (.png/.jpg), GIF, atau video.
3. Laraskan tetapan sehingga preview di bahagian **OLED Live** nampak jelas.
4. Jika menggunakan video/GIF, tekan butang **"Extract Smooth Animation"**.
5. Klik butang **Copy .h** dan **Copy .ino**.

### Langkah 2: Sediakan Fail di Arduino IDE
1. Buka Arduino IDE dan cipta sketch baru (Save as contohnya: `OLED_Animasi`).
2. **Cipta Fail Header**:
   * Klik pada ikon tiga titik di penjuru kanan atas tab Arduino IDE.
   * Pilih **New Tab**.
   * Namakan fail sebagai `VideoFrame.h`.
   * Paste (Tampal) kod dari butang **Copy .h** ke dalam tab ini.
3. **Kod Utama (.ino)**:
   * Pergi semula ke tab utama (fail `.ino`).
   * Padam semua kod asal dan Paste kod dari butang **Copy .ino**.

### Langkah 3: Upload
1. Sambungkan papan mikropengawal anda.
2. Pilih Board dan Port yang betul.
3. Tekan **Upload** dan lihat hasilnya!

---

## 📝 Nota Teknikal
* **Memori**: Animasi video menggunakan banyak memori Flash (PROGMEM). Untuk Arduino Uno, hadkan kepada 3-5 bingkai. Untuk ESP32, anda boleh memuatkan lebih banyak (30-50+ bingkai).
* **Rotation**: Gunakan butang *Rotate* di web generator jika paparan pada skrin fizikal terbalik.

---
Projek ini dibangunkan oleh [mirai](https://mirul-maker.vercel.app/)
