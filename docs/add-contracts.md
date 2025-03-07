## Add Contracts Log

Bu servis, kullanıcının sözleşme kaydını oluşturur.  
Sözleşme kaydı eklendiğinde, **onay durumu** ve **onay tarihi** alanları başlangıçta `NULL` olarak bırakılır.  
**Get All Sözleşmeler** servisinden gelen benzersiz (`uniqueValue`) ID değeri, sözleşme tipiyle birlikte parametre olarak bu servise gönderilir.  

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/User/AddContractsLog TipNo=2uniqueValue=54e53fdf-9d78-4587-a3d0-1c7fb681cb6e

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre | Tip      | Zorunlu | Açıklama                                  |
|-----------|---------|---------|---------------------------------|
| `tipNo`   | `integer` | Evet    | Sözleşme tipi numarası. |
| `uniqueValue`| `uuid` | Evet    | Kullanıcıya ait benzersiz sözleşme değeri.|

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/User/AddContractsLog?TipNo=2&uniqueValue=54e53fdf-9d78-4587-a3d0-1c7fb681cb6e' \
  -H 'accept: */*' \
  -H 'x-channel-info: WEB' \
  -d ''
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Sözleşme kaydı eklendi. Onay bekleniyor",
  "MessageEN": "Contract saved.",
  "data": {
    "uniqueValue": "54e53fdf-9d78-4587-a3d0-1c7fb681cb6e",
    "tipNo": 2,
    "url": "https://localhost:7279/swagger/index.html",
    "message": "Sözleşme kaydı eklendi. Onay bekleniyor.",
    "openIpAddress": "10.222.109.128:35706"
  },
  "requiresSecurityImageSelection": false
}

```
### ⏭️ **Bir Sonraki Adım**  
👉 Bu servise istek atılıp başarılı bir yanıt alındıysa, bir sonraki adım olarak sözleşmeleri onaylamak için, <a href="#" onclick="loadMarkdown('docs/confirm-contract-if-opened.md')"><strong>Sözleşme Okunma Durumu</strong></a> servisini çağırmalısınız.

