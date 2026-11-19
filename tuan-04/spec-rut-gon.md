# TRADEnFUN · Bản đặc tả sản phẩm (bản rút gọn để nộp)

Build to Own Master · Bài tập buổi 4 · rút từ bản đặc tả đầy đủ v1.8.1 ngày 19/11/2026 (bản v1.0 tôi chấm 9/10 ngày 18/11)

- User flow: https://tradenfun-mockup.tuysolo-porvest.workers.dev/flow
- Mockup bấm được: https://tradenfun-mockup.tuysolo-porvest.workers.dev/

Bản này giữ đủ năm phần của đề. Bản đầy đủ còn có mô tả từng màn, cấu trúc dữ liệu, toàn bộ yêu cầu bảo mật và 32 điều kiện hoàn thành; phiên build làm theo bản đầy đủ.

## 1. Vấn đề và ai đang gặp

TRADEnFUN là web app nhật ký giao dịch. Trader nối tài khoản sàn một lần bằng API key chỉ đọc (khoá chỉ xem được dữ liệu, không đặt lệnh, không rút tiền). Hệ thống tự kéo lịch sử lệnh, phí, funding và số dư từ mọi sàn về một chỗ, dựng thống kê, rồi chỉ ra thói quen giao dịch của chính người đó.

| Nhóm | Hôm nay họ làm thế nào | Đau ở đâu |
|---|---|---|
| A. Trader giao dịch theo cảm xúc | Vào và thoát lệnh theo cảm giác; không ghi lại, chỉ nhìn số dư trên app sàn | Không kiểm soát được tài khoản, không biết mình mất tiền vì thói quen nào |
| B. Trader có nhiều tài khoản, nhiều sàn | Mở từng app, tự cộng lãi lỗ trong đầu hoặc trên bảng tính | Thao tác mệt, không có con số tổng; phí và funding nằm rải rác nên không biết lãi thật |

**Tôi biết điều này từ đâu**

- Quan sát của tôi trong cộng đồng trader của mình (ghi ngày 17/11/2026): có những người giao dịch rất cảm tính, bị cuốn theo cảm xúc và không kiểm soát được tài khoản; có những người giao dịch trên nhiều tài khoản, nhiều sàn và mệt vì phải mở nhiều app để theo dõi.
- Khảo sát ngày 18/11/2026 trong nhóm chat của tôi. Tôi hỏi về một nơi gom tài khoản nhiều sàn thành một bảng điều khiển chỉ đọc, và "nếu là ae thì có dùng không, có tiện hơn không". Ba người trả lời trong một phút, cả ba nói sẽ dùng: "Dc ad" · "Em ok ạ" · "Bạn tính lấy board luôn thì tiện". Người thứ ba cho biết đã từng có ý tưởng tương tự.
- Chỗ còn yếu: ba câu trên là phản hồi cho ý tưởng tôi mô tả và đỡ cho nhóm B. Chưa có câu nào trader tự kể về vấn đề của họ, và chưa có lời nào của nhóm A. Tôi sẽ đưa 3-5 trader Việt vào dùng thử và ghi nguyên văn họ nói gì.

**Người dùng đầu tiên:** trader Việt Nam giao dịch hợp đồng perp (hợp đồng tương lai không kỳ hạn) trên Binance Futures, BingX, OKX. Sau đó tới trader CFD trên MT4, MT5 của Exness. Phần cho chủ cộng đồng chưa nằm trong bản này.

## 2. Kết quả người dùng nhận được

1. **Thấy mọi tài khoản ở một nơi.** Nối xong sàn, trong 5 phút thấy bảng tổng quan đầu tiên, gộp mọi tài khoản.
2. **Biết lãi thật.** Mọi con số lãi lỗ xem được ở hai chế độ: Gross (chưa trừ phí) và Net (đã trừ phí giao dịch và funding).
3. **Xem lại từng ngày, từng lệnh** qua lịch lãi lỗ và bảng lệnh, không phải ghi tay.
4. **Được chỉ ra thói quen.** Mỗi nhận xét có con số, có số lệnh làm căn cứ, và bấm vào thì xem được đúng những lệnh đó.
5. **Dùng thử khi chưa nối sàn.** Bấm Bỏ qua thì vào tài khoản demo có khoảng 300 lệnh mẫu, mọi màn chạy như thật.

## 3. Sản phẩm hoạt động thế nào

### Lõi và vỏ

| Lõi (thiếu thì không còn sản phẩm) | Vỏ (làm sau, đổi được) |
|---|---|
| **L1. Nối sàn chỉ đọc và đồng bộ** | Giao diện, biểu đồ, kéo thả bố cục |
| **L2. Chuẩn hoá thành lệnh và tính đúng số** | Tag, ghi chú, ảnh chụp cho từng lệnh |
| **L3. Chỉ ra thói quen bằng luật** | Chat AI, báo cáo tuần, giọng văn của nhận xét |
| **L4. Kho lịch sử giao dịch dài hạn** | Xuất file, chia sẻ, so sánh với người khác |

