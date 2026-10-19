# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** [Điền họ và tên của bạn]
- **MSSV:** [Điền MSSV]
- **Tên đề tài Website:** Harmony Music VIP – Giao diện website nghe nhạc
- **Công cụ AI đã sử dụng:** ChatGPT

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> Hãy tạo giao diện website nghe nhạc có tên Harmony Music VIP bằng HTML5 và CSS. Giao diện sử dụng phong cách dark mode hiện đại, hiệu ứng gradient tím/hồng/xanh cyan, thẻ album dạng đĩa vinyl, danh sách bài hát, khu vực lời bài hát và thanh trình phát nhạc cố định ở cuối trang. Website cần có bố cục rõ ràng, đẹp mắt và responsive trên máy tính lẫn điện thoại. Sử dụng CSS Variables để quản lý màu sắc và Flexbox/Grid để bố trí các thành phần.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variable

- **Prompt đã dùng:**
  > Tạo cấu trúc HTML cho website Harmony Music VIP. Sử dụng các thẻ semantic HTML5 phù hợp như `header`, `nav`, `main`, `section`, `article` và `footer`. Tách phần định dạng CSS ra file `style.css`, sử dụng các biến trong `:root` để quản lý màu sắc và giữ bố cục responsive bằng CSS Grid và Flexbox.

- **Kết quả AI tạo ra:**
  > AI tạo khung website gồm phần đầu trang, khu vực giới thiệu album, khu vực thông tin bài hát, danh sách phát và thanh trình phát ở chân trang. CSS được tổ chức riêng trong file `style.css`, có sử dụng biến màu, gradient và media query.

- **Nhận xét & Tinh chỉnh của SV:**
  > Tôi yêu cầu tách CSS khỏi HTML để mã nguồn dễ quản lý và chỉnh sửa. Tôi cũng rà soát cấu trúc để dùng `main`, `section`, `article`, `header` và `footer` đúng mục đích, hạn chế dùng `div` cho các khối nội dung có ý nghĩa ngữ nghĩa.

### Lần 2: Tích hợp thư viện Animate.css & AOS

- **Prompt đã dùng:**
  > Kiểm tra cách trình bày website và bổ sung hiệu ứng chuyển động vừa phải cho các thành phần chính. Nếu sử dụng Animate.css hoặc AOS thì hãy đảm bảo thư viện được liên kết và khởi tạo đúng cách; tránh dùng hiệu ứng quá nhiều gây mất tập trung.

- **Kết quả AI tạo ra:**
  > Bản giao diện ban đầu có liên kết đến thư viện Animate.css và AOS, đồng thời dùng các thuộc tính như `data-aos` để chỉ định hiệu ứng khi cuộn trang. Trong bản HTML tĩnh cuối cùng, phần JavaScript đã được loại bỏ theo yêu cầu nên AOS không được khởi tạo và các hiệu ứng AOS không hoạt động. Một số hiệu ứng trang trí như đĩa vinyl, equalizer và hover vẫn được thực hiện trực tiếp bằng CSS.

- **Nhận xét & Tinh chỉnh của SV:**
  > Tôi ưu tiên yêu cầu hiện tại là không sử dụng file JavaScript. Vì vậy, tôi giữ các hiệu ứng CSS thuần và không sử dụng AOS như một hiệu ứng cuộn đang hoạt động. Nếu giảng viên yêu cầu bắt buộc AOS hoạt động, cần trao đổi lại vì AOS thường cần JavaScript để khởi tạo.

- **Thách thức gặp phải:**
  > Cân bằng giữa yêu cầu giao diện có hiệu ứng sinh động và yêu cầu loại bỏ JavaScript. AOS cần JavaScript để khởi tạo, nên không thể đảm bảo hiệu ứng xuất hiện khi cuộn nếu không có JavaScript.

- **Cách sửa prompt (Debug prompt):**
  > Hãy giữ website ở dạng HTML và CSS tĩnh, không tạo file `.js` và không thêm thẻ script. Dùng CSS animation, transition, `:hover`, `:focus-visible` và media query để tạo hiệu ứng thay thế. Ghi rõ trong báo cáo những hiệu ứng nào không hoạt động do đã bỏ JavaScript.

