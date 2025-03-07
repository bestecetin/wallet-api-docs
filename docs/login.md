
## Login

Sistemde oturum açmak için kullanılacak servistir.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Login

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre | Tip      | Zorunlu | Açıklama                       |
| --------- | -------- | ------- | ------------------------------ |
| `phoneNumber`   | `string` | Evet    | Kullanıcının telefon numarası. |
| `password`   | `string` | Evet    | Kullanıcının şifresi.          |

#### REQUEST BODY

```json
{
  "phoneNumber": "1234567895",
  "password": "123456"
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Login' \
  -H 'accept: application/json' \
  -H 'x-channel-info: api' \
  -H 'Content-Type: application/json' \
  -d '{
  "phoneNumber": "1234567895",
  "password": "123456"
}'
```
#### Örnek RESPONSE

```json
{
  "statusCode": 0,
  "IsSuccess": true,
  "MessageTR": "string",
  "MessageEN": "string",
  "data": {
    "User": {
      "id": "string",
      "name": "string",
      "secondname": "string",
      "surname": "string",
      "phoneNumber": "string",
      "createdAt": "2025-03-03T16:46:04.605Z",
      "passwordShouldChange": true,
      "hasAktifTAccount": true,
      "roles": [
        "string"
      ],
      "userType": "INDIVIDUAL",
      "userAccountType": "STANDART",
      "profilePictureUrl": "string",
      "userNo": 0,
      "isactive": true,
      "securityImageUrl": "string",
      "securityImageId": 0,
      "securityImageSelectedAt": "2025-03-03T16:46:04.605Z",
      "mainEmail": "string",
      "favAccountNo": 0,
      "balanceSum": 0,
      "jobName": "string"
    },
    "message": "string",
    "AccessToken": "string",
    "refreshToken": "string",
    "randomSecurityImages": [
      {
        "id": 0,
        "url": "string"
      }
    ],
    "sessionId": "string",
    "securityToken": "string",
    "isSuccess": true,
    "messageTR": "string",
    "messageEN": "string",
    "statusCode": 0
  },
  "requiresSecurityImageSelection": true
}
```
Response headers içerisinde dönen **x-session-id** bilgisi bütün requestlerde headera aynı isimde eklenmelidir.


📌 **Not:** Kullanıcı sisteme ilk kez giriş yapıyorsa, güvenlik resmi seçmesi gerekmektedir. Güvenlik resmini seçmek ve kaydetmek için <a href="#" onclick="loadMarkdown('docs/set-security-image.md')"><strong>Güvenlik Resmi Seç</strong></a> servisini kullanabilirsiniz.  
