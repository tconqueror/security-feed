# Mozilla hiện cho phép các nhà phát triển phần mở rộng của Firefox hoàn nguyên các bản cập nhật lỗi

![Firefox](https://www.bleepstatic.com/content/hl-images/2024/03/22/Firefox-headpic.jpg)

Mozilla đã công bố một tính năng mới cho phép các nhà phát triển phần mở rộng của Firefox hoàn nguyên về các phiên bản đã được phê duyệt trước đó, giúp họ nhanh chóng khắc phục các lỗi và sự cố nghiêm trọng.

Khi phiên bản phần mở rộng mới nhất bị hoàn nguyên, người dùng sẽ không còn có thể cài đặt nó nữa. Nếu cập nhật tự động được bật, trình duyệt web cũng sẽ tự động hoàn nguyên phần mở rộng về phiên bản trước đó trong vòng 24 giờ đối với những người đã cài phiên bản bị lỗi.

"Nếu việc phát triển một phiên bản sửa đổi và nhận được đánh giá sẽ không giải quyết vấn đề đủ nhanh, bạn có thể hoàn nguyên về một phiên bản cũ hơn của phần mở rộng. Người dùng sau đó sẽ cập nhật lên phiên bản đã được hoàn nguyên khi trình duyệt của họ kiểm tra cập nhật phần mở rộng lần tiếp theo, điều này, theo mặc định, có nghĩa là trong vòng 24 giờ," [Mozilla cho biết](https://extensionworkshop.allizom.org/documentation/publish/version-rollback/).

"Để giải quyết vấn đề này, bạn có thể hoàn nguyên phần mở rộng bằng cách tái xuất bản một phiên bản trước đó với một số phiên bản mới và đẩy phiên bản này tới người dùng thông qua Developer Hub hoặc Add-on Submission API."

Tính năng hoàn nguyên phiên bản hiện có sẵn cho bất kỳ phần mở rộng nào có ít nhất hai phiên bản được phê duyệt, cho phép các nhà phát triển hoàn nguyên về phiên bản đã được phê duyệt được phát hành trước phiên bản hiện tại đối với các phiên bản được phân phối trên addons.mozilla.org. Tuy nhiên, nếu được phân phối tự thân, các nhà phát triển phần mở rộng Firefox có thể hoàn nguyên về bất kỳ phiên bản được phê duyệt nào.

Để hoàn nguyên về một phiên bản đã được phê duyệt trước đó qua Developer Hub, các nhà phát triển phải sử dụng tùy chọn "Rollback to a previous version", nằm cạnh "Upload a New Version" trên trang Status & Versions.

Vào tháng 6, Mozilla [đã giới thiệu một tính năng bảo mật khác](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/) cho cổng add-on của mình nhằm chặn các phần mở rộng độc hại rút tiền từ ví tiền mã hóa của người dùng.

Andreas Wagner, người đứng đầu nhóm đánh giá và bảo mật nội dung của addons.mozilla.org (AMO), cho biết vào thời điểm đó rằng Mozilla đã phát hiện và gỡ bỏ hàng trăm phần mở rộng như vậy trong vài năm qua, bao gồm nhiều ví mã hóa lừa đảo.

Kể từ đó, hai chiến dịch độc hại đã tràn ngập cửa hàng add-ons chính thức của Mozilla dành cho Firefox vào [tháng 7](https://www.bleepingcomputer.com/news/security/dozens-of-fake-wallet-add-ons-flood-firefox-store-to-drain-crypto/) và [tháng 8](https://www.bleepingcomputer.com/news/security/wave-of-150-crypto-draining-extensions-hits-firefox-add-on-store/) với gần 200 phần mở rộng giả mạo các ví tiền mã hóa phổ biến, bao gồm Coinbase, MetaMask, Trust Wallet, Phantom, Exodus, OKX, Keplr và MyMonero.