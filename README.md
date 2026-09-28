# 🎬 Phòng lồng tiếng: Cute!

Trang web giúp học sinh 4–10 tuổi luyện nói tiếng Anh bằng cách **lồng tiếng cho nhân vật hoạt hình**.
Học sinh xem video đã xoá giọng (chỉ còn hình, chữ chạy và nhạc nền gốc), thu âm từng câu thoại, rồi ghép thành **video nhân vật gốc với giọng của chính mình**.

Bài hiện có: *Cute!* (Little Fox, Level 1), gồm 9 câu kèm nghĩa tiếng Việt.

## Tính năng

- 🔊 **Nghe mẫu**: nghe giọng đọc gốc của từng câu.
- 🎤 **Thu âm từng câu**: đếm ngược 3-2-1, video chạy kèm nhạc nền, em nói khi chữ chuyển sang màu vàng.
- ▶ **Nghe giọng em**: nghe lại ngay, chưa ưng thì bấm *Thu lại*.
- 🎬 **Ghép video**: ghép giọng em với hình và nhạc nền gốc thành một video.
- ⬇ **Tải video về**: file `.mp4` hoặc `.webm`, đặt tên theo tên học sinh.
- Chạy ngay trên trình duyệt: không cần cài đặt, không cần tài khoản. Dữ liệu thu âm không được gửi đi đâu.

## Cấu trúc thư mục

```
phong-long-tieng/
├── index.html            # Trang lồng tiếng
├── README.md
└── media/
    ├── cute.mp4          # Video đã xoá giọng (nhạc nền + chữ chạy)
    ├── cute-mau.mp3      # Âm thanh gốc có giọng đọc (dùng cho "Nghe mẫu")
    └── cute-poster.jpg   # Ảnh bìa video
```

## Đưa lên GitHub Pages

1. Tạo repository mới trên GitHub, ví dụ `phong-long-tieng`.
2. Tải toàn bộ các file ở trên lên: **Add file → Upload files**, kéo cả thư mục `media` vào, rồi bấm **Commit changes**.
3. Vào **Settings → Pages**. Ở mục *Source*, chọn **Deploy from a branch**, chọn nhánh `main` và thư mục `/ (root)`, rồi bấm **Save**.
4. Sau khoảng 1–2 phút, trang sẽ có địa chỉ:
   `https://<tên-tài-khoản>.github.io/phong-long-tieng/`

> ⚠️ Micro chỉ hoạt động khi trang chạy qua **https** (GitHub Pages có sẵn), hoặc khi mở trên máy bằng một máy chủ cục bộ.
> Nếu mở trực tiếp `index.html` bằng cách nháy đúp, nút *Ghép video* có thể không hoạt động. Hãy dùng link GitHub Pages.

### Chạy thử trên máy tính

```bash
cd phong-long-tieng
python -m http.server 8000
# mở http://localhost:8000
```

## Hướng dẫn cho học sinh

1. Mở trang bằng **Chrome, Edge** (máy tính hoặc Android) hoặc **Safari** (iPad, iPhone).
2. Bấm **Cho phép** khi trình duyệt hỏi quyền dùng micro.
3. 🎧 Đeo tai nghe khi thu âm để nhạc nền không lọt vào micro.
4. Thu từng câu, nghe lại, rồi bấm **Ghép video** và đợi khoảng 2 phút đến khi video chạy hết.
5. Bấm **Tải video về** để nộp bài cho cô.

## Thêm bài mới

1. Chuẩn bị 2 file từ cùng một video:
   - **Video đã xoá giọng**: dùng CapCut (*Isolate voice → Remove vocal*) hoặc [vocal-remover.ai](https://vocal-remover.ai/video-vocal-remover).
   - **Âm thanh gốc**: tách phần tiếng từ video gốc (tuỳ chọn, dùng cho nút *Nghe mẫu*).
2. Chép file vào thư mục `media/`.
3. Mở `index.html` và sửa:
   - Đường dẫn file ở dòng `const VIDEO_SRC = ...` và `const MODEL_SRCS = [...]`.
   - Danh sách câu thoại `CUES`. Mỗi câu có dạng:
     ```js
     {en: "The kitten is cute.", vi: "Mèo con dễ thương.", s: 13.3, e: 16.3}
     ```
     Trong đó `s` là giây bắt đầu nói và `e` là giây kết thúc, xem theo đồng hồ của video.
   - Tiêu đề trong thẻ `<title>` và `<h1>`.
4. Nếu âm thanh gốc bị lệch so với video, chỉnh `ORIG_OFFSET` (tính bằng giây).

## Khi video hoặc âm thanh không chạy

| Hiện tượng | Cách xử lý |
|---|---|
| Khung báo *"Không tải được media/cute.mp4"* | Thư mục `media` chưa được tải lên GitHub, hoặc tên file bị sai. Vào repository kiểm tra xem có đủ `media/cute.mp4`, `media/cute-mau.mp3`, `media/cute-poster.jpg` không (tên phân biệt chữ hoa/thường). |
| Khung báo *"Bạn đang mở file trực tiếp"* | Trang đang được mở bằng cách nháy đúp `index.html`. Hãy mở bằng link GitHub Pages, hoặc dùng bản một-file `Phong_long_tieng_Cute.html`. |
| Link GitHub báo lỗi 404 | GitHub Pages chưa bật, hoặc chưa chạy xong. Kiểm tra lại mục **Settings → Pages** và đợi 1–2 phút. |
| Bấm nút mà không nghe thấy gì | Kiểm tra âm lượng máy, và tắt chế độ im lặng trên iPhone/iPad (công tắc bên hông máy). Sau đó bấm lại nút. |
| Không thu được âm | Bấm vào biểu tượng ổ khoá trên thanh địa chỉ, chọn **Micro → Cho phép**, rồi tải lại trang. |

## Lưu ý bản quyền

Video mẫu *Cute!* thuộc bản quyền © Little Fox Co., Ltd. và chỉ dùng cho mục đích học tập trong lớp.
Nếu để repository ở chế độ **công khai**, thầy cô nên thay bằng video tự làm hoặc video được phép chia sẻ.

## Công nghệ

HTML, CSS và JavaScript thuần, không dùng thư viện. Trang dùng Web Audio API để trộn giọng với nhạc nền, MediaRecorder để thu âm và ghi video, và Canvas `captureStream` để ghép hình.
