## Get All Contract User

Bu servis, kullanıcının sistemdeki sözleşmelerini listelemek için kullanılır. 
Servis çağrıldığında, her sözleşme için benzersiz (unique) bir değer oluşturulur ve bu değer sözleşmenin ID’si olarak kabul edilir.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/User/GetAllContractUser

**REQUEST METHOD** : GET

### İstek (Request):

#### Parametreler:

| Parametre      | Tip      | Zorunlu | Açıklama                                                |
| -------------- | -------- | ------- | ------------------------------------------------------- |
| `contractType` | `string` | Evet    | Sözleşme tipi (Örnek: USER\_REGISTER\_FRAME\_CONTRACT). |

#### Sözleşme Tipleri:

| Sözleşme Tipleri            |
| -------------- |
| `USER_REGISTER_FRAME_CONTRACT` | 
| `USER_REGISTER_PRIVACY_CONTRACT` | 
| `USER_REGISTER_KVKK_CONTRACT` | 
| `USER_REGISTER_PRIVAC_CONTRACT` | 

#### Örnek Curl REQUEST

```bash
curl -X 'GET' \
  'https://wallet-api-test.pratikislem.com.tr/api/User/GetAllContractUser?contractType=USER_REGISTER_FRAME_CONTRACT' \
  -H 'accept: application/json' \
  -H 'x-channel-info: API'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Sözleşmeler başarıyla listelendi.",
  "MessageEN": "Contracts have been successfully listed.",
  "data": [
    {
      "id": 2,
      "name": "çerez ",
      "type": 1,
      "url": "https://localhost:7279/swagger/index.html",
      "approvalType": 1,
      "content": "İçerik dizesi...",
      "createdDate": "2025-02-11T10:36:40.854125Z",
      "isActive": true,
      "isMandatory": true,
      "uniqueValue": "00000000-0000-0000-0000-000000000000"
    }
  ],
  "requiresSecurityImageSelection": false
}
```
👉 Bu servise istek gönderildiğinde ve başarılı bir yanıt alındığında, sözleşmenin log kayıtlarını oluşturmak için <a href="#" onclick="loadMarkdown('docs/add-contracts.md')"><strong>Sözleşme Ekle</strong></a> servisini çağırmalısınız.