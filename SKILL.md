---
name: seo-blog-writer
description: "Viết bài blog chuẩn SEO tiếng Việt từ một từ khóa: nghiên cứu nguồn, đề xuất 10 tiêu đề, duyệt dàn ý 9 H2, viết bài và FAQ, tạo bộ ảnh bằng tính năng tạo ảnh của ChatGPT theo số lượng cần thiết, xuất file và tạo bản nháp WordPress khi có kết nối. Dùng khi người dùng yêu cầu bài SEO, nội dung blog hoặc bài website tiếng Việt."
---

# SEO Blog Writer — tiếng Việt

Tạo bài blog hoàn chỉnh từ một từ khóa, với các điểm duyệt tiêu đề và dàn ý. Dùng tính năng tạo ảnh tích hợp của ChatGPT để sản xuất bộ ảnh; không dùng Pexels, không yêu cầu API key tạo ảnh. Chỉ tạo bản nháp WordPress nếu có khả năng truy cập website đã được người dùng chỉ định.

## Đầu vào và công cụ

- Bắt buộc: từ khóa mục tiêu. Nếu thiếu, hỏi một lần.
- Tận dụng thông tin người dùng đã cung cấp: độc giả, thương hiệu, mục tiêu, giọng văn, độ dài, website, số ảnh và phong cách ảnh.
- Mặc định: tiếng Việt, độc giả Việt Nam, 1.800–2.500 từ, 9 H2 nội dung, ảnh ngang 16:9. Điều chỉnh theo yêu cầu rõ ràng của người dùng.
- Suy luận ý định tìm kiếm từ từ khóa: KNOW = tìm hiểu; DO = thực hiện tác vụ; BUY = mua hàng; GO = đến thương hiệu hoặc website. Với từ khóa review/so sánh, xác định nhu cầu tìm hiểu trước khi mua; không mặc định mọi từ khóa là DO.
- Chỉ hỏi thêm nếu thông tin thiếu thực sự làm thay đổi bài viết. Dùng công cụ hỏi người dùng nếu có; nếu không, hỏi trực tiếp. Không gọi tên công cụ của nền tảng khác như AskUserQuestion, WebSearch, Agent hay SendUserFile.
- Nghiên cứu bằng công cụ tìm kiếm web sẵn có; tạo ảnh bằng công cụ image_gen tích hợp; dùng công cụ file/runtime để xuất bài; ưu tiên connector WordPress sẵn có cho bước tạo bản nháp. Kiểm tra công cụ thực tế trước khi gọi, không giả định đã có kết nối.
- Nếu một công cụ không khả dụng, hoàn thành các phần độc lập còn lại và nói rõ phần bị thiếu. Không báo hoàn thành việc chưa thực hiện.

## 0. Nghiên cứu

1. Tìm và đọc 3–5 nguồn liên quan đến từ khóa tiếng Việt; xác định chủ đề phụ, câu hỏi, ý định tìm kiếm và khoảng trống nội dung. Không gọi chúng là kết quả top Google nếu công cụ không cung cấp bằng chứng về thứ hạng.
2. Ưu tiên nguồn gốc/nguồn chính thức cho số liệu, giá, thông tin kỹ thuật và chủ đề sức khỏe, pháp lý, tài chính. Kiểm tra ngày công bố khi nội dung thay đổi theo thời gian.
3. Lập ghi chú nguồn gồm URL, luận điểm được hỗ trợ và ngày khi cần. Không sao chép bài đối thủ, không bịa số liệu, dẫn chứng hay thứ hạng SEO.
4. Nếu không có tìm kiếm web, dùng nguồn người dùng cung cấp và nêu giới hạn nghiên cứu; không tự dựng danh sách nguồn.

## 1. Đề xuất 10 tiêu đề

- Viết 10 tiêu đề tiếng Việt dưới 120 ký tự, chứa từ khóa hoặc biến thể tự nhiên gần đầu, phù hợp độc giả và ý định tìm kiếm.
- Dùng dấu gạch nối khi cần phân tách. Chỉ thêm năm hiện tại khi nội dung thực sự được kiểm tra cho năm đó.
- Tránh giật tít sai lệch và hứa hẹn đạt thứ hạng cao.
- Hiển thị danh sách và chờ người dùng chọn. Nếu họ đã chỉ định tiêu đề hoặc yêu cầu làm toàn bộ tự động, dùng tiêu đề được chỉ định hoặc tự chọn phương án phù hợp, nêu lựa chọn rồi tiếp tục.

## 2. Dàn ý

- Tạo mặc định 9 H2 nội dung, mỗi H2 có 2–3 luận điểm ngắn. Kết luận và FAQ nằm ngoài 9 H2 này.
- Viết tiêu đề phụ rõ nghĩa, tránh lặp từ khóa vào mọi H2. Mặc định dùng tiêu đề khẳng định, không đánh số La Mã.
- Chờ duyệt dàn ý, trừ khi người dùng đã cung cấp dàn ý hoặc yêu cầu làm tự động. Tôn trọng số H2 khác nếu họ chỉ định.

## 3. Viết bài và FAQ

