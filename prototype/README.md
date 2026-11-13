# Prototype T3 — Hoàn vé chưa xác nhận rõ

Mở `index.html` bằng trình duyệt. Không cài thư viện, đăng nhập hay điền API key. Có thể chạy từ thư mục repo: `python -m http.server 8655 --bind 127.0.0.1`, rồi mở `http://127.0.0.1:8655/prototype/`.

## Cách xem bản chính

1. Bấm “Tôi muốn hoàn vé”: AI hỏi rõ người cần hoàn, không tự chọn sẵn.
2. Chọn cả Nguyễn Minh An và Nguyễn Gia Bình, bấm “Tiếp tục · chưa gửi hoàn”.
3. Đọc hậu quả: gửi rồi không rút lại được, về phương thức thanh toán gốc, có thể tới 90 ngày; dữ liệu chưa có giá vé nên không hiển thị số tiền bịa.
4. Nút gửi chỉ bật sau khi tích xác nhận tên cả hai người và hậu quả. Có thể sửa hành khách hoặc quay lại trước khi gửi.
5. Gửi xong thấy mã `HT-MP-001`, trạng thái đã nhận yêu cầu (chưa phải đã hoàn tiền), và không có nút rút lại.

## Các đường thử thêm

- Không chọn hành khách / không tích xác nhận: không gửi được.
- Chỉ chọn người lớn: dừng vì còn trẻ 5 tuổi trong đặt chỗ, chuyển nhân viên để kiểm tra.
- Chỉ chọn trẻ em: chuyển nhân viên vì thiếu điều kiện hoàn tách vé.
- Nhắn “OK, làm đi”: không thay thế thao tác duyệt cuối.
- Bấm “Trợ lý vừa đổi nhầm”: không hứa hoàn tác, có đường gửi ca cho nhân viên.
- Đổi ý trước khi gửi: quay lại và xem chuyến thay thế; không có thay đổi vé.
- Đổi ý sau khi gửi: không rút lại yêu cầu, chỉ thêm đề nghị hỗ trợ.
- Ca chưa chuẩn bị: nhập tin nhắn; nếu chưa hiểu hoặc thiếu căn cứ, trợ lý hỏi rõ hoặc chuyển người, không tự thao tác.
- Bấm “Bắt đầu lại bản mô phỏng” ở cuối trang để thử ca mới.

## Số chú thích trên ảnh

1. **HAX G11 — Giải thích vì sao:** căn cứ đặt chỗ, chính sách và hậu quả trước khi gửi.
2. **HAX G10 — Thu hẹp khi nghi ngờ:** hỏi rõ hành khách, mặc định chưa chọn ai.
3. **HAX G9 — Sửa dễ dàng:** sửa người hoàn hoặc bỏ bước xem xét trước khi gửi. G9 không tạo quyền rút lại sau khi gửi.

## Phạm vi mô phỏng

Một file HTML/CSS/JavaScript, 2 màn hình: đặt chỗ & hỗ trợ; yêu cầu của bạn. AI, tool, mã yêu cầu và hàng chờ đều mô phỏng, không có backend, không gọi model hoặc gửi dữ liệu đi. Trạng thái chỉ tồn tại trong trang đang mở; tải lại trang hoặc reset sẽ khởi tạo phiên demo mới. Chỉ chống gửi trùng trong một phiên mô phỏng.

Luồng đổi chuyến chỉ hiển thị lựa chọn để hỗ trợ đổi ý; không thực hiện giữ chỗ hoặc đổi vé. Không có giá vé hay quy tắc hoàn từng người. Không hứa thời gian nhân viên nhận ca. Nguồn dữ liệu: [đề T3 của VinUni](https://github.com/VinUni-AI20k/K5-L3-Day05-AI-Product-UX-Autonomy/blob/main/tracks/t3-travel.md).

## Đã kiểm tra / chưa kiểm tra

- Đạt: cú pháp JavaScript; phục vụ HTTP 200; 16 kiểm tra logic nghiệp vụ bằng Node VM, không gọi API.
- Chưa kiểm tra: tương tác DOM bằng chuột/bàn phím, bố cục desktop/mobile và ảnh minh chứng. Công cụ điều khiển browser tự dừng vì không xác định chắc URL Chrome.
- Cần Đạt–Tấn mở file bấm thử các đường trên, thêm 1–2 ảnh thật có các số 1/2/3, chốt phần việc/thảo luận mức tự chủ và ghi ca lạ nhận ở demo trên lớp vào `spec.md`.