Số sai thì mọi thứ phía trên vô nghĩa, nên L1 và L2 làm trước và kiểm kỹ nhất.

**L1. Nối sàn và đồng bộ.** Trader dán API key và secret. Hệ thống gọi sàn để đọc danh sách quyền của key: key có quyền giao dịch hoặc rút tiền thì từ chối và không lưu gì, kèm hướng dẫn tạo lại key chỉ đọc. Key đạt thì secret được mã hoá rồi mới lưu. Lần đầu, hệ thống kéo lịch sử lùi về quá khứ tới mức sàn cho phép và hiện tiến độ. Sau đó cứ 10 phút hỏi sàn một lần, và có nút Đồng bộ ngay. Dữ liệu kéo về: lần khớp lệnh, phí, funding, vị thế đang mở, số dư, nạp rút. Mỗi lần khớp được nhận diện bằng mã của sàn nên chạy lại không tạo bản trùng.

**L2. Chuẩn hoá thành lệnh.** Dữ liệu lưu thành hai lớp. Lớp thô giữ nguyên văn những gì sàn trả về. Lớp chuẩn đổi dữ liệu của mọi sàn về cùng một định dạng: cùng tên cột, đơn vị, quy ước dấu, giờ UTC. Mọi phép tính chỉ đọc lớp chuẩn, nên thêm một sàn mới chỉ cần viết thêm một bộ đổi từ thô sang chuẩn. Một "lệnh" là một vòng đời vị thế trên một tài khoản, một mã, một chiều: từ lúc khối lượng khác 0 tới lúc về 0. Net P&L = Gross P&L − phí giao dịch + funding.

**L3. Chỉ ra thói quen.** Tám nhận xét, tính thẳng trên dữ liệu bằng luật, chưa dùng mô hình AI:

| # | Nhận xét | Cách tính |
|---|---|---|
| 1 | Khung giờ vào lệnh tốt nhất, tệ nhất | Net P&L và tỷ lệ thắng theo 6 khung 4 giờ |
| 2 | Ngày trong tuần tốt nhất, tệ nhất | Net P&L và tỷ lệ thắng theo thứ |
| 3 | Vào lệnh gỡ sau khi thua | So lệnh mở trong 30 phút sau một lệnh thua với các lệnh còn lại |
| 4 | Giao dịch quá nhiều | So những ngày có số lệnh gấp hơn 2 lần mức thường với các ngày còn lại |
| 5 | Chốt lãi sớm, gồng lỗ | So thời gian giữ và mức lãi, lỗ trung bình của lệnh thắng và lệnh thua |
| 6 | Phí và funding ăn vào lãi | (Phí + funding đã trả) ÷ tổng lãi của lệnh thắng |
| 7 | Coin và chiều giao dịch | Net P&L theo từng mã; long so với short |
| 8 | Sau chuỗi thua | Kết quả và khối lượng của lệnh ngay sau 3 lệnh thua liên tiếp |

Mỗi nhận xét xếp vào một trong ba nhóm: Điểm mạnh, Rủi ro, Cần cải thiện. Tài khoản có dưới 30 lệnh đã đóng thì hiện "Chưa đủ dữ liệu". Nhận xét chỉ mô tả hành vi đã xảy ra, không khuyên mua bán, không dự đoán giá.

**L4. Kho lịch sử dài hạn.** Sàn chỉ cho xem lại một khoảng giới hạn; TRADEnFUN giữ mãi. Ngắt kết nối, key hết hạn hay bị thu hồi đều chỉ xoá secret, lịch sử vẫn xem được. Dán key mới cho cùng tài khoản sàn thì hệ thống nối tiếp từ mốc cuối, không tạo bản trùng.

### Luồng chính

Đăng nhập bằng Google hoặc email kèm mã một lần → Nối sàn (chọn sàn, dán key, kiểm quyền) hoặc Bỏ qua để xem bản demo → Đồng bộ lần đầu, số liệu về dần → Bảng điều khiển (Tổng quan, Chi tiết, Lịch, Lệnh, Vị thế mở) → Thói quen → bấm "Xem các lệnh này" để mở đúng các lệnh làm căn cứ. Sơ đồ đầy đủ, kể cả luồng những lần sau, trao đổi giữa các bên khi nối sàn và luồng ngắt kết nối, nằm ở link user flow.

### Bảo mật API key

Đây là khâu tôi yêu cầu làm trước và làm kỹ nhất. Bốn nguyên tắc:

- Chỉ nhận key chỉ đọc, và kiểm lại quyền của key mỗi ngày. Key bị bật thêm quyền thì ngắt và xoá secret ngay.
- Secret được mã hoá trước khi lưu, khoá mã hoá nằm ngoài cơ sở dữ liệu. Trang web không giải mã được secret; chỉ tiến trình đồng bộ làm được.
- Không có chức năng nào hiện lại hay xuất secret. Giao diện chỉ hiện 4 ký tự cuối của API key.
- Có công tắc khẩn: khi nghi lộ key, dừng mọi đồng bộ và xoá toàn bộ secret trong 5 phút.

