# 🌡️ Arduino LM35 Temperature Monitor

Dự án mạng cảm biến nhiệt độ sử dụng Arduino UNO và cảm biến LM35, đọc dữ liệu từ **3 kênh analog** (A0, A1, A2) và gửi qua **Serial** dưới định dạng **JSON**.

> 📚 Môn học: Mạng Cảm Biến — Tuần 03: Git/GitHub + Arduino

---

## ✨ Tính năng

- 🔹 Đọc đồng thời 3 cảm biến LM35 trên kênh A0, A1, A2
- 🔹 Chuyển đổi ADC sang nhiệt độ (°C) theo công thức: `Temp = (ADC * 500.0) / 1023.0`
- 🔹 Xuất dữ liệu qua Serial dưới dạng JSON: `{"T1":25,"T2":30,"T3":28}`
- 🔹 Tốc độ lấy mẫu: 100ms/lần

---

## 🔧 Phần cứng cần thiết

| STT | Linh kiện | Số lượng | Ghi chú |
|-----|-----------|----------|---------|
| 1 | Arduino UNO (Genuino UNO) | 1 | Board chính |
| 2 | Cảm biến LM35 | 3 | Kênh A0, A1, A2 |
| 3 | Điện trở 100Ω | 3 | Bảo vệ đầu vào |
| 4 | Tụ điện 1µF | 3 | Lọc nhiễu |
| 5 | COMPIM (RS232 Serial) | 1 | Giao tiếp TX/RX |

> ⚠️ Dự án được mô phỏng trên **Proteus**, không sử dụng phần cứng thật.

---

## 🚀 Cách sử dụng

### 1. Clone repository
```bash
git clone https://github.com/P-ThanhSang/Arduino_LM35_TempMonitor.git
cd Arduino_LM35_TempMonitor
```

### 2. Mở firmware
- Mở file `firmware/LM35_TempReader/LM35_TempReader.ino` bằng **Arduino IDE**
- Chọn Board: **Arduino UNO**
- Chọn Port tương ứng

### 3. Upload và theo dõi
- Nhấn **Upload** để nạp code
- Mở **Serial Monitor** (Baud rate: `9600`)
- Dữ liệu JSON sẽ hiển thị liên tục:
```
{"T1":25,"T2":30,"T3":28}
{"T1":26,"T2":31,"T3":29}
```

---

## 📁 Cấu trúc thư mục

```
Arduino_LM35_TempMonitor/
├── firmware/
│   └── LM35_TempReader/
│       └── LM35_TempReader.ino    # Code chính Arduino
├── pc_app/                         # Ứng dụng PC (phát triển sau)
├── docs/                           # Tài liệu dự án
├── libs/                           # Thư viện bổ sung
├── simulation/                     # File mô phỏng Proteus
├── .gitignore                      # Bộ lọc file Git
└── README.md                       # File này
```

---

## 👥 Thành viên nhóm

| Họ tên | MSSV | Vai trò | GitHub |
|--------|------|---------|--------|
| Phạm Thanh Sang | *(điền MSSV)* | Trưởng nhóm | [@P-ThanhSang](https://github.com/P-ThanhSang) |

---

## 📜 Quy ước Commit

| Prefix | Ý nghĩa | Ví dụ |
|--------|----------|-------|
| `feat:` | Tính năng mới | `feat: ho tro doc 2 kenh LM35` |
| `fix:` | Sửa lỗi | `fix: sua loi doc ADC sai` |
| `docs:` | Tài liệu | `docs: cap nhat README` |
| `refactor:` | Tái cấu trúc | `refactor: tach ham doc cam bien` |

---

*Dự án được phát triển trong khuôn khổ môn học Mạng Cảm Biến.*
