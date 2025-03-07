## Start Session

KYC sürecinin başlatılması için kullanıcının kayıtlı telefon numarasına/email adresine indirmesi gereken uygulamanın linki gönderilir. Kullanıcı bu linke tıklayarak uygulamayı indirir ve kimliğini doğrular.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/Onboarding/StartKycSession/StartSession

**REQUEST METHOD** : POST

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/Onboarding/StartKycSession/StartSession' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-channel-info: WEB' \
  -d ''
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "KYC işlemi başlatıldı ve 2 SMS gönderildi.",
  "MessageEN": "KYC process started and 2 SMS messages were sent successfully.",
  "data": "trustchex://app-url/https://kyc.pratikislem.com.tr/verification-session/82d60408-a302-46ed-b109-09e1208221bc",
  "requiresSecurityImageSelection": false
}
```

👉 Bu servise istek atılıp başarılı bir yanıt alındıysa kullanıcının kimliği doğrulanmıştır.
#### ⏭️ Bir Sonraki Adım 
👉 Kullanıcıya bir kart oluşturmak için <a href="#" onclick="loadMarkdown('docs/create-prepaidcard.md')"><strong>Prepaid Kart Oluşturma</strong></a> servisini çağırabilirsiniz.
