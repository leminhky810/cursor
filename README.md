# 🧠 Ứng dụng AI trong công việc lập trình Android – Công cụ Cursor (Claude Model)

Hiện tại, em đang sử dụng **Cursor – AI Code Editor, với Claude model – để hỗ trợ công việc lập trình Android hằng ngày**. Đây là một công cụ mạnh mẽ giúp em **tăng tốc độ dev và testing**, đặc biệt hiệu quả trong các dự án outsource yêu cầu tiến độ cao và chất lượng ổn định.

---

## 🔧 Mức độ sử dụng AI

Em sử dụng Cursor khoảng **50% tổng thời gian coding**, tập trung vào các mảng như:

- Tạo mới mẫu code hoặc tái sử dụng các class/style hiện có cho `UseCase`, `Repository`, `ViewModel`, `RepositoryImpl`,...  
- Refactor logic bất đồng bộ, xử lý exception trong coroutine  
- Phân tích và viết `unit test` cho `UseCase`, `ViewModel` hoặc `RepositoryImpl`
- Gợi ý định nghĩa cho `interface` (ví dụ: repository), hoặc `sealed class` (state, network result…)  
- Viết `extension functions`, `mapper class` để chuyển đổi từ entity → model → UI, và viết unit test cho chúng  
- Thêm thư viện vào `Gradle` hoặc `toml` (Cursor có thể khai báo và implement).
- Thêm comment cho file và viết README.

**Ví dụ:** Trong một task xử lý danh sách ảnh, em sử dụng Cursor để sinh nhanh một `UseCase` lấy dữ liệu từ Room thông qua repository interface, và viết unit test tương ứng, bao gồm mock repository impl và coroutine scope bằng `runTest`, nhằm kiểm tra kết quả trả về có đúng với dữ liệu giả định không.

---

## ✅ Ưu điểm

- **Tiết kiệm thời gian:** Có thể sinh nhanh các đoạn code boilerplate như Adapter, ViewModel, base parser, v.v.  
- **Học hỏi và tham khảo:** Cursor có thể phân tích đoạn code hiện tại và đề xuất các hướng xử lý, giúp em chọn giải pháp phù hợp với context.  
- **Giảm lỗi lặp lại:** Đề xuất refactor hợp lý, tránh lỗi copy-paste hoặc logic trùng lặp.

---

## ⚠️ Nhược điểm

- **Hạn chế với các task liên quan đến UI:** Cursor hỗ trợ tốt phần bind dữ liệu, nhưng còn hạn chế với các hành vi UI phức tạp như scroll, gesture, nested motion.  
  > Ví dụ: Khi em nhờ Cursor custom carousell behavior cho `List View` dạng lưới, kết quả là UI bị giật, không mượt, và cuộn sai vị trí cell. Sau nhiều lần chỉnh sửa, Cursor không nhận ra được nhược điểm của hướng tiếp cận này. Sau khi em thay đổi hướng làm, kết quả mới đúng như mong muốn.

- **Đề xuất đôi khi không chính xác hoàn toàn**, hoặc gợi ý các method/logic không tồn tại, hoặc của những version cũ hơn.

- **Không tận dụng API có sẵn:** Thay vì tận dụng các API có sẵn (như `Result.retry` trong `WorkManager`), Cursor đôi khi tự viết lại bằng `repeat` thủ công, gây dư thừa và khó kiểm soát.

- **Cần kiểm tra đầu ra:** Có khả năng AI chỉnh sửa cả những file ngoài phạm vi yêu cầu, gây side-effect nếu không kiểm soát kỹ.

- **Không tích hợp trực tiếp với IDE như IntelliJ hay Xcode:** Việc phải chuyển sang Cursor để sử dụng AI khiến quy trình làm việc bị phân mảnh, không liền mạch như các plugin AI tích hợp sẵn (ví dụ: github copilot).

- **Tự động hạ cấp model nếu vượt hạn mức (quota):** Dù đang dùng bản trả phí, Cursor có thể tự động chuyển xuống Claude thấp hơn khi em sử dụng vượt giới hạn trong ngày/tháng. Điều này ảnh hưởng đến chất lượng phản hồi nếu em không để ý và có thể khiến kết quả thiếu chiều sâu hoặc không đồng nhất.

---

## 📌 Lưu ý khi sử dụng

- **Prompt phải rõ ràng và cụ thể.**  
  Ví dụ:  
  ✅ “Viết unit test cho `UserViewModel` sử dụng JUnit và MockK, không bao gồm ui test”  
  ❌ “Viết unit test cho `UserViewModel`”  
  → Nếu không rõ, AI có thể sinh cả InstrumentedTest hoặc dùng thư viện không phù hợp.

- **Luôn kiểm tra phần summary** mà Cursor trả về sau mỗi tác vụ, nhất là khi chỉnh sửa nhiều file.

- **Tuyệt đối không để lộ thông tin nhạy cảm.**  
  Với phiên bản Cursor em đang sử dụng, AI có quyền truy cập toàn bộ mã nguồn, do đó:
  - Các `secret key`, `token`, `credential` cần được thay bằng template hoặc dữ liệu giả (dành riêng cho môi trường test)  

---

## 🧩 Kết luận

AI (Cursor + Claude) đã trở thành một **trợ lý hiệu quả và đáng tin cậy** trong công việc lập trình Android của em. Tuy nhiên, để khai thác tối đa lợi ích, em cần:
- **Quản lý rõ phạm vi sử dụng**
- **Cung cấp đầy đủ ngữ cảnh**
- **Kiểm tra đầu ra một cách kỹ lưỡng**

Đặc biệt, việc **quản lý token, key và thông tin nhạy cảm** là rất quan trọng để đảm bảo an toàn và bảo mật trong quá trình phát triển dự án.

**Sự kết hợp giữa con người và AI – khi dùng đúng cách – sẽ giúp cải thiện chất lượng, tốc độ và tính nhất quán trong quá trình phát triển dự án.**

---

## 🤖 So sánh nhanh với GitHub Copilot

| Tiêu chí                  | Cursor (Claude)                                     | GitHub Copilot (OpenAI Codex)               |
|---------------------------|-----------------------------------------------------|---------------------------------------------|
| **Mô hình AI**            | Claude (Anthropic)                                  | Codex (OpenAI)                              |
| **Giao diện sử dụng**     | IDE riêng biệt (Cursor editor)                     | Tích hợp trực tiếp trong VSCode, IntelliJ   |
| **Hiểu ngữ cảnh toàn file**| Rất tốt – có thể đọc nhiều file cùng lúc           | Khá tốt – tập trung trong từng file         |
| **Phản hồi có giải thích**| Có summary, reasoning                              | Chủ yếu gợi ý code, không có reasoning rõ   |
| **Mạnh về…**              | Refactor, generate, kiến trúc, pattern              | Autocomplete nhanh                          |
| **Yếu ở…**                | Không tích hợp IDE phổ biến                        | Không hiểu toàn bộ context lớn như Claude   |

➡️ **Em chọn Cursor khi cần reasoning, cấu trúc tốt hoặc xử lý logic phức tạp; chọn Copilot khi cần code nhanh, đơn giản, và tích hợp liền mạch trong IDE.**