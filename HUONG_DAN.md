# Phòng làm bài trực tuyến · Vật lí 10 · Chương II · Mở rộng cuối bài (Bài 8–12)

Cùng động cơ và cách dùng với phòng khối 12 Chương 2 Chất khí: học sinh vào bằng link, nhập họ tên là làm được, không cần tài khoản. Giáo viên vào `/teacher` bằng mật khẩu để mở câu, đóng câu, xem % đúng và danh sách đúng/sai, in phiếu, xuất Word, tải kết quả `.csv`.

**Nội dung**: 184 câu (121 trắc nghiệm, 27 đúng sai, 36 trả lời ngắn), lấy từ phần "Mở rộng cuối bài" Chương II trong Hồ sơ dạy học số (chép từ bản scan `Quân -Ch2ly.pdf`, tr. 22–58). Chia **7 nhóm** theo bài và dạng:

| Nhóm | Nội dung | Số câu |
|---|---|---|
| 1 | Bài 8. Chuyển động biến đổi. Gia tốc | 11 |
| 2 | Bài 9 · Dạng 1. Phương trình và công thức của chuyển động thẳng biến đổi đều | 46 |
| 3 | Bài 9 · Dạng 2. Đồ thị vận tốc – thời gian | 25 |
| 4 | Bài 10. Sự rơi tự do | 27 |
| 5 | Bài 11. Thực hành: Đo gia tốc rơi tự do | 19 |
| 6 | Bài 12 · Dạng 1. Chuyển động ném ngang | 28 |
| 7 | Bài 12 · Dạng 2. Chuyển động ném xiên | 28 |

Mã câu: `B9-D2-I-05` = Bài 9, Dạng 2, Phần I, câu 5 (khớp với số câu trong file Word mở rộng cuối bài của từng bài).

**Cần biết về đáp án**
- Bản scan gốc không có đáp án. Đáp án và lời giải do Claude soạn bổ sung, **giáo viên cần duyệt** (danh sách câu cần xem kĩ ở `VIEC_LAM_TIEP_K10.md` trong kho hồ sơ).
- Câu B10-I-12 (công thức vận tốc chạm đất, tr. 40) **chưa đưa vào phòng** vì bản gốc không có phương án đúng. Sửa một phương án thành $v=\sqrt{2gh}$ trong nguồn rồi tạo lại dữ liệu là câu sẽ có.
- Trả lời ngắn: có đáp án lẻ thì nhận sai lệch dưới nửa đơn vị chữ số cuối (ví dụ đáp án 13,3 nhận 13,3 và 13,34). Hai câu đáp án âm nhận cả độ lớn: B8-III-01 (−3,3 hoặc 3,3), B9-D1-III-08 (−1 hoặc 1).
- Ô trả lời ngắn có nút **±** để thêm/bỏ dấu trừ (bàn phím số của điện thoại, nhất là iPhone, không có phím "-"). Máy chấm nhận các kiểu dấu trừ "-", "−", "–" và cả dấu phẩy lẫn dấu chấm.

**Ba kiểu mở câu** (trang giáo viên, dòng "Mở câu theo"):
1. **Nhóm (buổi) · 7 nhóm**: chọn nhóm, "Mở câu" mở câu kế tiếp, "Mở hết bộ này" mở cả nhóm.
2. **Đề ôn trộn ngẫu nhiên · 18 TN – 4 ĐS – 6 TLN**: bốc ngẫu nhiên từ toàn chương các câu chưa mở (đề sau không trùng đề trước). Phải "Đóng tất cả & hiện đáp án" rồi mới soạn đề tiếp. Ngân hàng đủ cho khoảng 6 đề.
3. **Dạng câu · lộn xộn toàn chương**: 3 tab Trắc nghiệm / Đúng sai / Trả lời ngắn, mở 1 hoặc 5 câu ngẫu nhiên.

**In giấy** và **Xuất Word (.docx)**: ở trang giáo viên, cho câu đang mở, các câu đã mở hoặc cả một nhóm; tick "kèm đáp án" để có bản giáo viên. File Word có công thức là Equation của Word.

