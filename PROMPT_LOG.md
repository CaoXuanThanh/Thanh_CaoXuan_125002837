# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Cao Xuân Thành
- **MSSV:** 125002837
- **Tên đề tài Website:** School Camera Access — Website quản lý và phân quyền truy cập camera trường học cho phụ huynh
- **Công cụ AI đã sử dụng:** ChatGPT

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> Xây dựng website một trang cho đề tài “School Camera Access”.
> Website mô phỏng bài toán phụ huynh dùng chung tài khoản camera lớp nên khó thu hồi quyền riêng.
> Yêu cầu dùng Semantic HTML5 gồm header, nav, main, section/article và footer;
> CSS Variables cho màu sắc, font và spacing; Flexbox/Grid để responsive;
> tích hợp Animate.css và AOS; có :hover và :focus tự viết.
> Không thêm backend, database hoặc chức năng JavaScript nghiệp vụ ngoài phạm vi đề.

**Kết quả AI tạo ra:** Khung website gồm Hero, Bài toán, Chức năng, Camera mẫu,
Phân quyền mẫu và Footer.

**Nhận xét & Tinh chỉnh của SV:** Bản đầu có thêm JavaScript tương tác cho lọc camera,
toggle quyền và tìm kiếm. Sau khi đối chiếu lại đề, tôi yêu cầu bỏ toàn bộ JavaScript
nghiệp vụ vì đề không có tiêu chí JavaScript; chỉ giữ đoạn khởi tạo AOS do thư viện
AOS bắt buộc phải được tích hợp.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variable

- **Prompt đã dùng:**

> Kiểm tra cấu trúc HTML theo đúng Semantic HTML5. Hạn chế div vô nghĩa,
> dùng header, nav, main, section, article, aside và footer đúng vai trò.
> Tạo :root chứa CSS Variables cho color, font, spacing, radius và shadow.

- **Kết quả AI tạo ra:** Website có đủ các thẻ semantic chính; toàn bộ màu,
spacing, radius và font được quản lý bằng CSS Variables.

- **Nhận xét & Tinh chỉnh của SV:** Cấu trúc rõ ràng hơn và dễ giải thích;
các biến CSS giúp giao diện nhất quán.

### Lần 2: Flexbox / Grid và Responsive

- **Prompt đã dùng:**

> Dùng CSS Grid cho Hero, nhóm card và khu phân quyền; dùng Flexbox cho Header,
> Footer và các hàng thông tin. Thêm breakpoint để mobile không bị tràn ngang.

- **Kết quả AI tạo ra:** Hero và permission dùng Grid 2 cột; các card dùng Grid 3 cột;
Header/Footer dùng Flexbox; mobile chuyển về một cột.

- **Nhận xét & Tinh chỉnh của SV:** Grid phù hợp bố cục nhiều cột,
Flexbox phù hợp các hàng ngang.

### Lần 3: Animate.css và AOS

- **Prompt đã dùng:**

> Tích hợp Animate.css và AOS qua CDN. Animate.css chỉ dùng cho Hero khi tải trang;
> AOS dùng cho section và card khi cuộn. Hiệu ứng vừa đủ, không lạm dụng.

- **Kết quả AI tạo ra:** Hero dùng `animate__fadeInLeft` và `animate__fadeInRight`;
section dùng `data-aos="fade-up"`; camera card dùng `data-aos="zoom-in"`.

- **Thách thức gặp phải:** AOS cần được khởi tạo sau khi tải thư viện.

- **Cách sửa prompt (Debug prompt):**

> Giữ JavaScript ở mức tối thiểu chỉ để `AOS.init()` hoạt động.
> Không tạo file JavaScript riêng và không thêm logic nghiệp vụ vì đề không yêu cầu JavaScript.

### Lần 4: Hover / Focus và độ mượt

- **Prompt đã dùng:**

> Tạo trạng thái :hover và :focus-visible rõ cho nút, link và card.
> Dùng transform cho chuyển động nhỏ, transition khoảng 220ms,
> tránh hiệu ứng quá mạnh hoặc lạm dụng animation.

- **Kết quả AI tạo ra:** Card nâng nhẹ khi hover/focus, nút đổi màu và dịch nhẹ,
keyboard focus có outline rõ.

## 3. Đánh giá cá nhân về quá trình Vibe Coding

### AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?

AI giúp dựng nhanh khung Semantic HTML, hệ CSS Variables, Flexbox/Grid,
responsive và tích hợp thư viện hiệu ứng.

### Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?

Cần đọc kỹ đề và giới hạn phạm vi rõ ràng. Nếu prompt không nói những gì không cần làm,
AI có thể tự thêm chức năng vượt yêu cầu. Việc đối chiếu rubric sau mỗi vòng giúp phát hiện
phần dư thừa và yêu cầu AI tinh chỉnh đúng mục tiêu bài thi.