1. Chia dàn ý thành các cụm 2–3 H2 để viết. Khi có công cụ subagent, có thể giao mỗi cụm cho một subagent, kèm tiêu đề, toàn bộ cấu trúc để tránh trùng lặp, độc giả, độ dài phân bổ và nguồn liên quan. Chỉ yêu cầu viết cụm được giao. Nếu không có, viết lần lượt các cụm trong phiên hiện tại.
2. Ghép đúng thứ tự, biên tập toàn bài để thống nhất giọng văn, bỏ lặp ý và cân đối tổng độ dài. Không đưa intro/kết luận vào từng cụm.
3. Mở bài bằng câu hỏi liên quan khi phù hợp; in đậm cụm chứa từ khóa chính một cách tự nhiên.
4. Ưu tiên đoạn ngắn dễ đọc, ví dụ cụ thể. Có ít nhất một bảng 3 cột khi nội dung có thông tin phù hợp để so sánh; không dựng dữ liệu chỉ để tạo bảng.
5. Phân bố từ khóa chính và biến thể theo ngữ nghĩa; không áp mật độ phần trăm hoặc lặp một lần trong mọi câu trả lời FAQ. Tránh nhồi từ khóa và in đậm quá nhiều.
6. Thêm H2 “Kết luận” với lời khuyên và bước tiếp theo phù hợp ý định tìm kiếm.
7. Cuối bài, thêm H2 “Câu hỏi thường gặp”, gồm 6 H3 câu hỏi và câu trả lời hữu ích, không trùng nguyên phần thân bài. Không chèn ảnh trong FAQ.
8. Gắn nguồn cho các khẳng định cần kiểm chứng. Trong file độc lập, chuyển citation của cuộc trò chuyện thành liên kết nguồn Markdown/HTML thật; không để mã citation nội bộ trong bài.

## 4. Tạo bộ ảnh bằng ChatGPT

### Xác định số ảnh

- Ưu tiên số lượng và vị trí người dùng yêu cầu. Nếu họ chưa chỉ định, dùng một ảnh cho mỗi H2 nội dung: mặc định 9 ảnh với dàn ý 9 H2.
- Không tạo ảnh cho kết luận hoặc FAQ. Chỉ thêm ảnh bìa nếu được yêu cầu; khi có ảnh bìa, tổng số ảnh = số ảnh nội dung + 1.
- Với yêu cầu ít ảnh hơn số H2, chọn các phần có giá trị minh họa cao nhất. Với yêu cầu nhiều ảnh hơn, phân bổ thêm ảnh có mục đích rõ ràng; không tạo ảnh dư chỉ để đủ số.
- Lập bảng kế hoạch: mã ảnh, vị trí, chủ thể, prompt, tỷ lệ, alt tiếng Việt, trạng thái. Thông báo tổng số trước khi tạo; đây là cập nhật tiến độ, không phải điểm duyệt mới nếu người dùng đã yêu cầu tạo bộ ảnh.

### Prompt và thực thi hàng loạt

1. Đọc skill imagegen nếu có trong môi trường. Dùng tính năng tạo ảnh tích hợp, không chuyển sang Pexels hoặc API/CLI tạo ảnh bên ngoài.
2. Giữ một phong cách chung cho bộ ảnh. Dùng phong cách người dùng đã chọn; nếu chưa có, chọn ảnh minh họa biên tập đơn giản, chuyên nghiệp, đúng chủ đề.
3. Viết một prompt riêng cho mỗi ảnh: nội dung H2, chủ thể, bối cảnh, phong cách, bố cục, tỷ lệ ngang 16:9 (trừ khi có chỉ định khác), ánh sáng và điều cần tránh. Mặc định không có chữ, logo hoặc watermark.
4. Gọi công cụ tạo ảnh một lần cho mỗi ảnh, tạo lần lượt đến hết số lượng đã lên kế hoạch. Với ảnh mới không truyền tham chiếu; chỉ dùng tham chiếu khi cần nhất quán với ảnh người dùng cung cấp hoặc ảnh đã tạo, theo schema công cụ thực tế.
5. Kiểm tra từng kết quả về mức độ đúng chủ đề, chất lượng và tính nhất quán. Sửa có mục tiêu khi cần, không tính ảnh lỗi hay biến thể bị bỏ vào số ảnh hoàn thành.
6. Cập nhật trạng thái sau mỗi ảnh/cụm ảnh. Nếu bị lỗi hoặc giới hạn công cụ, giữ các ảnh đã hoàn thành, ghi rõ ảnh còn thiếu và prompt tương ứng; khi tiếp tục chỉ tạo phần thiếu. Không thay ảnh thiếu bằng ảnh stock và không báo đã tạo đủ.
7. Khi dùng image_gen trong code mode, hiển thị kết quả bằng generatedImage(result) theo hướng dẫn công cụ. Không in dữ liệu base64. Không tạo ảnh mẫu khi nhiệm vụ hiện tại chỉ là sửa hoặc cài skill.

### Chèn ảnh vào bài

