# 🤖 Sensor Ultrasonik dengan Servo & Buzzer – iMCLab Test

## 📌 Deskripsi Singkat Proyek

Proyek ini merupakan **skrip pengujian Arduino** menggunakan sensor ultrasonik **HC-SR04**, motor **servo**, dan **buzzer**. Sistem akan mengukur jarak objek di depan sensor dan memberikan respon:

- Jika jarak < 10 cm: **servo bergerak** dan **buzzer berbunyi**
- Jika jarak ≥ 10 cm: sistem kembali ke posisi awal dan buzzer mati

Proyek ini dikembangkan dalam rangka praktikum/pengujian sistem robotika cerdas di iMCLab.

---

## ⚙️ Komponen yang Digunakan

| No | Komponen         | Jumlah |
|----|------------------|--------|
| 1  | Arduino UNO/Nano | 1      |
| 2  | HC-SR04 Sensor   | 1      |
| 3  | Motor Servo      | 1      |
| 4  | Buzzer           | 1      |
| 5  | Breadboard + Jumper | 1 set |

---

## 🧠 Cara Kerja Sistem

1. Sensor **HC-SR04** mengukur jarak ke objek di depannya
2. Jika objek terdeteksi pada jarak **< 10 cm**:
   - **Servo** bergerak (misal: membuka palang)
   - **Buzzer** berbunyi sebagai peringatan
3. Jika tidak ada objek (jarak ≥ 10 cm):
   - Servo kembali ke posisi awal
   - Buzzer dimatikan

---

## 💡 Cuplikan Kode Penting

```cpp
if (jarak < 10) {
  digitalWrite(buzzer, HIGH);  // Aktifkan buzzer
  myservo.write(90);           // Putar servo
  delay(1000);
} else {
  digitalWrite(buzzer, LOW);   // Matikan buzzer
  myservo.write(0);            // Kembalikan servo
  delay(1000);
}
```

---

## 🛠 Cara Menggunakan

1. **Upload** file `01_Test_iMCLab.ino` ke board Arduino (UNO/Nano)
2. Pastikan semua komponen sudah terpasang dengan benar sesuai pin:
   - Trigger HC-SR04: pin 9
   - Echo HC-SR04: pin 8
   - Buzzer: pin 3
   - Servo: pin 11
3. Buka **Serial Monitor** (9600 baud) untuk melihat jarak yang terbaca

---

## 📂 Struktur File

```
├── 01_Test_iMCLab.ino     ← File utama Arduino sketch
└── README.md              ← Dokumentasi proyek
```

---

## 📸 Dokumentasi Tambahan _(opsional)_

Jika ada, tambahkan:
- Gambar wiring diagram
- Video demo sistem
- Data pengujian

---

## 🧑‍💻 Kontributor

Proyek ini dibuat oleh tim praktikum iMCLab untuk keperluan pembelajaran dan pengujian sensor + aktuator berbasis Arduino.
