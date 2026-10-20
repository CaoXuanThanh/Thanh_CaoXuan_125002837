# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Cao Xuân Thành
- **MSSV:** 125002837
- **Tên đề tài Website:** NOIR. — Curated Cinema Archive
- **Công cụ AI đã sử dụng:** ChatGPT

## 1. Yêu cầu ban đầu

> Thiết kế website chủ đề điện ảnh theo phong cách cao cấp, khác với landing page thông thường. Bài phải dùng Semantic HTML5, CSS Variables, Flexbox/Grid, Animate.css, AOS và hover/focus; giao diện cần đủ ấn tượng khi mở trực tiếp trên GitHub Pages.

**Kết quả ban đầu:** Có hai hướng thiết kế: một bản editorial hiện đại, thiên về typography/illustration; một bản cinema archive cổ điển, dùng ảnh thật, tông vàng và font serif.

**Nhận xét của SV:** Hai hướng đều có điểm mạnh nhưng chưa muốn chọn bỏ hẳn một hướng. Tôi yêu cầu AI phân tích rồi hợp nhất các điểm mạnh thay vì chỉ đổi màu hoặc sao chép nguyên một mẫu.

## 2. Quá trình tinh chỉnh

### Lần 1 — Chọn visual direction cuối

- **Prompt:**

> Lấy bố cục điện ảnh mạnh, hero có chiều sâu, editorial statement và visual hierarchy của mẫu hiện đại; kết hợp film grain, ảnh thật, màu vàng cổ điển, typography sang trọng, poster archive, bento collections và membership của mẫu cinema archive. Không để giao diện giống bài tập sinh viên.

- **Kết quả:**
  - Hero dùng ảnh điện ảnh toàn màn hình, overlay nhiều lớp, light beam và typography lớn.
  - Giữ glass cards cho Premiere/Rating để hero có chiều sâu.
  - Dùng palette đen/navy + antique gold/cream.
  - Dùng Cinzel cho display, Cormorant Garamond cho chữ italic và Plus Jakarta Sans cho body.

### Lần 2 — Sửa lỗi hero bị chồng CTA và progress

- **Vấn đề:** Ở bản trước, CTA và chỉ số `01 / 04` nằm quá gần nhau nên khi chiều cao màn hình thấp chúng có cảm giác bị đè lên nhau.

- **Debug prompt:**

> Không vá bằng margin ngẫu nhiên. Tách hero thành hai hàng độc lập: nội dung chính và hero-bottom. Hero phải tự tăng chiều cao khi nội dung nhiều; progress bar luôn ở hàng dưới và không thể chồng lên CTA.

- **Kết quả:** Hero dùng CSS Grid `grid-template-rows: 1fr auto`; CTA nằm trong `hero-main`, còn pagination/scroll prompt nằm trong `hero-bottom` độc lập.

### Lần 3 — Semantic HTML5

- **Prompt:**

> Audit HTML: dùng header/nav/main/section/article/aside/footer đúng ngữ nghĩa. Poster phim, thẻ Premiere/Rating và membership card phải là thành phần semantic hợp lý; hạn chế div chỉ để layout.

- **Kết quả:** Header/nav/main/section/article/aside/footer được sử dụng xuyên suốt; các vùng độc lập có heading/aria phù hợp.

### Lần 4 — CSS Variables + Flexbox/Grid

- **Prompt:**

> Gom màu, typography, spacing, radius, transition vào CSS Variables. Grid dùng cho hero, archive, feature, bento và membership; Flexbox dùng cho navigation, CTA, meta và footer. Không hard-code style rời rạc nếu có thể dùng token chung.

- **Kết quả:** Toàn site dùng một design system gồm `--bg-deep`, `--gold`, `--cream`, `--text-main`, `--line`, font variables, gutter, radius và transition.

### Lần 5 — Animate.css + AOS

- **Prompt:**

> Dùng Animate.css cho phần xuất hiện đầu tiên của header/hero. Dùng AOS cho các section/poster/bento/membership khi cuộn. Giữ hiệu ứng vừa phải, không animate mọi phần tử.

- **Kết quả:** Header/hero dùng Animate.css; archive, manifesto, feature, bento và membership dùng AOS. AOS chạy một lần với duration 900ms.

### Lần 6 — Hover/Focus + cảm giác thương mại

- **Prompt:**

> Làm hover/focus rõ cho nav, button, poster, bento và link. Poster phải có zoom ảnh nhẹ + overlay “OPEN FILM”, nhưng không làm rối mắt. Keyboard focus phải nhìn thấy được.

- **Kết quả:** Poster có transform/overlay, nav có underline transition, button có lift/shadow, bento zoom ảnh; `:focus-visible` có outline màu gold.

### Lần 7 — Responsive

- **Prompt:**

> Desktop ưu tiên cinematic layout. Tablet giảm navigation, mobile dùng details/summary để mở menu mà không cần JavaScript nghiệp vụ. Hero, poster grid, bento và membership phải giảm cột hợp lý và không tràn ngang.

- **Kết quả:** Có breakpoint 1180px, 900px và 640px; mobile menu hoạt động không cần JS riêng.

## 3. Đánh giá cá nhân

### AI giúp tiết kiệm thời gian ở đâu?
AI giúp dựng nhanh các layout Grid/Flexbox, tạo hệ CSS Variables, thử nhiều visual direction và sửa nhanh các lỗi spacing/responsive. Phần cần con người quyết định nhiều nhất là chọn phong cách, loại bỏ chi tiết làm giao diện giống template và đánh giá xem visual hierarchy đã đủ thuyết phục chưa.

### Bài học khi prompt AI trong thiết kế web
Yêu cầu “làm đẹp” là chưa đủ. Prompt hiệu quả phải nói rõ loại sản phẩm, mood, typography, hierarchy, phần nào cần giữ, phần nào cần bỏ, kỹ thuật bắt buộc và cả những lỗi cụ thể quan sát được. Việc so sánh hai phương án rồi yêu cầu hợp nhất theo tiêu chí rõ ràng cho kết quả tốt hơn chọn một mẫu và chỉnh màu.
