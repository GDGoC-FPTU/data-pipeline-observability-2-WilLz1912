# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-WilLz1912
**Name:** WilLz1912
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Dua ra ket qua chinh xac, hop ly tu danh sach san pham dien tu thuc te. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Tra loi ngo ngan vi de xuat lo phan ung hat nhan voi gia tren troi. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung Garbage Data, AI Agent bi anh huong nghiem trong boi cac van de ve chat luong du lieu:
1. **Gia tri ngoai le cuc doan (Outliers)**: San pham "Nuclear Reactor" co gia tri toi $999,999. Do khong duoc loc bo o dau vao, thuat toan lua chon san pham dat nhat (duoc thiet ke de tim "best electronic product") da de xuat san pham phi ly nay.
2. **Kieu du lieu sai (Wrong data types)**: "Broken Chair" co gia tri price la chuoi chu "ten dollars" chu khong phai so. Neu he thong can tinh toan hoac sap xep tang/giam, viec nay se gay crash hoac lam sai lech ket qua.
3. **Trung lap ID (Duplicate IDs)**: ID 1 bi gan cho ca Laptop va Banana, khien he thong bi lung tung khi truy van index.
4. **Gia tri thieu (Null values)**: "Ghost Item" co nhieu gia tri None lam Agent khong the phan loai hay tinh toan logic.

Vi AI Agent suy luan dua tren nguon du lieu duoc cung cap (Knowledge Base), neu nguon nay bi "nhiem doc" (Poisoned data), nguyen ly "Garbage In, Garbage Out" se xay ra: he thong se dua ra nhung ket qua ngo ngan va sai su that.

---

## 3. Ket luan

**Quality Data > Quality Prompt?**
Dong y. Cho du prompt viet co tot va logic den dau di chang nua (Quality Prompt), neu du lieu dau vao truy van (Knowledge Base) bi loi, sai loai hoac chua cac outlier ky quac thi Agent van se lay phai thong tin sai va de xuat sai cho nguoi dung. Viec lam sach du lieu qua ETL la nen mong bat buoc de AI Agent hoat dong tin cay.
