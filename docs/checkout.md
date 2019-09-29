## Checkout là gì

> Là cổng thanh toán được xây dựng bởi Sacombank, hỗ trợ thanh toán/liên kết thẻ/tài khoản Sacombank, thẻ ATM nội địa (Napas) và thẻ quốc ngân hàng khác (Visa/MasterCard/JCB).

## Chức năng chi tiết

- Thanh toán với thẻ/tài khoản Sacombank, thẻ ATM nội địa (Napas) và thẻ QTNHK.

- Thanh toán và liên kết (tạo token để lưu thông tin cho các lần thanh toán sau) với thẻ/tài khoản Sacombank, thẻ ATM nội địa (Napas) và thẻ QTNHK.

- Chỉ liên kết thẻ/tài khoản Sacombank (khách hàng không cần phải thanh toán bất kỳ số tiền nào).

- Chỉ liên kết thẻ ATM nội địa (Napas) và thẻ QTNHK (khách hàng cần thanh toán số tiền min do Sacombank quy định, sau đó khách hàng sẽ được hoàn lại số tiền vừa thanh toán sau khi liên kết thành công).

## Chức năng thanh toán

<strong>HTTP Request</strong>

<table>
<thead>
<tr>
<th>Attribute</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody><tr>
<td>requestId</td>
<td>String</td>
<td>√</td>
<td>Giống với yêu cầu ban đầu</td>
</tr>
<tr>
<td>errorCode</td>
<td>int</td>
<td>√</td>
<td><a href="#/docs/aio/?id=b%e1%ba%a3ng-m%c3%a3-l%e1%bb%97i">Mã lỗi</a></td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>√</td>
<td>Mô tả lỗi tiếng Anh</td>
</tr>
<tr>
<td>localMessage</td>
<td>String</td>
<td>√</td>
<td>Mô tả lỗi Tiếng Việt</td>
</tr>
<tr>
<td>requestType</td>
<td>String</td>
<td>√</td>
<td><code>captureMoMoWallet</code></td>
</tr>
<tr>
<td>payUrl</td>
<td>String</td>
<td>√</td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
<tr>
<td>qrCodeUrl</td>
<td>String</td>
<td></td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
<tr>
<td>deeplink</td>
<td>String</td>
<td></td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
<tr>
<td>deeplinkWebInApp</td>
<td>String</td>
<td></td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
</tbody></table>

> Example request

```json
{
  "accessKey": "F8BBA842ECF85",
  "partnerCode": "MOMO",
  "requestType": "captureMoMoWallet",
  "notifyUrl": "https://momo.vn",
  "returnUrl": "https://momo.vn",
  "orderId": "MM1540456472575",
  "amount": "150000",
  "orderInfo": "SDK team.",
  "requestId": "MM1540456472575",
  "extraData": "email=abc@gmail.com",
  "signature": "996ed81d68a1b05c99516835e404b2d0146d9b12fbcecbf80c7e51df51cac85e"
}
```
<strong>HTTP Response</strong>

<table>
<thead>
<tr>
<th>Attribute</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody><tr>
<td>requestId</td>
<td>String</td>
<td>√</td>
<td>Giống với yêu cầu ban đầu</td>
</tr>
<tr>
<td>errorCode</td>
<td>int</td>
<td>√</td>
<td><a href="#/docs/aio/?id=b%e1%ba%a3ng-m%c3%a3-l%e1%bb%97i">Mã lỗi</a></td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>√</td>
<td>Mô tả lỗi tiếng Anh</td>
</tr>
<tr>
<td>localMessage</td>
<td>String</td>
<td>√</td>
<td>Mô tả lỗi Tiếng Việt</td>
</tr>
<tr>
<td>requestType</td>
<td>String</td>
<td>√</td>
<td><code>captureMoMoWallet</code></td>
</tr>
<tr>
<td>payUrl</td>
<td>String</td>
<td>√</td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
<tr>
<td>qrCodeUrl</td>
<td>String</td>
<td></td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
<tr>
<td>deeplink</td>
<td>String</td>
<td></td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
<tr>
<td>deeplinkWebInApp</td>
<td>String</td>
<td></td>
<td>Tham khảo cách sử dụng ở phía dưới</td>
</tr>
</tbody></table>

> Example response

```json
{
  "requestId": "MM1540456472575",
  "errorCode": 0,
  "orderId": "MM1540456472575",
  "message": "Success",
  "localMessage": "Thành công",
  "requestType": "captureMoMoWallet",
  "payUrl": "https://test-payment.momo.vn/gw_payment/payment/qr?partnerCode=MOMO&accessKey=F8BBA842ECF85&requestId=MM1540456472575&amount=150000&orderId=MM1540456472575&signature=df2a347519abb91e9c1bd1bee80e675f4108cb6dbcac531979e805857293d486&requestType=captureMoMoWallet",
  "signature": "ee6a01b85ffc48a2b5d3df473da88c75cc5e879d1543d9e76ced279c10bcd646",
  "qrCodeUrl": "https://test-payment.momo.vn/gw_payment/s/zoVKZd",
  "deeplink": "momo://?action=payWithAppToken&amount=150000&fee=0&requestType=payment&orderLabel=M%C3%A3+%C4%91%C6%A1n+h%C3%A0ng&orderId=MM1540456472575&requestId=MM1540456472575&merchantnamelabel=Nh%C3%A0+cung+c%E1%BA%A5p&description=SDK+team.&partnerCode=MOMO&merchantcode=MOMO&language=vi&merchantname=MoMo+Payment&packageId=&extras=&extraData=email=abc@gmail.com&deeplinkCallback=https%3A%2F%2Ftest-payment.momo.vn%2Fgw_payment%2Fm2%3Fid%3DM7EWVy&callbackUrl=https%3A%2F%2Ftest-payment.momo.vn%2Fgw_payment%2Fm2%3Fid%3DM7EWVy&urlSubmitToken=https%3A%2F%2Ftest-payment.momo.vn%2Fgw_payment%2Fpayment_with_app%3FpartnerCode%3DMOMO%26accessKey%3DF8BBA842ECF85%26requestId%3DMM1540456472575%26orderId%3DMM1540456472575%26orderInfo%3DSDK%2Bteam.%26amount%3D150000%26signature%3Ddf2a347519abb91e9c1bd1bee80e675f4108cb6dbcac531979e805857293d486%26requestType%3DcaptureMoMoWallet%26payType%3Dapp-in-app&appScheme=",
  "deeplinkWebInApp": "http://momo//?type=webinapp&action=payment&requestId=MM1540456472575&billId=MM1540456472575&partnerCode=MOMO&partnerName=MoMo Payment&amount=150000&description=SDK team.¬ifyUrl=https://momo.vn&returnUrl=https://momo.vn&code=momo&extraData=eyJzaWduYXR1cmUiOiI0OWUzMTZhNTVkN2UxM2Q0ZjEwNGFjZjM2YTM5MzllZjg0NDk3NWU2OTJiMWU1OGM3MDFjYWUyM2ZiM2QxNDY5In0=&signature=49e316a55d7e13d4f104acf36a3939ef844975e692b1e58c701cae23fb3d1469"
}
```