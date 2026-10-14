# Tạo QR VietinBank — bản in Canon CP1300

Đã chỉnh theo giấy Canon Postcard 100 × 148 mm, khổ đứng. Giữ 7 mẫu và thao tác trên điện thoại, tăng cỡ chữ và dùng QR đen dạng ô vuông, có vùng trắng xung quanh. Chữ, logo và QR được vẽ lại khi tải ảnh, độc lập với ảnh xem trước. Nền trang trí dùng ảnh nén không mất dữ liệu.

## Hai định dạng tải ảnh

| Lựa chọn trong app | Kích thước | Độ phân giải | Mục đích |
| --- | --- | --- | --- |
| JPG · In Canon CP1300 | 1181 × 1748 px | 300 dpi, có Exif | In Canon, ứng dụng in ảnh hoặc thẻ nhớ/USB |
| PNG · Lưu ảnh chất lượng cao | 2362 × 3496 px | 600 dpi, không mất dữ liệu | Lưu bản gốc và chia sẻ ảnh |

Cả hai có cùng khổ 100 × 148 mm. CP1300 in ở 300 dpi; PNG 600 dpi là bản lưu có nhiều điểm ảnh hơn, không tăng độ phân giải phần cứng máy in.

## Cập nhật website đang dùng

1. Giải nén ZIP bằng Extract All trên Windows.
2. Mở kho GitHub `tao-qr-vietinbank`, chọn nhánh `main`.
3. Chọn Add file → Upload files, kéo `index.html`, `vercel.json`, `README.md` từ ZIP đã giải nén lên, lưu/commit để thay phiên bản cũ.
4. Vercel tự triển khai lại từ nhánh production `main`. Chờ lần triển khai mới thành công rồi tải lại website; trên laptop có thể dùng Ctrl+F5.
5. Kiểm tra app xuất hiện mục “Định dạng tải ảnh” với lựa chọn JPG in Canon CP1300 và ghi khổ 100 × 148 mm.

`index.html` là toàn bộ chương trình. Tệp phải nằm ở cấp đầu tiên của kho. Không cần thêm API hoặc cơ sở dữ liệu; số tài khoản và tên chỉ xử lý trong trình duyệt.

## In đúng khổ Canon CP1300

1. Trong app, nhập STK, tên và chọn mẫu, giữ định dạng JPG · In Canon CP1300 rồi bấm Tải ảnh QR.
2. Mở tệp JPG đã tải bằng phần mềm/ứng dụng in ảnh, chọn Canon SELPHY CP1300.
3. Chọn giấy Postcard/P tương ứng 100 × 148 mm, hướng dọc (Portrait), Page Layout 1-up, Borders: Borderless (Không viền).
4. Có thể tắt Image Optimize để giữ màu và độ tương phản của thiết kế. Kiểm tra bản xem trước của phần mềm in để QR và dòng tài khoản nằm trọn trong giấy.
5. In một tờ thử, dùng ứng dụng ngân hàng quét QR và đối chiếu đúng ngân hàng, STK và tên người nhận.

Tên in trên ảnh do người dùng nhập; chương trình không tự tra cứu tên tài khoản. Dùng tệp ảnh tải về để in; ảnh xem trước trong app chỉ phục vụ thao tác trên màn hình.

## Triển khai lần đầu trên Vercel

Tạo kho trên GitHub, tải ba tệp ở cấp gốc lên. Trên Vercel chọn New Project, import kho và Deploy. Cấu hình Other, Root Directory mặc định ./, Build Command và Install Command để trống, Output Directory là một dấu chấm (.). `vercel.json` đã đặt sẵn cấu hình này.

Vercel Hobby dành cho cá nhân, phi thương mại; dùng phục vụ hoạt động của chi nhánh/ngân hàng cần gói phù hợp.

## Kiểm tra đã thực hiện

- Tệp JPG/PNG đúng kích thước và dpi, dữ liệu Exif của JPG, kiểm tra cấu trúc PNG.
- Giải mã QR độc lập ở cả hai định dạng, 7 mẫu, STK có số 0 đầu, STK dài, tên dài và ảnh thu nhỏ trên điện thoại.
- Kiểm tra hai nút tải, đổi định dạng, chọn mẫu, nhập lại khách hàng và thao tác bàn phím.
- Chưa in thử trực tiếp trên máy CP1300 thực tế.

## Tài liệu Canon và triển khai

- Canon CP1300, khổ giấy và độ phân giải: https://www.canon-europe.com/printers/selphy-cp1300/specifications/
- Hướng dẫn Canon: https://gdlp01.c-wss.com/gds/6/0300028156/02/SELPHY_CP1300_Printer_User_Guide_EN.pdf
- GitHub tải tệp: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- Vercel kết nối Git: https://vercel.com/docs/git
- Vercel HTML tĩnh: https://vercel.com/docs/builds/configure-a-build
