[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112811&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** quang191204@gmail.com
**Name:** WilLz1912

---

## Mo ta

Bai lab nay thuc hien xay dung mot duong ong du lieu ETL (Extract, Validate, Transform, Load) tu dong bang Python va Pandas. Sau do tien hanh thuc nghiem stress test danh gia anh huong cua chat luong du lieu (Data Quality/Data Observability) len cau tra loi cua AI Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Sinh du lieu rac (garbage_data.csv)
python generate_garbage.py

# Chay mo phong de so sanh phan hoi cua Agent
python agent_simulation.py
```

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

- **Tong so records thiet ke**: 5 records thon.
- **Ket qua Validation**: Loc va giu lai 3 records hop le, loai bo 2 records loi (1 record gia < 0, 1 record category bi rong).
- **Thuc nghiem**: 
  - Voi Garbage Data: Agent de xuat "Nuclear Reactor" gia $999,999 (Sai lech hoan toan vi outlier).
  - Voi Clean Data: Agent de xuat "Laptop" gia $1200 (Chinh xac).
