## Register Personal Account

Giriş yapan yönetici hesabına bağlı olacak şekilde yeni müşteri kartı oluşturmak için kullanılır.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Register

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre     | Tip      | Zorunlu | Açıklama                                           |
| ------------- | -------- | ------- | -------------------------------------------------- |
| `name`        | `string` | Evet    | Kullanıcının adı.                                  |
| `surname`     | `string` | Evet    | Kullanıcının soyadı.                               |
| `identityNumber`        | `string` | Evet    | Kullanıcının T.C. kimlik numarası.                 |
| `birthDay` | `string` | Evet    | Kullanıcının doğum tarihi (YYYY-AA-GG formatında). |

#### REQUEST BODY

```json
{
  "singleBody": {
    "name": "Beste",
    "surname": "Cetin",
    "identityNumber": "60382173875",
    "birthDay": "1997-03-04"
  }
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Register' \
  -H 'accept: application/json' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "singleBody": {
    "name": "Beste",
    "surname": "Cetin",
    "identityNumber": "60382173875",
    "birthDay": "1997-03-04"
  }
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 201,
  "IsSuccess": true,
  "MessageTR": "Kullanıcı oluşturuldu",
  "MessageEN": "User created",
  "data": {
    "User": {
      "User": {
        "id": "gpcDsB3G8kh+VBG6aPzaZn3+6Juz5/RVvtUfnh6qHi4IKsdY6T+tAPsbPvGFvcL4",
        "name": "Beste",
        "secondname": "",
        "surname": "Cetin",
        "createdAt": "2025-03-04T09:11:42.380909Z",
        "passwordShouldChange": false,
        "hasAktifTAccount": false,
        "userType": "INDIVIDUAL",
        "userAccountType": "STANDART",
        "userNo": 500145,
        "isactive": false
      },
      "AccessToken": "eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6IiIsIm5hbWUiOiJCZXN0ZSIsIm5hbWVpZCI6ImdwY0RzQjNHOGtoK1ZCRzZhUHphWm4zKzZKdXo1L1JWdnRVZm5oNnFIaTRJS3NkWTZUK3RBUHNiUHZHRnZjTDQiLCJwaG9uZV9udW1iZXIiOiIiLCJyb2xlIjpbInJlZ2lzdGVyIiwidmFsaWRhdGVPVFAiXSwibmJmIjoxNzQxMDc5NTAyLCJleHAiOjE3NDEzMzg3MDIsImlhdCI6MTc0MTA3OTUwMiwiaXNzIjoiZS1jdXpkYW4tYXBpIiwiYXVkIjoiZS1jdXpkYW4tY2xpZW50In0.nNcwyNJUyUav2PwldJ6v-3DjUwB8AImuHUgDWmdUDRVH3DIOZngAaIrj-QsfY_BKwbe8U4TRk0zwPDJ2_sjyRg",
      "isSuccess": false,
      "statusCode": 0
    },
    "hasPhoneNumber": false,
    "phoneNumberConfirmed": false,
    "hasEmail": false,
    "emailConfirmed": false,
    "hasPassword": false,
    "contracts": [],
    "hasContract": false
  },
  "requiresSecurityImageSelection": false
}
```
#### ⏭️ Bir Sonraki Adım

👉 Kullanıcıya telefon numarası eklemek için:
<a href="#" onclick="loadMarkdown('docs/add-phone.md')"><strong>Telefon Ekle</strong></a> servisini çağırmalısınız.

veya

👉Kullanıcıya mail eklemek için:
<a href="#" onclick="loadMarkdown('docs/add-email.md')"><strong>Mail Ekle</strong></a> servisini çağırmalısınız.