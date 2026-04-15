[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574114&assignment_repo_type=AssignmentRepo)
# Bài Lab Ngày 10: Data Pipeline & Data Observability

**Email học viên:** email@example.com
**Họ và tên:** (Điền tên của bạn)

---

## Mô tả

Bài lab này xây dựng một pipeline ETL (Extract - Transform - Load) tự động để xử lý dữ liệu sản phẩm từ file JSON. Pipeline thực hiện các bước: đọc dữ liệu thô, kiểm tra và loại bỏ dữ liệu không hợp lệ (giá âm, danh mục trống), chuẩn hóa danh mục về dạng Title Case, tính giá sau giảm 10%, thêm timestamp xử lý, và lưu kết quả ra file CSV.

---

## Cách chạy (How to Run)

### Yêu cầu cài đặt
```bash
pip install pandas pytest
```

### Chạy ETL Pipeline
```bash
python solution.py
```

Kết quả sẽ được lưu vào file `processed_data.csv`.

### Chạy kiểm thử tự động
```bash
pytest tests/test_autograder.py -v
```

### Chạy thí nghiệm Stress Test (Agent Simulation)
```bash
# Chạy với dữ liệu sạch
python agent_simulation.py processed_data.csv

# Chạy với dữ liệu rác
python generate_garbage.py
python agent_simulation.py garbage_data.csv
```

---

## Cấu trúc thư mục

```
├── solution.py              # Script ETL Pipeline chính
├── raw_data.json            # Dữ liệu đầu vào thô
├── processed_data.csv       # Kết quả đầu ra của pipeline
├── experiment_report.md     # Báo cáo thí nghiệm
├── agent_simulation.py      # Script mô phỏng AI Agent
├── generate_garbage.py      # Script tạo dữ liệu rác
└── README.md                # File này
```

---

## Kết quả

Pipeline xử lý 5 bản ghi từ `raw_data.json`:
- **3 bản ghi hợp lệ** được giữ lại và lưu vào CSV
- **2 bản ghi bị loại**: 1 bản ghi có giá âm (-10), 1 bản ghi có danh mục trống
- Tất cả danh mục được chuẩn hóa về Title Case
- Giá giảm 10% được tính và lưu vào cột `discounted_price`
- Timestamp xử lý được thêm vào cột `processed_at`
