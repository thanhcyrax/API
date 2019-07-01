# API Affiliate
**Đối với User mới cài App**
**POST** `https://affiliate.fireapps.io/api/update_campaign`
**Mô tả:** Nếu có User mới cài App thì tiến hành gọi API.
```sh
$data = array(
        'partner_id'  => empty($_COOKIE['partner_id']) ? '' : $_COOKIE['partner_id'],
        'campaign'    => empty($_COOKIE['utm_campaign']) ? '' : $_COOKIE['utm_campaign'],
        'source'      => empty($_COOKIE['utm_source']) ? '' : $_COOKIE['utm_source'],
        'medium'      => empty($_COOKIE['utm_medium']) ? '' : $_COOKIE['utm_medium'],
        'store_name'  => $shopDomain,
        'accessToken' => $accessToken,
        'app'         => $appName, //alireviews, alihunter 
        'status'      => $planName, //free, pro, unlimited
        'price'       => $price, //0, 9.9, 14.9
    );
```
Lưu ý:
_ Đối với những plan có thu phí thì chỉ khi xác nhận charge thì mới gọi API.

**Đối với User muốn Upgrade hoặc Downgrade**
**POST** `https://affiliate.fireapps.io/api/upgrade_campaign`
**Mô tả:** Mỗi lần User muốn up lên Plan cao hơn, hạ xuống Plan thấp hơn , User gỡ App cài lại hoặc User đóng  Store thì tiến hành gọi API.
```sh
$data = array(
        'store_name' => $shopDomain,
        'app' => $appName, //alireviews, alihunter
        'status' => $planName, //free, pro, unlimited
        'price' => $price, //0, 9.9, 14.9
    );
```
Lưu ý:
_ Đối với những plan có thu phí thì chỉ khi xác nhận charge thì mới gọi API.

**Gửi Access Token mỗi khi User Login vào App**
**POST** `https://affiliate.fireapps.io/api/update_token`
**Mô tả:** Mỗi lần User login vào App thì gọi API để cập nhật Token cho đồng bộ.
```sh
$data = array(
        'store_name'  => $shopDomain,
        'accessToken' => $accessToken,
    );
```
