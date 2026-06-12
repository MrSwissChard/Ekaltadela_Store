# Ekaltadela Store

Một siêu dự án mã nguồn mở xây dựng hệ sinh thái ứng dụng đa nền tảng thế hệ mới, hoạt động độc lập và tách biệt hoàn toàn khỏi hệ điều hành nền tảng.

---

## 🎯 Tầm nhìn & Mục tiêu (Vision & Goals)

Mục tiêu cốt lõi của **Ekaltadela Store** là định nghĩa lại cách phân phối và thực thi ứng dụng bằng việc phân tách triệt để giữa logic phần mềm và môi trường hệ điều hành:

*   **Viết một lần, chạy mọi nơi đúng nghĩa:** Các ứng dụng trên Store sẽ được viết riêng cho một bộ API chuẩn (Core) thống nhất của Ekaltadela, hoàn toàn không phụ thuộc vào hệ điều hành (OS) bên dưới.
*   **Tách biệt kiến trúc:** Trọng tâm của dự án là xây dựng một môi trường thực thi (Runtime Engine) quản lý các App Core này. Việc tương thích với từng hệ điều hành cụ thể (Windows, Linux, macOS, Android...) sẽ do một lớp dịch chuyển cấp thấp (Compatibility Layer) riêng biệt xử lý.
*   **Hiệu năng & An toàn:** Hệ thống hướng tới sự tối ưu tuyệt đối về tốc độ, bảo mật sandbox và quản lý tài nguyên gọn nhẹ nhất có thể.

---

## 🏗️ Kiến trúc Hệ thống (System Architecture)

Dự án được chia thành 3 thành phần độc lập:

1.  **App Core (Lớp Ứng dụng):** Các phần mềm được phát triển dựa trên bộ API/Core chuẩn của Ekaltadela. Lớp này chỉ chứa logic nghiệp vụ và giao diện chung, chạy giống nhau 100% trên mọi nền tảng.
2.  **Ekaltadela Store / Runtime Engine (Lớp Lõi):** Môi trường trung gian chịu trách nhiệm nạp, thực thi và quản lý vòng đời của App Core. 
3.  **OS Compatibility Layer (Lớp Tương thích):** Thành phần cầu nối cấp thấp (Low-level). Thành phần này sẽ dịch chuyển các lệnh gọi từ Lớp Lõi (Store Engine) thành các API Native của từng OS cụ thể.

---

## 🛠️ Công nghệ Dự kiến (Proposed Tech Stack)

Để hiện thực hóa kiến trúc phức tạp này, siêu dự án định hướng tích hợp sức mạnh từ các công nghệ mã nguồn mở hàng đầu:
*   **Rust / C++:** Sử dụng để xây dựng *Runtime Engine* và *OS Compatibility Layer* nhằm đảm bảo hiệu năng tối đa, an toàn bộ nhớ và can thiệp sâu xuống tầng hệ thống.
*   **Dart (Flutter) / Python:** Sử dụng để định hình cách thiết kế API cho *App Core*, giúp các nhà phát triển dễ dàng xây dựng ứng dụng với giao diện mượt mà và logic tối ưu.

---

## 🤝 Kêu gọi Cộng tác (Call for Contributors)

**Ekaltadela là một siêu dự án khổng lồ và đầy rủi ro kỹ thuật.** Người khởi xướng dự án giữ vai trò định hướng tầm nhìn nhưng năng lực lập trình hệ thống (đặc biệt là Rust) hiện tại còn rất giới hạn. Chúng tôi rất cần sự chung tay từ cộng đồng mã nguồn mở toàn cầu để cùng gánh vác các phần việc khó.

Chúng tôi tìm kiếm các cộng sự ở các mảng:
*   **Kiến trúc sư Hệ thống (System Architects):** Phản biện, tối ưu hóa mô hình phân tầng và thiết kế cơ chế giao tiếp giữa các lớp (IPC, Dynamic Loading, Sandboxing).
*   **Lập trình viên Cấp thấp (Low-level Developers):** Xây dựng nền móng Core Engine bằng Rust/C++ và viết lớp tương thích cho các OS đầu tiên (Linux, Windows).
*   **Nhà phát triển API:** Thiết kế SDK bằng Dart/Python để tạo môi trường lập trình app thân thiện nhất.

*Mọi đóng góp, thảo luận hoặc phản biện gạch đá về kiến trúc đều được trân trọng tại mục **Issues** hoặc **Discussions** của Repository này!*
