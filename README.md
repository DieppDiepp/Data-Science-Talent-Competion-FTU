# Data Science Talent Competion, CLB CTE FTU Hà Nội
------
## Đây là đề thi vòng 1, vòng 2 dataset private nên mình không public

---

# 🏆 HomeMart Data Challenge  

## 🚀 Giới thiệu  

Repo này chứa lời giải cho một cuộc thi **phân tích dữ liệu bán lẻ** tại HomeMart. Thí sinh được cung cấp dữ liệu hành vi mua sắm của khách hàng và phải thực hiện **làm sạch dữ liệu, tiền xử lý, khai thác dữ liệu** nhằm tối ưu hóa hoạt động kinh doanh. Xem đề bài tại [BANG-B-Cau-hoi-Vong-01.pdf](https://github.com/DieppDiepp/Data-Science-Talent-Competion-FTU/blob/main/01.%20DSTC%202024%20_%20T%C3%80I%20LI%E1%BB%86U%20B%E1%BA%A2NG%20B/BANG-B-Cau-hoi-Vong-01.pdf)

### 🔥 Thách thức chính: **Xác định khi nào khách hàng thực sự mua sản phẩm?**  

Dữ liệu không ghi nhận trực tiếp giao dịch "mua hàng", nên cần **phân tích hành vi khách hàng** để suy luận được **một sản phẩm có thực sự được mua hay không?**  

## 📊 Dữ liệu  

Bộ dữ liệu bao gồm **3 bảng CSV**:  

1️⃣ **Shelf information** – Thông tin về vị trí các gian hàng.  
2️⃣ **Customer behavior** – Hành vi chi tiết của khách hàng (nhìn, cầm, đặt hàng vào giỏ…).  
3️⃣ **Item information** – Danh sách sản phẩm và thông tin chi tiết.  

---

## ❓ Thách thức lớn nhất: **Khi nào khách hàng thực sự MUA sản phẩm?**  

📌 **Điều kiện để xác định một sản phẩm đã được mua**:  
✔ **Nhặt lên** (*Picking up item* = True)  
✔ **Không bị trả lại kệ** (*Returning item* = False)  
✔ **Bỏ vào giỏ hàng** (*Putting item into bag* = True)  
✔ **Không bị lấy ra khỏi giỏ** (*Taking item out of bag* = False)  
✔ Nếu bị lấy ra khỏi giỏ nhưng **được bỏ vào lại lần 2** (*Putting item into bag in the 2nd time* = True) => **Vẫn tính là đã mua**.  

💡 **Điều này giúp loại bỏ các trường hợp khách hàng chỉ xem sản phẩm mà không mua thực sự.**  

---

## 🛠️ **Phương pháp giải quyết**  

🔍 **Bước 1: Làm sạch & tiền xử lý dữ liệu**  
- Điền dữ liệu thiếu (*missing values*) bằng xử lý logic và phương pháp nội suy.  
- Chuẩn hóa lại các trạng thái hành vi của khách hàng.  

📈 **Bước 2: Phân tích dữ liệu để tìm ra câu trả lời**  

| 🏆 Câu hỏi | 📌 Phương pháp giải quyết |
|------------|--------------------------|
| **1️⃣ & 2️⃣**: 📊 **Thống kê 5 sản phẩm có tổng thời gian nhìn và cầm lâu nhất & 5 sản phẩm bị cầm lên rồi đặt lại nhiều nhất** | ✅ **Dùng Excel**: Lọc dữ liệu, tính tổng thời gian quan sát và kiểm tra tần suất cầm lên rồi đặt lại. |
| **3️⃣**: 🛒 **Nhóm khách hàng theo độ tuổi thích mua mặt hàng nào nhất?** | ✅ **Phân nhóm theo độ tuổi**, áp dụng điều kiện mua hàng và lọc ra sản phẩm phổ biến nhất mỗi nhóm. |
| **6️⃣ & 7️⃣**: 🎯 **Top 5 sản phẩm giảm giá và quảng cáo được mua nhiều nhất** | ✅ Lọc danh sách sản phẩm có chương trình giảm giá/quảng cáo và kiểm tra số lần được mua. |
| **8️⃣ & 9️⃣**: 🏬 **Quầy hàng nào khách hàng quan tâm & mua sắm nhiều nhất?** | ✅ Tính thời gian trung bình khách hàng "nhìn & cầm" sản phẩm tại từng quầy hàng, ✅ Thống kê quầy có doanh số cao nhất. |
| **🔟**: 🚶‍♂️ **Hành trình di chuyển giữa các quầy hàng phổ biến nhất** | ✅ Phân tích chuỗi di chuyển của khách hàng và tìm ra cặp quầy hàng có tần suất di chuyển nhiều nhất. |

---
## 📊 Câu trả lời của tôi

Xem chi tiết tại các file:

📊 [**Cau_1_2.xlsx**](https://github.com/DieppDiepp/Data-Science-Talent-Competion-FTU/blob/main/01.%20DSTC%202024%20_%20T%C3%80I%20LI%E1%BB%86U%20B%E1%BA%A2NG%20B/205160_Round01/Cau_1_2.xlsx)  
📘 [**Cau_3_6_7_8_9_10_11_12.ipynb**](https://github.com/DieppDiepp/Data-Science-Talent-Competion-FTU/blob/main/01.%20DSTC%202024%20_%20T%C3%80I%20LI%E1%BB%86U%20B%E1%BA%A2NG%20B/205160_Round01/Cau_3_6_7_8_9_10_11_12.ipynb)

---

### 📌 **Thông tin bổ sung**
[![GitHub](https://img.shields.io/badge/Truy%20c%E1%BA%ADp-GitHub-blue?logo=github)](https://github.com/DieppDiepp/Data-Science-Talent-Competion-FTU)


## 🎯 **Tóm tắt kết quả quan trọng**  

- **✨ Nhóm khách hàng trung niên (31 - 60)** là nhóm tiêu dùng mạnh nhất, mua nhiều **kem tràng tiền**. 🍦  
- **📅 Ngày có doanh thu cao nhất:** khả năng rơi vào **cuối tuần**, do lượng khách tăng cao. 📈  
- **📌 Quầy số 7** – Thu hút sự chú ý lớn nhất, có thời lượng quan tâm trên lượt truy cập cao nhất.  
- **🚶‍♂️ Xu hướng di chuyển:** **Quầy số 7 → Quầy số 0** là lộ trình phổ biến của khách hàng.  

---

## 🎯 **Tổng kết**  

Giải pháp này tập trung vào việc **xây dựng quy tắc xác định mua hàng hợp lý**, làm sạch dữ liệu chặt chẽ và **phân tích hành vi tiêu dùng theo từng bước rõ ràng**.  

💡 **Điểm mạnh của phương pháp này:**  
- ✅ **Excel** giúp thống kê và trực quan hóa dữ liệu nhanh chóng.  
- ✅ **Python** xử lý tập dữ liệu lớn, lọc khách hàng theo hành vi mua hàng chính xác.  
- ✅ **Hệ thống rule-based rõ ràng** để xác định khi sản phẩm thực sự được mua.  

🚀 Với cách tiếp cận này, có thể **tối ưu hóa chiến lược nhập hàng, quảng cáo và khuyến mãi** để tăng doanh số bán lẻ hiệu quả!  
