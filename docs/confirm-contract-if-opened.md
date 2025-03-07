## Confirm Contract If Opened  

Kullanıcının sözleşmeyi açıp açmadığını doğrulamak için kullanılır.  

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/User/ConfirmContractIfOpened?uniqueValue=54e53fdf-9d78-4587-a3d0-1c7fb681cb6e

**REQUEST METHOD** : `POST`  

### İstek (Request):

#### Parametreler:

| Parametre    | Tip       | Zorunlu | Açıklama                                      |
|-------------|----------|---------|-----------------------------------------------|
| `uniqueValue` | `uuid` | Evet    | Kullanıcıya ait benzersiz sözleşme değeri. |


#### REQUEST BODY

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Kullanıcı Sözleşmesi açıldı",
  "MessageEN": "User Contract opened",
  "data": "Sözleşme açıldı.",
  "requiresSecurityImageSelection": false
}
```  
#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/User/ConfirmContractIfOpened?uniqueValue=54e53fdf-9d78-4587-a3d0-1c7fb681cb6e' \
  -H 'accept: application/json' \
  -H 'x-channel-info: WEB' \
  -d ''
```  

### **Örnek RESPONSE**  

```
access-control-allow-origin: *
access-control-expose-headers: x-session-id,x-correlation-id
content-type: application/json; charset=utf-8
date: Wed, 05 Mar 2025 15:35:32 GMT
strict-transport-security: max-age=31536000; includeSubDomains
transfer-encoding: chunked
x-content-type-options: nosniff
x-correlation-id: ca71894c31b84dd18265d061692b4ac1
```  
### ⏭️ **Bir Sonraki Adım**  

👉 Bu servise istek atılıp başarılı bir yanıt alındıysa, bir sonraki adım olarak sözleşmeleri onaylamak için, <a href="#" onclick="loadMarkdown('docs/confirm-contract.md')"><strong>Sözleşmeleri Onayla</strong></a> servisini çağırmalısınız.

