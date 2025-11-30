# Project Kỹ thuật truyền thông
# 🔍 Tìm Hiểu Thuật Toán ABC và Các Biến Thể (ABC – GABC – qABC)
📌 *Artificial Bee Colony Optimization — HUST SoICT Project*

Dự án này tổng hợp toàn bộ nội dung báo cáo học phần **Kỹ thuật Truyền thông** tại Đại học Bách Khoa Hà Nội.  
Project trình bày lý thuyết nền tảng về **bài toán tối ưu**, **thuật toán ABC**, các biến thể nâng cao như **GABC** và **qABC**, kèm theo mô hình hóa, phân tích ưu — nhược điểm, so sánh và mã giả.

---

## 📘 Nội dung chính

### 1️⃣ Bài toán tối ưu (Optimization Problem)
- Khái niệm cực trị: cực tiểu toàn cục, cực tiểu địa phương, cực tiểu chặt.
- Phân loại:  
  - Quy hoạch tuyến tính / phi tuyến  
  - Quy hoạch nguyên (Discrete Optimization)  
  - Tối ưu đa mục tiêu  
  - Tối ưu liên tục  
- Hai hướng giải:  
  - Giải chính xác (Exact)  
  - Giải gần đúng (Heuristic / Metaheuristic)

---

### 2️⃣ Thuật toán ABC (Artificial Bee Colony)
Thuật toán mô phỏng quá trình tìm kiếm mật của ong mật, gồm 3 pha chính:

- 🐝 **Ong thợ (Employed bees)**: khai thác lân cận nguồn thức ăn  
- 👀 **Ong quan sát (Onlooker bees)**: chọn nguồn theo xác suất dựa trên fitness  
- 🔎 **Ong do thám (Scout bees)**: sinh nghiệm mới thay thế nguồn bị “cạn kiệt”  

🎯 ABC hướng tới cân bằng giữa **khám phá** và **khai thác**, nhưng còn hạn chế về tốc độ hội tụ và khai thác cục bộ.

---

### 3️⃣ Biến thể GABC (Gbest-guided ABC)
GABC bổ sung thêm thành phần kéo nghiệm về **global best**:  
v_ij = x_ij + φ_ij(x_ij - x_kj) + ψ_ij(x_best,j - x_ij)  

- 👍 Tăng tốc độ hội tụ  
- 👍 Khai thác mạnh xung quanh nghiệm tốt nhất  
- 👎 Nhưng dễ hội tụ sớm vào cực trị địa phương

---

### 4️⃣ Biến thể qABC (Quick ABC)
Tập trung vào **leader cục bộ** thay vì global best.

- Xây dựng tập lân cận \( N_i \)  
- Chọn nghiệm tốt nhất vùng \( x^{best}_{N_i} \)  
- Sinh nghiệm mới theo hướng local-best:

v_j = x_best_j + φ (x_best_j - x_kj)  

- 👍 Khai thác mạnh  
- 👍 Giữ đa dạng tốt hơn GABC  
- 👎 Tốn chi phí tính khoảng cách

---

### 5️⃣ So sánh ABC – GABC – qABC
| Tiêu chí | ABC | GABC | qABC |
|---------|-----|------|-------|
| Hướng cập nhật | Ngẫu nhiên | Hướng về global best | Hướng về local best |
| Khai thác | Thấp | Cao | Rất cao |
| Thăm dò | Mạnh | Giảm | Trung bình |
| Nguy cơ kẹt local | Thấp | Cao | Thấp |
| Tốc độ hội tụ | Chậm | Nhanh | Nhanh nhất |

---

## 🧪 Mã giả của ba thuật toán

Repo bao gồm mã giả chuẩn hóa cho:
- ABC
- GABC
- qABC  

Kèm giải thích logic và từng bước thao tác của mỗi pha.


## 🧑‍💻 Thành viên thực hiện
**Nhóm 17 — Trường Công nghệ Thông tin & Truyền thông (SoICT)**  
- Đinh Ngọc Khánh — 20235752  
- Nguyễn Hải Dương — 20235692  

---