## Tạo lại dữ liệu (khi sửa câu hỏi hoặc đáp án)
Sửa nguồn ở kho hồ sơ `D:\Hồ sơ dạy học số\tools\k10_chuong2_mo_rong\src\p*.txt` (dòng `=> ` là đáp án, `=: ` là lời giải), rồi:
1. `python -I -X utf8 tools/k10_chuong2_mo_rong/dung.py "<Quân -Ch2ly.pdf>"` (dựng lại trang hồ sơ, Word, hình)
2. `python -I -X utf8 tools/k10_chuong2_mo_rong/tao_phong.py D:\phong-k10-chuong2-mo-rong` (sinh `data/*.json`, `public/img`, `nguon-goc/*.docx`)
3. Trong kho phòng: `node tools/kiem_tra.js` (đúng định dạng, đáp án gốc được chấm đúng, đủ ảnh).

## Cách 1. Chạy trên laptop của giáo viên (cả lớp cùng Wi-Fi)
1. Cài Node.js (bản LTS) từ nodejs.org, nếu máy chưa có.
2. Bấm đôi `chay-tren-may.bat`, nhập mật khẩu giáo viên (gõ không dấu).
3. Cửa sổ hiện dòng **Cung Wi-Fi: http://192.168.x.x:3000/**. Học sinh mở địa chỉ đó. Giáo viên mở thêm `/teacher`.

## Cách 2. Đưa lên mạng bằng Render (học sinh vào từ bất kì đâu)
1. Tạo kho GitHub riêng cho phòng này (Public, không tick README), tên đã tạo: `Ch-ng-II-Ph-n-m-r-ng-cu-i-b-i` (GitHub tự bỏ dấu từ "Chương II · Phần mở rộng cuối bài").
2. Đẩy mã lên kho đó (nhờ Claude).
3. Trên Render: **Configure account** để cấp quyền cho kho mới, rồi **New, Blueprint**, chọn kho. Render đọc `render.yaml` (dịch vụ `phong-k10-chuong2-mo-rong`).
4. Ở ô `TEACHER_PASS`, **tự nhập** mật khẩu giáo viên (không ghi vào kho GitHub). Bấm **Apply**.
5. Địa chỉ: `https://phong-k10-chuong2-mo-rong.onrender.com`. Học sinh: địa chỉ đó. Giáo viên: thêm `/teacher`. Hồ sơ dạy học số đã gắn sẵn địa chỉ này ở mục Làm bài trực tuyến của khối 10.

### Cần biết khi dùng gói miễn phí của Render
- Máy chủ tự ngủ sau khoảng 15 phút không ai dùng. Mở `/teacher` trước giờ học 5 phút.
- Bài làm mất khi máy chủ ngủ, khởi động lại hoặc cập nhật mã. Cuối buổi bấm **Tải kết quả (.csv)**. Không đẩy bản mới khi học sinh đang làm.
- Tên học sinh được lưu trên máy chủ của Render. Chỉ dùng họ tên và lớp.

## Mã QR, điểm quá trình, vòng tròn tiến độ (16/11/2026)
- **Mã QR**: trang giáo viên có nút **Mã QR** (và tự hiện khi chưa mở câu nào). Bấm vào mã hoặc **Phóng to để chiếu** để học sinh quét. Chạy trên laptop thì mã tự dùng địa chỉ Wi-Fi của máy (học sinh phải cùng mạng).
- **Điểm quá trình**: mỗi buổi tính từ lúc bắt đầu tới khi bấm **Làm lại từ đầu**; điểm buổi = câu đúng gửi kịp / câu đã chấm × 10. Học sinh thấy điểm từng buổi và điểm trung bình ngay trên trang làm bài, nhận ra nhau theo **họ tên và lớp** (không phân biệt dấu, hoa thường), nên dặn các em gõ tên giống nhau mỗi buổi.
- Bảng điểm quá trình (nút **Điểm quá trình**) được lưu ở trình duyệt của giáo viên và trên máy chủ. Máy chủ ngủ (mất dữ liệu) thì mở `/teacher` bằng đúng trình duyệt cũ, bảng tự nạp lại lên máy chủ. Đổi máy: **Sao lưu (.json)** rồi **Nạp tệp sao lưu**. Có **Tải bảng điểm (.csv)**, xóa từng buổi, xóa hết.
- **Vòng tròn tiến độ**: mỗi câu đang mở có vòng tròn "số em đã gửi / sĩ số" ở cả trang học sinh và giáo viên (đầu cột bảng kết quả).
- Mã dùng chung ở hồ sơ dạy học số: `tools/phong_qr_qua_trinh/` (`vao_phong.py` vá hoặc cập nhật một phòng).
