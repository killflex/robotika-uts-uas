# 💡 IoT LED Control via Blynk – ESP32 Project

## 📌 Deskripsi Singkat Proyek

Proyek ini merupakan implementasi **Internet of Things (IoT)** menggunakan **ESP32** dan platform **Blynk** untuk mengontrol **LED** dari jarak jauh melalui aplikasi mobile.

Fitur utama:
- Kendali LED ON/OFF dari aplikasi Blynk
- Komunikasi via WiFi dan internet
- Respon real-time terhadap perubahan status tombol virtual

---

## ⚙️ Komponen yang Digunakan

| No | Komponen         | Jumlah |
|----|------------------|--------|
| 1  | ESP32 / ESP8266  | 1      |
| 2  | LED              | 1      |
| 3  | Resistor 220Ω    | 1      |
| 4  | Breadboard & Jumper | 1 set |
| 5  | Smartphone + Aplikasi Blynk | 1 |

---

## 🌐 Platform & Tools

- 📱 **Blynk IoT** (versi terbaru)
- 📶 **WiFi** sebagai koneksi internet
- 💻 **Arduino IDE** untuk pemrograman
- 📲 Virtual Pin Blynk: `V0` (untuk tombol kontrol)

---

## 🔌 Cara Kerja Sistem

1. ESP32 terhubung ke jaringan WiFi
2. Menggunakan **Blynk Auth Token** untuk koneksi ke server Blynk
3. Ketika tombol virtual `V0` di aplikasi ditekan:
   - `value = 1` → **LED menyala**
   - `value = 0` → **LED mati**

---

## 💡 Cuplikan Kode Penting

```cpp
BLYNK_WRITE(V0) {
  int pinValue = param.asInt(); // Ambil nilai dari aplikasi
  digitalWrite(ledPin, pinValue); // Kendalikan LED
}
```

---

## 🛠 Cara Menggunakan

1. Buat project baru di aplikasi **Blynk IoT**
   - Tambahkan **Device** (ESP32)
   - Tambahkan widget **Button**, hubungkan ke **V0**
2. Dapatkan **Auth Token** dari aplikasi Blynk
3. Masukkan Auth Token, nama WiFi, dan password ke dalam kode:
   ```cpp
   char auth[] = "TOKEN_BLYNK_ANDA";
   char ssid[] = "NAMA_WIFI_ANDA";
   char pass[] = "PASSWORD_WIFI_ANDA";
   ```
4. Upload sketch `IoT_OnOff.ino` ke board ESP32
5. Jalankan aplikasi dan coba kendalikan LED dari smartphone

---

## 📂 Struktur File

```
├── IoT_OnOff.ino         ← Kode utama ESP32 untuk kontrol LED via Blynk
└── README.md             ← Dokumentasi proyek
```

---

## 🧑‍💻 Kontributor

Proyek ini dibuat sebagai implementasi sederhana **IoT Home Automation** berbasis ESP32 & Blynk oleh tim iMCLab / UAS / praktikum.
