## Save Info

Kullanıcının kişisel bilgilerini kaydettiği servistir. KYC akışında ilk adımdır.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/Onboarding/VerifyAndSaveInfo

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre            | Tip         | Zorunlu | Açıklama                                                   |
|----------------------|------------|---------|------------------------------------------------|
| `identitySeriesNumber`            | `string`    | Evet    | Kimlik seri numarası. |
| `jobId`          | `integer`   | Evet    | Kullanıcının meslek ID'si. |
| `averageMonthly`| `integer`   | Evet    | Kullanıcının aylık ortalama geliri. |
| `sourceOfIncome`      | `string`    | Evet    | Kullanıcının gelir kaynağı. |

#### REQUEST BODY

```json
{
  "identitySeriesNumber": "BvC2ozsaK",
  "jobId": 2147483647,
  "averageMonthly": 2147483647,
  "sourceOfIncome": "string"
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/Onboarding/VerifyAndSaveInfo' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-session-id: <SESSION_ID>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "identitySeriesNumber": "BvC2ozsaK",
  "jobId": 2,
  "averageMonthly": 2147483647,
  "sourceOfIncome": "string"
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "data": true,
  "requiresSecurityImageSelection": false
}
```
#### ⏭️ Bir Sonraki Adım
👉 Bu servise istek atılıp başarılı bir yanıt alındıysa,bir sonraki adım olarak adres doğrulanmalıdır. Bunun için
<a href="#" onclick="loadMarkdown('docs/validate-address.md')"><strong>Adres Doğrulama</strong></a> servisini çağırmalısınız.