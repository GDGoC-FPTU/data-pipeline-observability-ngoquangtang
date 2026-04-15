[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574027&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** student@example.com
**Name:** Student Name

---

## Mo ta

Bài lab này thực hiện một ETL Pipeline đầy đủ để xử lý dữ liệu sản phẩm từ file JSON:
- **Extract**: Đọc dữ liệu từ `raw_data.json`
- **Validate**: Lọc bỏ records có giá <= 0 hoặc category rỗng
- **Transform**: Tính discounted_price (giảm 10%), chuân hóa category (Title Case), thêm timestamp
- **Load**: Lưu kết quả ra file CSV

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python agent_simulation.py
```
Script này sẽ chạy pipeline với dữ liệu sạch (clean) và dữ liệu rác (garbage) để so sánh hiệu suất.

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Sau khi chạy pipeline với `raw_data.json` (5 records):
- ✅ Records hợp lệ: 3 (Laptop, Chair, Monitor)
- ❌ Records bị loại: 2 (Mystery Box - giá âm, Phone - category rỗng)
- 📊 Output được lưu tại: `processed_data.csv`

**Cột trong output:**
- `id`: ID sản phẩm
- `product`: Tên sản phẩm
- `price`: Giá gốc
- `category`: Danh mục (đã chuân hóa Title Case)
- `discounted_price`: Giá sau khi giảm 10%
- `processed_at`: Timestamp xử lý
