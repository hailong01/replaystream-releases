# ReplayStream Commercial

Bộ cài chính thức và thông tin cập nhật có chữ ký cho ReplayStream Commercial trên Windows.

**[Tải phiên bản mới nhất](https://github.com/hailong01/replaystream-releases/releases/latest)** · Gia hạn / hỗ trợ: **Zalo 0984 191 333**.

## Cấu hình máy: chọn theo cách phát

**Không bắt buộc có RTX 3060 hoặc card đồ họa rời.** Với chế độ **Chuẩn bị trước**, video được xử lý một lần và lúc phát chủ yếu gửi dữ liệu đã mã hóa. Chế độ **Phát ngay** vẫn giải mã, đổi kích thước và mã hóa trong suốt phiên nên cần máy mạnh hơn. Cách sao chép luồng không phải mã hóa lại được mô tả trong [tài liệu FFmpeg](https://ffmpeg.org/ffmpeg.html#Streamcopy).

### Mức thấp nhất đề xuất để thử: 1 luồng, Chuẩn bị trước

| Thành phần | Mốc đề xuất ban đầu |
| --- | --- |
| Hệ điều hành | Windows 10 22H2 64-bit hoặc Windows 11 64-bit; ưu tiên Windows 11 |
| CPU | Intel/AMD x64, từ 2 nhân / 4 luồng; phải tương thích bản FFmpeg sử dụng, ưu tiên CPU có AVX2 |
| RAM | Từ 8 GB; hạn chế mở nhiều tab trình duyệt và giả lập cùng lúc |
| Ổ lưu trữ | Ưu tiên SSD; chừa ít nhất 20 GB, cộng thêm chỗ cho video gốc và bản chuẩn bị |
| Card đồ họa | Không bắt buộc card rời nếu chuẩn bị bằng CPU và phát từ bản đã chuẩn bị |
| Mạng | Upload ổn định khoảng 10 Mbps trở lên cho 1 luồng 1080p, video 6.000 kbps |
| Cách dùng | Chuẩn bị video xong trước giờ live; có thể bắt đầu 720p nếu máy xử lý chậm |

**Đây là mốc đề xuất để thử, chưa phải cấu hình tối thiểu đã được chứng nhận trên máy yếu.** Chúng tôi chưa thử trực tiếp mọi máy 2 nhân / RAM 8 GB nên không cam kết đây là máy yếu nhất tuyệt đối hoặc bảo đảm 1080p trên mọi máy. Thời gian chuẩn bị có thể lâu hơn thời lượng video. Hãy gửi cấu hình máy qua Zalo và chạy thử trước khi mua gói nhiều luồng.

### Cấu hình khuyến nghị theo nhu cầu

| Nhu cầu | CPU đề xuất | RAM đề xuất | Chế độ ưu tiên | Upload gợi ý |
| --- | --- | --- | --- | --- |
| 1 luồng, tiết kiệm cấu hình | Từ 2 nhân / 4 luồng x64 | 8 GB | Chuẩn bị trước | 10 Mbps trở lên |
| 2-3 luồng | Từ 4 nhân / 8 luồng x64 | 16 GB | Chuẩn bị trước | 20-30 Mbps trở lên |
| 4-6 luồng | Từ 6 nhân / 12 luồng x64 | 16 GB; nên 32 GB nếu chạy thêm nhiều ứng dụng | Chuẩn bị trước | 40-60 Mbps trở lên |
| 1 luồng 1080p mã hóa ngay | Từ 6 nhân / 12 luồng là mốc tham khảo | 16 GB | GPU H.264 tương thích hoặc CPU qua bài thử thực tế | 10 Mbps trở lên |
| Nhiều luồng mã hóa ngay | Cần kiểm tra trên chính máy sử dụng; không suy ra từ tên CPU/GPU | Từ 16 GB, cân nhắc 32 GB | Nên chuyển sang Chuẩn bị trước khi máy không theo kịp | Tính theo số luồng và bitrate |

Các dòng trên là **khuyến nghị tư vấn, không phải kết quả chứng nhận cho từng cấu hình**. Quyền gói 6 luồng cho phép tạo tối đa 6 đầu ra; không đồng nghĩa mọi máy phát được 6 luồng mã hóa trực tiếp.

### Phần mềm và GPU

- Cần Microsoft Edge WebView2 Runtime và FFmpeg/FFprobe tương thích. Không cần cài Python hoặc Node để dùng bộ cài khách. Bộ cài hiện không kèm FFmpeg; xem hướng dẫn trong ứng dụng.
- Bản Windows dành cho CPU Intel/AMD x64. Chưa kiểm chứng Windows ARM64; không có bản chạy trực tiếp trên macOS, Linux, Android hoặc iPhone.
- Chế độ GPU chỉ dùng khi bộ mã hóa H.264 và driver hoạt động qua bài kiểm tra của tool. Tên card không đủ để bảo đảm khả năng mã hóa hoặc số phiên đồng thời.
- Đã thử bộ mã hóa NVIDIA NVENC trên RTX 3060 Laptop. Intel Quick Sync/AMD AMF còn phụ thuộc GPU, driver và bản FFmpeg trên từng máy. Số phiên mã hóa GPU có thể chịu giới hạn của phần cứng/driver; xem [tài liệu NVIDIA](https://docs.nvidia.com/video-technologies/video-codec-sdk/13.1/nvenc-application-note/index.html).
- Có thể dùng CPU để chuẩn bị video ngay cả khi không có GPU phù hợp. Lúc gửi bản đã chuẩn bị, không cần GPU mã hóa video lại.
- WebView2 có yêu cầu hệ điều hành riêng; tham khảo [Microsoft WebView2](https://learn.microsoft.com/en-us/microsoft-edge/webview2/).

### Mạng và dung lượng

Các con số upload trong bảng dành cho **1080p30, video 6.000 kbps và audio khoảng 128 kbps mỗi đầu ra**, cộng khoảng 50% dự phòng rồi làm tròn. Đây là phép tính dung lượng gửi, không phải cam kết chất lượng Facebook. 6 đầu ra dùng khoảng 36,8 Mbps dữ liệu âm thanh/hình ảnh trước dự phòng; nên dành khoảng 60 Mbps upload ổn định cho tool.

- Quan tâm tốc độ **upload**, không phải download. Nên dùng dây mạng; tránh dùng chung đường truyền với tải lên dung lượng lớn.
- Video đã chuẩn bị ở 6.000 + 128 kbps cần xấp xỉ **2,8 GB mỗi giờ cho một bản chuẩn bị**. Video gốc, cấu hình chất lượng khác và cache bổ sung chiếm thêm dung lượng. Giữ nguyên cùng bản chuẩn bị để phát lại không nhân dung lượng theo số lần phát.
- Chất lượng người xem nhận còn phụ thuộc video gốc, mạng và Facebook. Không cam kết cứ chọn 1080p hoặc một loại GPU là Facebook luôn phân phối 1080p.
- Phải giữ máy bật, ứng dụng mở và mạng hoạt động suốt phiên; không để máy sleep. Đây là bộ phát trên máy Windows, không phải dịch vụ phát hộ trên máy chủ.

## Đã kiểm tra thực tế những gì?

Ngày 04/11/2026: thử cục bộ trên Ryzen 7 5800H, 8 nhân / 16 luồng; Windows 10 Pro 64-bit; RAM Windows ghi nhận khoảng 28 GB; RTX 3060 Laptop và Radeon tích hợp.

Video mẫu tự tạo 1440 x 2560 được đưa về 1080 x 1920, 30 fps, cấu hình video 6.000 kbps + AAC. Mỗi lượt dùng clip khoảng 12 giây, nhận bằng RTMP vòng lặp trên cùng máy. Kết quả:

| Chế độ | Số đầu ra | CPU trung bình phần FFmpeg, tính trên toàn máy | RAM đỉnh cộng dồn phần FFmpeg |
| --- | --- | --- | --- |
| Bản đã chuẩn bị | 1 | 0,18% | 20,6 MB |
| Bản đã chuẩn bị | 3 | 0,58% | 61,8 MB |
| Bản đã chuẩn bị | 6 | 1,08% | 122,1 MB |
| Phát ngay, CPU | 1 | 11,60% | 746,9 MB |
| Phát ngay, NVIDIA NVENC | 1 | 1,63% | 649,8 MB |

Các lượt trên hoàn tất; đầu ra đúng 1080 x 1920 và bộ phát không báo bỏ khung hình. **CPU/RAM trong bảng chỉ là các tiến trình FFmpeg gửi đi**, không gồm giao diện tool, WebView2, Windows, bộ nhận thử và các ứng dụng khác; không được hiểu là tổng RAM máy cần dùng. Phép đo GPU không gồm VRAM. Clip ngắn không đủ để kết luận khả năng mã hóa liên tục nhiều giờ.

Đây **không phải** thử trên máy cấu hình tối thiểu, không phải thử mạng Internet/Facebook, không xác nhận 6 luồng Facebook 1080p dài giờ và không thay thế thử tải trên máy khách. Đã có thêm kiểm thử giới hạn giấy phép 6 luồng và chặn luồng thứ 7.

## Kiểm tra trước khi dùng chính thức

1. Gửi CPU, RAM, GPU và tốc độ upload cho người hỗ trợ; không gửi mật khẩu hoặc khóa phát.
2. Chọn một video thật sẽ sử dụng, chuẩn bị trước ở cấu hình cần phát.
3. Thử 1 luồng 15-30 phút. Sau đó tăng dần số luồng, quan sát tốc độ xử lý, khung bỏ, tải máy và Live Producer. Không dùng một bài thử ngắn làm bằng chứng ổn định cho phiên dài.
4. Nếu máy đuối: dùng Chuẩn bị trước; giảm số luồng hoặc chất lượng. Không nên chọn GPU chỉ theo tên card.

## Bản quyền và cập nhật

Sử dụng ứng dụng cần giấy phép hợp lệ theo mã máy. Từ bản 1.0.6, ứng dụng có sẵn nguồn cập nhật GitHub: khi có bản mới, chuông có chấm đỏ; khách chủ động cập nhật khi đã dừng mọi luồng và hủy lịch chờ. Khách bản cũ cần cài 1.0.6 một lần để có nguồn cập nhật.

Kho này chỉ phân phối bộ cài khách và thông tin cập nhật. Mã nguồn ứng dụng, khóa quản trị và dữ liệu khách không được đưa vào kho.