### Lần 3: Tách CSS và loại bỏ JavaScript

- **Prompt đã dùng:**
  > Tách toàn bộ CSS trong HTML thành file `style.css`, giữ file HTML riêng và bỏ toàn bộ JavaScript. Không tạo file JavaScript. Giữ phong cách dark mode, gradient, bố cục danh sách bài hát và thanh phát nhạc cố định.

- **Kết quả AI tạo ra:**
  > Website được chia thành hai file `index.html` và `style.css`. HTML tham chiếu CSS bằng đường dẫn tương đối `style.css`. Các phần tử giao diện như danh sách bài hát, thông tin bài hát và thanh điều khiển được trình bày tĩnh.

- **Nhận xét & Tinh chỉnh của SV:**
  > Tôi kiểm tra lại để hai file nằm trong cùng thư mục và không còn mã JavaScript. Vì không dùng JavaScript, các nút phát/dừng, chuyển bài, tìm kiếm, yêu thích và điều chỉnh âm lượng chỉ là thành phần giao diện, không thực hiện chức năng thật.

### Lần 4: Hoàn thiện bố cục và khả năng responsive

- **Prompt đã dùng:**
  > Rà soát CSS để giao diện hiển thị tốt trên màn hình nhỏ. Sử dụng CSS Grid/Flexbox, điều chỉnh kích thước tiêu đề, danh sách bài hát, thanh trình phát và khoảng cách ở các breakpoint. Bổ sung trạng thái hover và hỗ trợ `prefers-reduced-motion`.

- **Kết quả AI tạo ra:**
  > CSS có các media query cho màn hình vừa và nhỏ, hiệu ứng hover trên thẻ bài hát, animation cho đĩa vinyl và equalizer, cùng quy tắc giảm chuyển động khi người dùng bật tùy chọn giảm hiệu ứng trong hệ điều hành.

- **Nhận xét & Tinh chỉnh của SV:**
  > Tôi ưu tiên bố cục dễ nhìn, màu sắc thống nhất và tránh để thanh trình phát che mất nội dung. Các đường dẫn ảnh và font được tải từ dịch vụ bên ngoài nên cần có kết nối Internet để hiển thị đầy đủ.

## 3. Đánh giá cá nhân về quá trình Vibe Coding

- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?**
  > AI giúp tôi tạo nhanh bố cục ban đầu, đề xuất bảng màu, thiết lập CSS Variables, viết các hiệu ứng CSS và điều chỉnh giao diện responsive. Nhờ đó, tôi có thể tập trung kiểm tra cấu trúc, nội dung và tinh chỉnh thiết kế thay vì viết toàn bộ mã từ đầu.

- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?**
  > Prompt cần nêu rõ mục tiêu website, phong cách giao diện, cấu trúc HTML mong muốn, cách tổ chức file và các giới hạn kỹ thuật. Khi tinh chỉnh, nên yêu cầu từng thay đổi cụ thể, kiểm tra kết quả sau mỗi lần và chỉ ra những phần chưa đạt yêu cầu. Cần tự kiểm tra mã do AI tạo ra, vì giao diện đẹp chưa chắc đã đáp ứng đầy đủ yêu cầu kỹ thuật của đề bài.

## 4. Tự kiểm tra trước khi nộp

- [ ] Đã điền họ tên và MSSV.
- [ ] Repository được đặt tên đúng định dạng `Ten_Ho_MSSV`.
- [ ] Có `index.html` và `style.css` trong repository.
- [ ] Đường dẫn CSS trong HTML là đường dẫn tương đối: `style.css`.
- [ ] Đã kiểm tra website sau khi tải lên GitHub Pages.
- [ ] Đã thêm đường dẫn GitHub Pages vào phần mô tả repository.
- [ ] Đã kiểm tra yêu cầu thư viện của giảng viên. Lưu ý: bản hiện tại không dùng JavaScript, vì vậy AOS không được khởi tạo và các nút điều khiển nhạc chỉ là giao diện tĩnh.