- Chèn ảnh ngay dưới H2 tương ứng, với alt tiếng Việt mô tả nội dung thực tế, không nhồi từ khóa.
- Ảnh tạo sẵn được hiển thị và lưu tự động theo nền tảng; không tải lại chỉ để lưu hoặc hiển thị. Khi bài viết cần một bộ file ảnh để xuất hoặc tải lên WordPress, dùng cơ chế truy xuất file được công cụ hỗ trợ để lấy bản ảnh thực tế. Không đoán đường dẫn hoặc URL.
- Nếu có file ảnh dùng được, đóng gói bài với thư mục ảnh và dùng đường dẫn tương đối, ví dụ `![Mô tả ảnh](images/h2-01.png)`. Lưu bộ deliverable theo quy tắc lưu file của môi trường.
- Nếu chưa lấy được file ảnh, giao bài và ảnh đã hiển thị kèm bảng ánh xạ vị trí; ghi rõ hạn chế ghép ảnh vào file. Không chèn URL giả, đường dẫn không tồn tại hoặc URL tạm chưa được xác minh.
- Dùng công cụ vẽ/plot chính xác cho biểu đồ số liệu hoặc sơ đồ cần chính xác; không dùng ảnh AI làm bằng chứng, ảnh kết quả thực tế hay đồ thị dữ liệu.

## 5. Kiểm tra SEO và xuất file

- Kiểm tra tiêu đề, số H2 đã duyệt, độ dài, nguồn, tính nhất quán, bảng khi phù hợp, kết luận và 6 câu FAQ.
- Kiểm tra ảnh đúng vị trí và số lượng đã yêu cầu. Báo riêng số ảnh hoàn thành và còn thiếu nếu có lỗi; thiếu ảnh không ngăn xuất bản thảo văn bản.
- Đầu file đặt comment `<!-- Meta title: ... -->` và `<!-- Meta description: ... -->`; viết mô tả khoảng 150–160 ký tự khi phù hợp, tự nhiên và chứa từ khóa. Không hứa đây là giới hạn hiển thị cố định của công cụ tìm kiếm.
- Cấu trúc: một H1 tiêu đề → mở bài → các H2 nội dung và ảnh → H2 Kết luận → H2 Câu hỏi thường gặp với 6 H3 → nguồn tham khảo khi cần.
- Xuất file Markdown; xuất thêm HTML nếu cần WordPress. Nếu có ảnh local, bảo đảm tất cả liên kết tương đối trỏ đến file thật.
- Lưu artifact theo chính sách của môi trường, cung cấp liên kết file thực tế; không giả định công cụ SendUserFile tồn tại.

## 6. Tạo bản nháp WordPress

1. Chỉ thực hiện cho website do người dùng chỉ định và trong phạm vi yêu cầu viết bài/tạo draft. Nếu chưa có website hoặc khả năng truy cập, hỏi thông tin còn thiếu; vẫn hoàn thành bản thảo và bộ ảnh trước.
2. Ưu tiên connector WordPress sẵn có. Nếu không có, chỉ dùng REST API khi môi trường có cấu hình xác thực phù hợp. Không yêu cầu dán mật khẩu vào chat; hướng dẫn thiết lập bằng cơ chế nhập bí mật hoặc biến môi trường an toàn.
3. Không hardcode, ghi log hoặc lưu username/password/API key trong skill, bài viết, bộ ảnh hay kho mã. Không tự dựng thông tin xác thực hoặc giả định đã kết nối.
4. Chuyển Markdown thành HTML, giữ bảng, đậm, ảnh và FAQ; bỏ comment metadata và H1 trùng tiêu đề bài. Dùng meta description làm excerpt; không khẳng định đã cấu hình Yoast/RankMath nếu chưa có tích hợp.
5. Khi có file ảnh thực tế và quyền phù hợp, tải ảnh lên Media Library, dùng URL ảnh do WordPress trả về và alt đã chuẩn bị. Đặt featured image nếu có ảnh bìa. Không dùng đường dẫn local hoặc URL sandbox làm src trên website.
6. Tạo post với `status=draft`. Chỉ dùng `status=publish` nếu người dùng yêu cầu đăng công khai. Chỉ sửa post ID có sẵn khi được yêu cầu cập nhật; không ghi đè bài khác.
7. Đọc lại kết quả để xác nhận post ID, trạng thái draft, nội dung và URL ảnh. Khi timeout sau thao tác tạo, kiểm tra draft đã tồn tại trước khi thử lại để tránh bài trùng.
8. Trả link sửa bài thực tế. Nếu không có khả năng đăng, giao file Markdown/HTML và bộ ảnh có sẵn; nói rõ chưa tạo draft trên WordPress.

## Nguyên tắc biên tập

- Viết tiếng Việt rõ ràng, hạn chế thuật ngữ khi không giúp ích.
- Giữ quy trình và yêu cầu người dùng đã duyệt; không hỏi lại thông tin đã có.
- Không hứa thứ hạng, không bịa trải nghiệm cá nhân, review, số liệu, giá hoặc thương hiệu.
- Với sức khỏe, pháp lý và tài chính, dựa vào nguồn có thẩm quyền, nêu giới hạn phù hợp với nội dung; tránh khẳng định chữa bệnh hoặc đưa lời khuyên cá nhân thiếu căn cứ.