### Sản phẩm mẫu đã học

Tôi đã đăng nhập dùng thật TraderMake.Money; xem bản demo công khai của Tradevipe; đọc tài liệu công khai của TradeZella và Coin Market Manager. Phiên build chỉ đọc spec, flow và mockup, không xem sản phẩm mẫu (quy tắc phòng sạch): bố cục, câu chữ, màu và dữ liệu demo đều tự làm.

## 4. Những điều không làm trong bản đầu

1. Không đặt lệnh, sửa lệnh, rút tiền, hay chạm vào bất cứ thứ gì trên sàn. Chỉ đọc.
2. Không nhận API key có quyền giao dịch hoặc rút tiền, kể cả khi trader muốn.
3. Không dùng mô hình AI: không chat, không AI coach, không văn do AI viết.
4. Không thanh toán, không gói trả tiền, không mã giảm giá.
5. Không nối sàn nào ngoài Binance Futures, BingX, OKX; MT4, MT5 của Exness làm sau khi ba sàn này đã chạy.
6. Không spot, không hợp đồng ký quỹ bằng coin, không options, không ví on-chain.
7. Không nhập tay, không nhập file CSV.
8. Không tag, ghi chú, ảnh chụp cho lệnh; không replay, backtest, vẽ chart giá.
9. Không tính năng cho chủ cộng đồng: không mentor, bảng xếp hạng, chia sẻ công khai, white label.
10. Không khuyến nghị mua bán, không tín hiệu, không dự đoán giá.
11. Không báo cáo định kỳ qua email, không cảnh báo thời gian thực.
12. Không app di động riêng; chỉ web chạy được trên điện thoại.
13. Không build chức năng xoá dữ liệu lịch sử; yêu cầu xoá đi qua email, xử lý tay.
14. Không chép câu chữ, tên tính năng, màu, bố cục hay dữ liệu demo từ sản phẩm mẫu.

## 5. Định nghĩa hoàn thành và cách kiểm

Bản đầu xong khi các điều kiện dưới đây đạt với ba sàn crypto. Bản đầy đủ có 32 điều kiện; đây là 12 điều kiện chính.

| # | Điều kiện | Cách kiểm |
|---|---|---|
| 1 | Nối được ba sàn bằng key chỉ đọc | Tôi tạo key chỉ đọc trên từng sàn, dán vào: thấy "Đã đồng bộ" và lệnh hiện trong bảng Lệnh |
| 2 | Key có quyền giao dịch bị từ chối | Dán một key có bật quyền giao dịch: thấy thông báo từ chối có lý do; cơ sở dữ liệu không có dòng nào được lưu |
| 3 | Số khớp với sàn | Lấy ngẫu nhiên 20 lệnh đã đóng trên mỗi sàn, so Net P&L với lịch sử lãi lỗ của sàn: mỗi lệnh lệch không quá 0,01 USD; tổng 30 ngày lệch không quá 0,5% |
| 4 | Gộp nhiều tài khoản đúng | Nối 2 tài khoản: tổng ở "Tất cả" bằng tổng của hai tài khoản xem riêng |
| 5 | Lịch và bảng Lệnh khớp nhau | Tổng tháng trên Lịch bằng tổng Net P&L của bảng Lệnh lọc đúng tháng đó, kiểm 2 tháng |
| 6 | Tài khoản demo chạy đủ | Đăng ký mới, bấm Bỏ qua: mọi màn có dữ liệu, băng "dữ liệu mẫu" hiện trên mọi trang |
| 7 | Thói quen có căn cứ | Mỗi thẻ có con số và số lệnh; bấm "Xem các lệnh này" ra đúng số lệnh đó. Tài khoản 10 lệnh thì hiện "Chưa đủ dữ liệu" |
| 8 | Lệnh mới về trong 15 phút | Đóng một lệnh trên sàn, bấm giờ: lệnh xuất hiện trong 15 phút mà không cần bấm gì |
| 9 | Mất kết nối được báo rõ | Xoá key trên sàn: trong 15 phút trạng thái thành "Mất kết nối", số liệu cũ vẫn còn, có nút nối lại |
| 10 | Secret không lộ | Cột secret trong cơ sở dữ liệu là chuỗi đã mã hoá; phản hồi mạng và log máy chủ không có secret |
| 11 | Người này không xem được dữ liệu người kia | Đăng nhập tài khoản B, gọi thẳng địa chỉ dữ liệu của tài khoản A: bị từ chối |
| 12 | Từ đăng ký tới bảng tổng quan dưới 5 phút | 3 trader trong nhóm dùng thử, đã có sẵn key, tự làm, bấm giờ |

## Chỗ còn mở

- Chưa có lời trader tự kể về vấn đề, nhất là nhóm A.
- Độ sâu lịch sử mỗi sàn cho kéo về và cách đọc quyền của key ở từng sàn phải kiểm khi build.
- Các ngưỡng 30 phút, 2 lần, 30 lệnh là mức đề xuất ban đầu, chỉnh lại khi có dữ liệu thật.
