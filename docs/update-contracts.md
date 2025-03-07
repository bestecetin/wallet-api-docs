## Update Contracts Log With User ID  

Bu servisi kullanmak için, **Register** servisinden dönen AccessToken bilgisinin Authorization başlığına **Bearer Token** yerine eklenmesi gerekmektedir.

**REQUEST URL** : `https://wallet-api-test.pratikislem.com.tr/api/User/UpdateContractsLogWithUserId?uniqueValue=54e53fdf-9d78-4587-a3d0-1c7fb681cb6e`  

**REQUEST METHOD** : `POST`  

### İstek (Request):

#### Parametreler:

| Parametre    | Tip       | Zorunlu | Açıklama                                      |
|-------------|----------|---------|-----------------------------------------------|
| `uniqueValue` | `string` | Evet    | Kullanıcıya ait benzersiz sözleşme değeri. |

#### **Örnek Curl **  

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/User/UpdateContractsLogWithUserId?uniqueValue=54e53fdf-9d78-4587-a3d0-1c7fb681cb6e' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6IiIsIm5hbWUiOiJIYWthbiIsIm5hbWVpZCI6ImpxOTRTYlEwRG5nTkNveE56S0Evc1hYdXh4VGtqVUg3dlRkMk85THllS0lmbXpyeWhVVXhSdkJEUURDUndkbmoiLCJwaG9uZV9udW1iZXIiOiIiLCJyb2xlIjpbInJlZ2lzdGVyIiwidmFsaWRhdGVPVFAiXSwibmJmIjoxNzQxMjcyNTA5LCJleHAiOjE3NDE1MzE3MDksImlhdCI6MTc0MTI3MjUwOSwiaXNzIjoiZS1jdXpkYW4tYXBpIiwiYXVkIjoiZS1jdXpkYW4tY2xpZW50In0.DGi4BF2TO2B2EIHpaLVxUrKHggOFdDjWjKC_7Nc7ETa8IIm_b98-40LmTZyaHZBF8JLLp_AQEFrN7-zkVXRR5g' \
  -H 'x-channel-info: WEB' \
  -d ''
```  

### **Örnek RESPONSE**  

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "data": "Kullanıcı id (794b1e80-2046-4513-a264-f82b0cf2e5d7) sözleşme log kaydına güncellendi.",
  "requiresSecurityImageSelection": false
}
```  

### ⏭️ **Bir Sonraki Adım**  

👉 Bu servise istek gönderip başarılı bir yanıt aldıysanız, kullanıcı sözleşmeleri okunmuş ve onaylanmıştır. Bir sonraki adım olan Parola Oluştur aşamasına geçebilirsiniz.

📌 Parola oluşturmak için:
<a href="#" onclick="loadMarkdown('docs/add-password.md')"><strong>Parola Oluştur</strong></a> servisini çağırmalısınız.

⚠️ Not: Sözleşmeler onaylanmadıysa, Parola Oluştur servisini çağırmamalısınız. Sözleşme adımlarına başlamak için:
📌 <a href="#" onclick="loadMarkdown('docs/get-all-contracts.md')"><strong>Sözleşmeleri Listele</strong></a> servisini çağırmalısınız.
