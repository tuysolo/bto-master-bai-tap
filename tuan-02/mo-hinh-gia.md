# Bài tập tuần 2 · Mô hình kinh doanh và giá · làm cho TRADEnFUN

Ngày viết: 18/11/2026. Đề: ba bài giao cuối buổi 2 (bài giảng 16, https://build2own.dev/app/master/week-2/tong-ket-bai-tap-ve-nha). Chỗ nộp: https://build2own.dev/app/master/week-2/homework. Bài này đã quá hạn từ 05/11, Campus đang ghi 0/30.

Viết theo các bước của skill `master-pricing-model`. Loại tiền: USD. Mọi mức giá bên dưới là **gợi ý để kiểm**, anh quyết sau khi hỏi người thật.

## Bài 1 · Chọn thị trường ngách sâu

Ba việc anh làm lâu nhất (lấy từ câu 1 bài Product Thesis):

| Việc | Từ khi nào | Kết quả có số |
|---|---|---|
| Xây kênh YouTube crypto tiếng Việt và điều hành team content | 08/2022 | 60.000 subscriber, 100% traffic tự nhiên |
| Vận hành cộng đồng Telegram và affiliate cho các đối tác trong lĩnh vực Finance | 08/2022 | 5.000-6.000 tài khoản mở qua link |
| Livestream phân tích thị trường hằng ngày | cuối 2023 | 300-400 người xem ổn định |

**Ngách chọn:** công cụ theo dõi và soát thói quen giao dịch cho trader perp crypto người Việt, sau đó là CFD. Đây là đi sâu trong đúng ngành và đúng tệp anh đã ở cạnh hơn 4 năm. Thứ duy nhất mới là kỹ năng build phần mềm.

## Bài 2 · Phân tích đối thủ, trong nước và quốc tế

| Đối thủ | Giá | Mô hình | Doanh thu | Traffic, người dùng | Vốn |
|---|---|---|---|---|---|
| TradeZella (Mỹ) | 35, 59, 99 USD/tháng | Thuê bao 3 bậc + credit AI | chưa kiểm | 1,0 triệu lượt/tháng (Semrush); tự ghi 100.000+ trader | Tự bỏ vốn |
| TraderMake.Money | 0-22 USD/tháng | Freemium | chưa kiểm | Tự ghi 100.000+ người dùng | chưa kiểm |
| UltraTrader | 0-20 USD/tháng | Freemium | chưa kiểm | Tự ghi 100.000+ trader | chưa kiểm |
| Coin Market Manager (Dubai) | 0 USD qua link sàn; 699,99-899,99 USD/năm | Hoa hồng sàn + thuê bao năm + API | 513.330 USD/năm (ước lượng của Prospeo, không phải số công bố) | Tự ghi 13.000+ trader | Chưa từng gọi vốn (Prospeo) |
| Tradevipe (Brazil) | 50-500 USD/tháng B2B; trader lẻ 0-30 USD | White label theo ghế | Tổng 159.856 USD từ 08/2023 (verify, TrustMRR) | 2.571 lượt/tháng | chưa kiểm |
| Tradervue (Mỹ) | từ 29,95 USD/tháng | Thuê bao | chưa kiểm | 100.000+ trader lúc bán | SureSwift Capital mua 2021 |
| Edgewonk (Đức) | 197 USD/năm | Thuê bao năm | 5,5 triệu USD (ước lượng của ZoomInfo, không rõ năm) | chưa kiểm | chưa kiểm |
| Trong nước | | | | | Chưa kiểm: chưa tìm bằng từ khoá tiếng Việt |

Nguồn giá và mô hình: `../tuan-03/boc-gia-3-doi-thu.md` (đọc 12-15/11/2026) và bảng quét 14/11. Nguồn doanh thu ước lượng: https://prospeo.io/c/coin-market-manager-revenue · https://www.zoominfo.com/c/edgewonk/415056718 (tìm ngày 18/11/2026).

## Bài 3 · Mô hình định giá và đóng gói

### Bước 1. Khách đang trả cho ai, bao nhiêu

| Cách khách đang giải việc này | Ví dụ | Chi phí | Nguồn |
|---|---|---|---|
| Trả tiền để học từ một người đi trước | 120 người đã trả cho anh, 08/2022-08/2023 | 249 USD cho 3 tháng, tức 83 USD/tháng (249 ÷ 3, tự tính); 449 USD trọn đời, không quy ra tháng được vì không có thời hạn | Số của anh, bài Product Thesis câu 1 và câu 6 |
| Khoá học trading | The Trading Channel; BitProfits | 997 USD; 1.497 USD một lần | Trang gốc, đọc 11/11/2026 |
| Nhóm tín hiệu | Learn 2 Trade | 39 GBP/tháng | Trang gốc, đọc 11/11/2026 |
| Thuê người soát tài khoản, coach 1-1 | | chưa kiểm | Đưa thành câu hỏi ở bước 6 |
| Tự làm bằng tay | Bảng tính, hoặc mở từng app sàn | 0 USD cộng thời gian; số giờ chưa kiểm | Đưa thành câu hỏi ở bước 6 |
| Phần mềm nhật ký | Bảng ở bài 2 | 0-99 USD/tháng | Không dùng làm mốc chính |

**Mốc chính:** 83 USD/tháng, giá gói 3 tháng trader từng trả cho chính anh để được kèm (249 ÷ 3, tự tính). Đây là giá của một gói, chưa phải trung bình của cả 120 người: muốn có trung bình thật cần biết bao nhiêu người mua gói 3 tháng, bao nhiêu người mua trọn đời, và có ai gia hạn không. Đây là mốc dịch vụ, đúng cách buổi 2 dạy.

### Bước 3. Mô hình

Chính: **Freemium** (số 2), tiền đến từ hoa hồng của đối tác khi trader mở tài khoản qua link. Ghép: **Productized service** (số 8), một gói soát tài khoản làm tay giá cố định.

Vì sao: trader crypto perp đã quen nhật ký miễn phí (Coin Market Manager ghi 90% người dùng của họ không trả tiền trực tiếp), còn anh đã có sẵn đường hoa hồng. Gói làm tay là thứ khách trả nhiều hơn trên mỗi lần mua, theo bài "Chi phí trên mỗi khách" tuần 3.

### Bước 4. Ba gói

| | Gói thấp | Gói giữa | Gói cao |
|---|---|---|---|
| Tên | Qua link | Pro | Soát tài khoản |
| Giá | 0 USD. Anh nhận hoa hồng từ đối tác: trung bình 56 USD mỗi trader active mỗi tháng (số từ trang affiliate của đối tác), tính thận trọng 6 USD ở năm đầu (số ước lượng trong bài Product Thesis, chưa có phép tính đỡ) | 29 USD/tháng `gợi ý, lấy từ bài Product Thesis` | 100 USD/tháng `gợi ý, lấy từ bài Product Thesis` |
| Gồm gì | Nối sàn chỉ đọc, bảng tổng quan, lịch, bảng lệnh, 8 nhận xét thói quen | Như gói thấp, cho người không mở tài khoản qua link; đồng bộ nhanh hơn, nhiều tài khoản hơn | Gói Pro, cộng mỗi tháng một buổi 30-45 phút anh đọc nhật ký cùng trader và một bản tổng kết thói quen |
| Phần làm tay, phần phần mềm | Phần mềm làm hết | Phần mềm làm hết | Phần mềm tính số; anh đọc và nói chuyện |
| Bán cho ai | Trader mở tài khoản mới qua link | Trader đã có tài khoản sàn, không muốn đổi | Trader thua lỗ kéo dài, muốn có người kèm |

So với mốc 83 USD: gói giữa rẻ hơn khoảng 3 lần; gói cao đắt hơn mốc khoảng 20% và có thêm phần mềm.

Ba chỗ anh cần quyết:

1. **Miễn phí hay giảm giá cho người qua link.** Bài Product Thesis ghi "miễn phí hoặc giảm giá". Spec mục 5 (Phase 1C) ghi "mã giảm giá". Hai chỗ chưa khớp.
2. **Gói Pro 29 USD cao hơn đối thủ trực tiếp.** TraderMake.Money 6-22 USD/tháng, UltraTrader 20 USD/tháng. Buổi 2 dạy không so với phần mềm cùng ngành, nhưng trader sẽ tự so.
3. **Gói cao có bán không.** Anh đã bỏ thu phí từ 08/2023 vì nó giới hạn doanh thu và có thể liên quan pháp lý (lời anh ở phiên làm bài tuần 3). Gói soát tài khoản là thu phí dịch vụ trở lại.

### Hoà vốn

Lấy lại phép tính ở câu 6 bài Product Thesis: mỗi khách mang lại khoảng 20 USD/tháng (40% qua link × 6 USD + 60% trả 29 USD, tự tính); chi phí phục vụ 1 USD mỗi khách; chi phí cố định 100 USD/tháng; thêm một nhân sự 300 USD từ khoảng 20 khách, 1.000-2.000 USD ở quy mô lớn.

| Số khách | Doanh thu/tháng | Chi phí/tháng | Lợi nhuận/tháng |
|---|---|---|---|
| 5 | 99 USD | 105 USD | âm 6 USD |
| 10 | 198 USD | 110 USD | 88 USD |
| 100 | 1.980 USD | 500 USD | 1.480 USD |
| 1.000 | 19.800 USD | 2.100-3.100 USD | 16.700-17.700 USD |

Kiểm lại số học (tự tính, 18/11): 40% × 6 + 60% × 29 = 19,8 USD mỗi khách; hoà vốn khi tự làm = 100 ÷ (19,8 − 1) = 5,3, làm tròn lên 6 khách; có một nhân sự = 400 ÷ 18,8 = 21,3, làm tròn lên 22 khách. Bảng khớp.

Chỗ chưa chuẩn nằm ở hai giả định đầu vào, không nằm ở phép tính:

| Kịch bản | Tỷ lệ qua link (miễn phí) | Hoa hồng mỗi người qua link | Mỗi khách mang lại | Hoà vốn tự làm | Hoà vốn có một nhân sự |
|---|---|---|---|---|---|
| Bài luận cũ | 40% | 6 USD | 19,8 USD | 6 khách | 22 khách |
| Phần lớn dùng miễn phí, như Coin Market Manager tự ghi | 90% | 6 USD | 8,3 USD | 14 khách | 55 khách |
| Như trên, hoa hồng bằng mức trung bình trader active | 90% | 56 USD | 53,3 USD | 2 khách | 8 khách |

Cả bảng là tự tính. 56 USD là trung bình trên trader **active**; 6 USD phải là trung bình trên **mọi** người mở tài khoản qua link trong năm đầu, kể cả người không giao dịch. Số này chỉ anh lấy được từ trang affiliate của đối tác: hoa hồng 12 tháng của nhóm mở tài khoản trong một tháng, chia cho số tài khoản mở, chia 12.

Bảng 5, 10, 100, 1.000 khách ở trên tính cho sản phẩm ở bài luận cũ. Với TRADEnFUN có hai khoản chưa có số: phí dịch vụ trung gian để đọc tài khoản MT4, MT5 (tính theo tài khoản, spec ghi `cần kiểm khi build`), và người dùng miễn phí tốn hạ tầng mà không mang lại doanh thu.

### Bước 5. Bước 1: bán dịch vụ làm tay tuần này

Khi phần mềm chưa có, anh làm tay đúng việc phần mềm sẽ làm cho nhóm 3-5 trader dùng thử đã chốt trong spec: mỗi người xuất lịch sử lệnh 3 tháng từ sàn thành file, anh (cùng agent) tính 8 nhận xét thói quen ở mục 4.1 của spec, rồi gửi lại một trang tổng kết và nói chuyện 30 phút. Thu tiền hay làm miễn phí đổi lấy phản hồi là việc anh quyết. Cả hai cách đều cho anh câu nói thật của trader, thứ spec và bài luận đang thiếu.

### Bước 6. Câu hỏi để hỏi 3 người thật

Minh An không nhắn ai thay anh. Anh hỏi và ghi nguyên văn:

1. Giá bao nhiêu một tháng thì anh/chị thấy rẻ tới mức nghi ngờ chất lượng?
2. Giá bao nhiêu thì thấy rẻ, đáng mua?
3. Giá bao nhiêu thì thấy đắt nhưng vẫn cân nhắc?
4. Giá bao nhiêu thì không mua?
5. Hiện anh/chị theo dõi lãi lỗ bằng cách nào, mỗi tuần mất bao lâu?
6. Anh/chị đã từng trả tiền cho ai để soát tài khoản hay kèm giao dịch chưa, bao nhiêu?
7. Nếu công cụ miễn phí khi mở tài khoản sàn qua một link, anh/chị có mở tài khoản mới không?

## Debrief

- **Mô hình:** Freemium sống bằng hoa hồng đối tác, ghép một gói soát tài khoản làm tay.
- **Ba gói:** Qua link 0 USD · Pro 29 USD/tháng · Soát tài khoản 100 USD/tháng. Cả ba là gợi ý.
- **Mốc so sánh:** 83 USD/tháng, giá gói 3 tháng trader từng trả cho chính anh (249 ÷ 3).
- **Câu hỏi còn mở:** miễn phí hay giảm giá cho người qua link; giá Pro so với đối thủ 6-22 USD; có bán lại dịch vụ thu phí không; giá coach 1-1 ngoài thị trường chưa kiểm.
