# Bao Cao Thi Nghiem: Tac Dong Cua Chat Luong Du Lieu Den AI Agent

**Ma so hoc vien:** 2A202600056
**Ho va ten:** Hàn Quang Hiếu
**Ngay thuc hien:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | "Based on my data, the best choice is Laptop at $1200." | 9 | Ket qua hop ly, Laptop la san pham gia cao nhat trong du lieu sach |
| Garbage Data (`garbage_data.csv`) | "Based on my data, the best choice is Nuclear Reactor at $999999." | 1 | Agent bi danh lua boi outlier voi gia tri bat thuong $999999 |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung du lieu rac (garbage data), Agent nhan vao nhung du lieu co chat luong kem dan den nhieu van de nghiem trong. Thu nhat, cac gia tri gia am hoac bang 0 khong co y nghia kinh te, khien Agent tinh toan discounted_price sai hoan toan. Thu hai, danh muc bi de trong hoac null lam cho viec phan loai san pham that bai, Agent khong the nhom san pham dung cach. Thu ba, ID trung lap gay ra tinh trang du lieu bi tinh nhieu lan, lam sai lech cac thong ke tong hop nhu tong doanh thu hay so luong san pham. Thu tu, cac gia tri ngoai le (outlier) voi gia qua cao nhu Nuclear Reactor $999999 lam lech phan phoi du lieu, khien Agent de xuat san pham vo nghia trong thuc te. Nhin chung, du lieu rac la nguyen nhan chinh khien AI Agent hoat dong kem hieu qua, bat ke prompt co tot den dau di nua. Day la minh chung ro rang cho thay chat luong du lieu quan trong hon chat luong prompt.

---

## 3. Ket luan

**Chat luong du lieu quan trong hon chat luong prompt?** Dong y hoan toan. Du lieu sach la nen tang cua moi he thong AI. Mot prompt tot khong the bu dap cho du lieu xau — neu dau vao sai thi ket qua dau ra chac chan se sai. Dau tu vao chat luong du lieu luon mang lai hieu qua cao hon la chi tap trung toi uu hoa prompt.
