# Bài tập tuần 1 · Winning product · làm lại cho TRADEnFUN

Ngày viết: 18/11/2026. Đề: ba phần giao cuối buổi 1 (bài giảng 15, https://build2own.dev/app/master/week-1/bai-tap-tuan-va-cau-truc-mot). Chỗ nộp: https://build2own.dev/app/master/week-1/homework (anh đã nộp bài cũ ngày 01/11, được 30/30).

Dữ liệu gốc: bảng quét 46 nhật ký giao dịch ngày 14/11/2026 ở thư mục này (`bang-46-nhat-ky.csv`, `bang-46-nhat-ky.html`, `debrief-2026-11-14.md`). Bài này không quét lại, chỉ sắp xếp lại theo đề.

## Phần 1 · Danh sách 10 winning product

Ngách: nhật ký giao dịch cho trader cá nhân, ưu tiên crypto perp và forex/CFD. Thứ tự theo đề: doanh thu đã verify → vốn hoặc thương vụ → traffic và số người dùng.

| # | Sản phẩm | Làm gì | Doanh thu verify | Vốn, thương vụ | Traffic, người dùng | Giá thấp nhất | Website | Nguồn số |
|---|---|---|---|---|---|---|---|---|
| 1 | Heron Copier | Sao chép lệnh giữa nhiều tài khoản forex, kèm nhật ký | MRR 7.474 USD; tổng 505.657 USD; 384 thuê bao | | | | https://heroncopier.com | https://trustmrr.com/startup/heron-copier |
| 2 | Tradevipe | Nhật ký gắn thương hiệu riêng, bán cho chủ cộng đồng trading | Tổng 159.856 USD từ 08/2023; MRR đang hiện 0 USD; founder nói khoảng 4.500 USD/tháng | | 2.571 lượt/tháng | 50 USD/tháng (B2B); trader lẻ 0-30 USD | https://www.tradevipe.com | https://trustmrr.com/startup/tradevipe |
| 3 | Traderstats | Theo dõi và phân tích hiệu suất | MRR 498 USD; tổng 11.376 USD; 22 thuê bao | | | | https://traderstats.app | https://trustmrr.com/startup/traderstats |
| 4 | Trading Journal (iOS) | App iOS ghi nhật ký đa thị trường | MRR 308 USD; tổng 15.357 USD; 26 thuê bao | | | | https://apps.apple.com/app/id1658216708 | https://trustmrr.com/startup/trading-journal |
| 5 | Deltalytix | Nhật ký mã nguồn mở cho futures, prop | MRR 264 USD; tổng 21.776 USD; 19 thuê bao | | | | https://deltalytix.app | https://trustmrr.com/startup/deltalytix |
| 6 | Tradervue | Nhật ký lâu đời nhất, ra 2011 | chưa verify | SureSwift Capital mua 2021, giá không công bố | 100.000+ trader lúc bán | 29,95 USD/tháng | https://www.tradervue.com | https://www.sureswiftcapital.com/blog/interview-with-tradervue-founder |
| 7 | TradeZella | Nhật ký tự động kèm replay, backtest, AI, nhóm mentor | chưa verify | Tự bỏ vốn | 1,0 triệu lượt/tháng (Semrush); tự ghi 100.000+ trader | 35 USD/tháng | https://www.tradezella.com | https://www.tradezella.com/pricing |
| 8 | TraderMake.Money | Nhật ký crypto perp, tự đồng bộ 11 sàn, tính funding và phí | chưa verify | | Tự ghi 100.000+ người dùng | 6 USD/tháng; miễn phí 1 sàn | https://tradermake.money | https://tradermake.money/prices |
| 9 | UltraTrader | Nhật ký crypto chỉ đọc + MT5, cTrader; soát 12 thói quen xấu | chưa verify | | Tự ghi 100.000+ trader | 20 USD/tháng; miễn phí 1 sàn | https://ultratrader.app | https://ultratrader.app/crypto-trading-journal |
| 10 | Coin Market Manager | Nhật ký phái sinh crypto, miễn phí nếu mở sàn qua link của họ | chưa verify | | Tự ghi 13.000+ trader, 90% dùng miễn phí qua link | 699,99 USD/năm | https://www.coinmarketman.com | https://www.coinmarketman.com/pricing |

Ghi chú về cách chọn:

- Dòng 1-5 là năm sản phẩm có doanh thu verify cao nhất trên TrustMRR trong ngách này. Tradevipe đứng thứ 2 vì tổng doanh thu verify lớn thứ hai, dù MRR đang hiện 0 USD.
- Dòng 6 là thương vụ thoát vốn duy nhất tìm thấy. Y Combinator (6.397 công ty) không có nhật ký giao dịch nào.
- Dòng 7-10 xếp theo traffic và số người dùng. Số người dùng là số từng bên tự ghi, chưa kiểm được. Coin Market Manager ghi 13.000+ ở trang giá, tài liệu API của họ lại ghi 50.000+.
- TrustMRR không có TradeZella, TraderSync, TradesViz, TraderMake.Money, nên doanh thu của các bên lớn không verify được.
- 36 sản phẩm còn lại nằm trong `bang-46-nhat-ky.csv`.

## Phần 2 · Chân dung khách hàng và lý do chốt sản phẩm

**Sản phẩm chốt:** TRADEnFUN, nhật ký giao dịch nối API sàn chỉ đọc (spec v1.0 anh duyệt 18/11/2026, `../tuan-04/spec-rut-gon.md`).

**Chân dung khách hàng** (lấy từ mục 2 của spec, là quan sát của anh ngày 17/11/2026):

| | Nhóm A: trader giao dịch theo cảm xúc | Nhóm B: trader nhiều tài khoản, nhiều sàn |
|---|---|---|
| Là ai | Trader Việt Nam giao dịch hợp đồng perp trên Binance Futures, BingX, OKX; sau đó là CFD trên MT4, MT5 của Exness | Như nhóm A, có từ hai tài khoản hoặc hai sàn trở lên |
| Hôm nay làm thế nào | Vào và thoát lệnh theo cảm giác; không ghi lại, hoặc chỉ nhìn số dư trên app sàn | Mở từng app, từng sàn; tự cộng lãi lỗ trong đầu hoặc trên bảng tính |
| Đau ở đâu | Không biết mình mất tiền vì thói quen nào | Không có con số tổng; phí và funding rải rác nên không biết lãi thật |
| Gặp họ ở đâu | Nhóm private khoảng 400 người, nhóm chat 6.000 người, livestream hằng ngày | Như nhóm A |

Chỗ còn thiếu: đây là quan sát của người làm sản phẩm, chưa có câu nào của trader nói về việc theo dõi tài khoản. Spec đã ghi việc này là TODO khi 3-5 trader dùng thử.

**Lý do chốt** (điểm giao thoa của ba thứ):

1. Điểm mạnh: hơn 4 năm làm nội dung và vận hành cộng đồng trader; anh giao dịch crypto từ 2020 trên 7-8 sàn nên chính anh là người dùng nhóm B.
2. Nguồn lực: 5.000-6.000 tài khoản đã mở qua link của anh; hợp tác chính thức với 8 đối tác trong lĩnh vực Finance. Đây là đường thu tiền mà nhật ký bán thuê bao không có.
3. Thị trường trả tiền: trader đang trả 6-99 USD/tháng cho nhật ký. Hai mô hình có tiền thật ngoài thuê bao là hoa hồng sàn (Coin Market Manager) và bán cho chủ cộng đồng (Tradevipe).

**Điều đi ngược lại lựa chọn này**, anh cần biết: 6 trong 8 nhật ký có doanh thu verify đang dưới 500 USD mỗi tháng. Mảnh crypto perp không trống: TraderMake.Money đã nối 11 sàn với giá 6-22 USD/tháng. Nếu chỉ bán thuê bao cho trader lẻ thì số liệu nói đây không phải winning product. Lý do chốt đứng được là nhờ đường hoa hồng sàn anh đã có.

## Phần 3 · Deep research toàn thị trường

**Ai đang trả tiền, cho ai** (giá đọc tại trang gốc 11-15/11/2026):

| Nhóm | Ví dụ | Giá |
|---|---|---|
| Nhật ký đa thị trường | TradeZella, TraderSync, Tradervue, TradesViz, Edgewonk | 19,95-99 USD/tháng; Edgewonk 197 USD/năm |
| Nhật ký crypto perp | TraderMake.Money, UltraTrader, Coin Market Manager, TraderDNA, Trade Journal AI | 0-30 USD/tháng; Coin Market Manager 699,99 USD/năm hoặc 0 USD qua link |
| Nhật ký forex, prop | Consistry, TraderWaves, Tradoshi, Myfxbook | 0-19,99 USD/tháng, nhiều bên miễn phí vĩnh viễn |
| Nhật ký cho chủ cộng đồng | Tradevipe | 50-500 USD/tháng |
| Tự làm | Bảng tính, hoặc không ghi | 0 USD |

**Năm điều rút ra** (điều 1-4 từ debrief 14/11/2026, điều 5 là ghi chú của Minh An):

1. Mảnh crypto perp không trống, mảnh forex và prop cũng đông.
2. Nhật ký bán thuê bao cho cá nhân có doanh thu verify rất thấp.
3. Ba chỗ có tiền thật ngoài TradeZella: bán cho chủ cộng đồng (Tradevipe), sống bằng hoa hồng sàn (Coin Market Manager), kèm một công cụ trader đã trả tiền (Heron Copier).
4. Không quỹ lớn nào đầu tư vào nhật ký giao dịch.
5. Chưa tìm thấy nhật ký nào làm riêng cho trader Việt Nam. Lần quét 14/11 không tìm bằng từ khoá tiếng Việt, nên đây là chỗ chưa kiểm, không phải kết luận.

**Quy mô (tính lại ngày 18/11/2026 cho TRADEnFUN, toàn bộ là tự tính).** Tính từ số người, giá 29 USD/tháng (gói Pro gợi ý, tức 348 USD/năm).

| | Phép tính | Số người | Quy ra tiền |
|---|---|---|---|
| TAM, tổng thị trường | Trader forex/CFD và crypto futures toàn cầu × 348 USD/năm | 4,8-11,6 triệu | 1,7-4,0 tỷ USD/năm |
| SAM, thị trường tôi nhắm tới | Trader crypto futures toàn cầu (3-10 triệu) × phần của Việt Nam (2,3-5,0%) × 44% còn trade sau 12 tháng | 30.400-218.700 người dùng được | × 3% chịu trả tiền = 910-6.560 người × 348 USD = 0,32-2,28 triệu USD/năm |
| SOM, phần tôi phục vụ được trong 12 tháng | Nhóm private khoảng 400 người × 10-30% chịu nối sàn | 40-120 người dùng | × 8,3 USD mỗi người mỗi tháng × 12 = 4.000-12.000 USD/năm |

Giả định, xếp từ chắc tới yếu:

- 4,8-11,6 triệu trader toàn cầu và 3-10 triệu người trade crypto futures: giữ từ bài Product Thesis đã nộp, nguồn và giả định ghi ở câu 3 bài đó.
- 44% còn trade sau 12 tháng: Barber và cộng sự, day trader Đài Loan 1992-2006 (https://faculty.haas.berkeley.edu/odean/papers/Day%20Traders/Day%20Trading%20and%20Learning%20110217.pdf).
- Phần của Việt Nam 2,3-5,0%: không nguồn nào công bố số người Việt trade crypto futures (tìm ngày 18/11/2026, không thấy). Mốc dưới 2,3% = 17 triệu người Việt sở hữu crypto (báo Chính phủ dẫn số liệu, 01/2026, https://en.baochinhphu.vn/viet-nam-ranks-7th-in-number-of-crypto-asset-holders-globally-111260129102245433.htm) chia 741 triệu người sở hữu toàn cầu. Mốc trên 5,0% = phần lượt truy cập Binance đến từ Việt Nam, 4,97% (cryip.co dẫn Similarweb, khoảng giữa 2026; nguồn thứ cấp, lấy từ kết quả tìm kiếm, Minh An chưa mở trang gốc).
- SAM chỉ tính crypto futures. CFD (Bước 2 của spec) chưa tính vì chưa có số trader CFD người Việt.
- 3% chịu trả tiền: giả định yếu, giữ từ bài đã nộp. Coin Market Manager tự ghi 90% người dùng của họ không trả tiền trực tiếp.
- 10-30% người trong nhóm private chịu nối sàn: **giả định yếu nhất, chưa có số đo nào.** Thay bằng số thật sau lần đo 21/11/2026 và nhóm 3-5 trader dùng thử.
- 8,3 USD mỗi người mỗi tháng: kịch bản 90% dùng miễn phí qua link (hoa hồng 6 USD) và 10% trả 29 USD, xem bảng hoà vốn trong `../tuan-02/mo-hinh-gia.md`. Ở kịch bản của bài luận cũ (19,8 USD) thì SOM là 9.500-28.500 USD/năm.

Đọc kết quả: SOM bằng 0,02-0,4% số người của SAM. Trần của SAM ở Việt Nam thấp (dưới 2,3 triệu USD/năm nếu chỉ thu thuê bao), nên tiền của sản phẩm này phải đến từ hoa hồng đối tác hoặc từ việc bán ra ngoài Việt Nam.

**Số bị từ chối:** doanh thu TradeZella, TraderSync, TraderMake.Money. Không nguồn nào công bố, các trang tổng hợp trả về số của công ty khác trùng tên (tìm ngày 18/11/2026).

## Còn thiếu để nộp

- Đề yêu cầu xuất danh sách ra bảng tính trên Google Drive. Bảng 46 dòng đang là file CSV trên máy.
- Đề yêu cầu founder, trang X, social: tên founder mới có ở 3 trong 10 dòng (Tradevipe, TradeZella, Tradervue), xem CSV.
