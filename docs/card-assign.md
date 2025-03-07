## Assign Physical Card

Kullanıcıya fiziksel kart tanımlayan servistir.

**REQUEST URL** : https://localhost:7279/api/Account/AssignPhysicalCard/assign-physical-card

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre           | Tip     | Açıklama                      |
|---------------------|---------|--------------------------------|
| `cardBarcode`      | string  | Kartın barkod numarası        |
| `last4Digits`      | string  | Kartın son 4 hanesi           |
| `cardFriendlyName` | string  | Kartın adı    |

#### REQUEST BODY

```json
{
  "cardBarcode": "4388563",
  "last4Digits": "5012",
  "cardFriendlyName": "En Yeni"
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://localhost:7279/api/Account/AssignPhysicalCard/assign-physical-card' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InpYNW9jVlJ3bVpGWThFTm9VcWlFUzR1ZHhrdU01WWpHTnN5ZVFzb1pvd3c9IiwibmFtZSI6IkVuZXMiLCJuYW1laWQiOiJsbkpDQ05GNUx5VGttRW51ZlV4MkxXS1ZaZUVVWmxwajVpSUxmYVZweWlwamN5TWJkR1V4SFV1TFp1blBTMjZnIiwicGhvbmVfbnVtYmVyIjoid29na3AzVkw1NDB4MjEzVGdVclNKdz09Iiwicm9sZSI6WyJ1c2VyIiwic3VwZXJhZG1pbiIsImFkbWluIl0sIm5iZiI6MTc0MTI5NDMyNSwiZXhwIjoxNzQxNTUzNTI1LCJpYXQiOjE3NDEyOTQzMjUsImlzcyI6ImUtY3V6ZGFuLWFwaSIsImF1ZCI6ImUtY3V6ZGFuLWNsaWVudCJ9.WoVsdW-4UJrig6IyyLe25IY2a8V0aSS4kScd6A3t1EN5AdHqkD_FqKKBIDO-1zk1PPd9oIFm40hq7JMx8tLknw' \
  -H 'x-session-id: xklX0uQe5sBlcBZ2nHiuSikbwBQU1kOMP0hdFadsIgtQ0QUfbSQB7luywPfNvOzP' \
  -H 'x-channel-info: WEB' \
  -H 'Content-Type: application/json' \
  -d '{
  "cardBarcode": "4388563",
  "last4Digits": "5012",
  "cardFriendlyName": "En Yeni"
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Kart başarıyla tanımlandı ve favori hesaba bağlandı. Tüm izinler false olarak atandı.",
  "MessageEN": "Card assigned successfully and linked to favorite account. All permissions set to false.",
  "data": {
    "cardId": 49,
    "cardNumber": "2663992667255012",
    "createdAt": "2025-03-06T21:11:05.4918816Z",
    "cardFriendlyName": "En Yeni"
  },
  "requiresSecurityImageSelection": false
} "requiresSecurityImageSelection": false
```
