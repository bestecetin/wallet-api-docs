## Set Security Image  

Kullanıcının güvenlik resmini belirlemek için kullanılır.  

**REQUEST URL** : `https://wallet-api-test.pratikislem.com.tr/api/UserAccount/SetSecurityImage/set-security-image`  

**REQUEST METHOD** : `POST`  

### İstek (Request):

#### Parametreler:

| Parametre         | Tip       | Zorunlu | Açıklama                                  |
|------------------|----------|---------|------------------------------------------|
| `securityToken`   | `string`  | Evet    | Kullanıcının güvenlik doğrulama tokenı.  |
| `securityImageId` | `integer` | Evet    | Kullanıcının seçeceği güvenlik resim ID’si. |

#### REQUEST BODY

```json
{
  "securityToken": "eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9...",
  "securityImageId": 2
}
```  

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/UserAccount/SetSecurityImage/set-security-image' \
  -H 'accept: application/json' \
  -H 'x-channel-info: WEB' \
  -H 'Content-Type: application/json' \
  -d '{
  "securityToken": "eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9...",
  "securityImageId": 2
}'
```  

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Güvenlik resmi başarıyla ayarlandı.",
  "MessageEN": "Security image successfully set.",
  "requiresSecurityImageSelection": false
}
```  
#### ⏭️ Bir Sonraki Adım 
👉 Kullanıcıyı sözleşmeli hesaba geçirmek istiyorsanız <a href="#" onclick="loadMarkdown('docs/save-info.md')"><strong>Kişisel Bilgiler</strong></a> servisini çağırabilirsiniz.