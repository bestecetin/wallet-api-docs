# **DijiPratik Cüzdan**

DijiPratik Cüzdan, tüm finansal işlemlerinizi tek bir platformdan yönetmenizi sağlayan güvenilir ve pratik bir dijital cüzdan çözümüdür. **DijiPratik Cüzdan** altyapısı sayesinde hem bireysel hem de kurumsal kullanıcılar, bakiyelerini güvenle saklayabilir, transfer işlemlerini kolayca gerçekleştirebilir ve finansal hesaplarını tek bir panel üzerinden yönetebilir. **DijiPratik Cüzdan** entegrasyonu sayesinde, her kullanıcı ihtiyaçlarına uygun bir dijital cüzdana sahip olabilir ve finans yönetimini zahmetsizce gerçekleştirebilir.


## **🚀 DijiPratik ile Neler Yapabilirsiniz?**
### **Cüzdana Kayıt Olma**
Yeni kullanıcılar için güvenli bir cüzdan hesabı oluşturun.
- <a href="#" onclick="loadMarkdown('docs/register.md')"><strong>Bireysel hesap oluştur</strong></a>
- Telefon <a href="#" onclick="loadMarkdown('docs/add-phone.md')"><strong>kaydet</strong></a> ve <a href="#" onclick="loadMarkdown('docs/validate-otp-phone.md')"><strong> doğrula </strong></a>
- E-posta <a href="#" onclick="loadMarkdown('docs/add-email.md')"><strong>kaydet</strong></a> ve <a href="#" onclick="loadMarkdown('docs/validate-otp-email.md')"><strong> doğrula </strong></a>
- Sözleşmeleri <a href="#" onclick="loadMarkdown('docs/get-all-contracts.md')"><strong>listele</strong></a>, <a href="#" onclick="loadMarkdown('docs/add-contracts.md')"><strong> ekle</strong></a>, <a href="#" onclick="loadMarkdown('docs/confirm-contract-if-opened.md')"><strong> kontrol et </strong></a>, <a href="#" onclick="loadMarkdown('docs/confirm-contract.md')"><strong> onayla </strong></a> , <a href="#" onclick="loadMarkdown('docs/update-contracts.md')"><strong> eşleştir </strong></a>
- <a href="#" onclick="loadMarkdown('docs/add-password.md')"><strong>Parola oluştur</strong></a>

### 🔍 **KYC (Know Your Customer) Kontrolü**
Kimlik doğrulama süreçlerini tamamlayarak cüzdanınızı aktif hale getirin.
- <a href="#" onclick="loadMarkdown('docs/save-info.md')"><strong>Sözleşmeli hesaba geç </strong></a>
- <a href="#" onclick="loadMarkdown('docs/validate-address.md')"><strong>Adres doğrula</strong></a>
- <a href="#" onclick="loadMarkdown('docs/start-session.md')"><strong>Dijital kimlik doğrulama</strong></a>

### **Kart Yönetimi**
Dijital kartlarınızı oluşturun ve yönetin. 
-  <a href="#" onclick="loadMarkdown('docs/create-prepaidcard.md')"><strong>Sanal Kart oluştur</strong></a>
-  <a href="#" onclick="loadMarkdown('docs/card-assign.md')"><strong>Fiziki Kart Tanımla</strong></a>
-  <a href="#" onclick="loadMarkdown('docs/list-cards.md')"><strong>Kartları listele</strong></a>

### **Finansal Hareketleri Takip Etme**
Gerçekleşen işlemleri detaylı bir şekilde görüntüleyin.
- <a href="#" onclick="loadMarkdown('docs/wallet-transactions.md')"><strong>Cüzdan hareketlerini görüntüle</strong></a>
- <a href="#" onclick="loadMarkdown('docs/wallet-list.md')"><strong>Cüzdanları listele</strong></a>


## **API Kullanımı İçin Oturum Açma**  
👉 DijiPratik API'lerini kullanabilmek için öncelikle oturum açmanız gerekmektedir. Oturum açmak için <a href="#" onclick="loadMarkdown('docs/login.md')"><strong>Oturum Aç</strong></a> servisini çağırabilirsiniz.

## **Kullanıcı Oturum Açma**  
👉 DijiPratik hesabı ile kullanıcının işlem yapabilmesi ve hesap yükseltebilmesi için önce kullanıcıya bir oturum açmanız gerekmektedir. Bunun için <a href="#" onclick="loadMarkdown('docs/login.md')"><strong>Oturum Aç</strong></a> servisini kullanabilirsiniz.  

📌 **Not:** Kullanıcı sisteme ilk kez giriş yapıyorsa, güvenlik resmi seçmesi gerekmektedir. Güvenlik resmini seçmek ve kaydetmek için <a href="#" onclick="loadMarkdown('docs/set-security-image.md')"><strong>Güvenlik Resmi Seç</strong></a> servisini kullanabilirsiniz.  

---

## **API Genel Yapısı**

Bütün servisler aşağıdaki formatta JSON cevabı döner:

```json
{
  "statusCode": 0,
  "IsSuccess": true,
  "MessageTR": "string",
  "MessageEN": "string",
  "data": {}
}
```

### **🚨 Hata ve İstisna Durumları**
- Yetkisiz işlem yapıldığında (**FORBIDDEN**), **403 HTTP** statu kodu döner.
- Kimlik doğrulama gerektiren servislere eksik veya yanlış token ile erişildiğinde, **401 (UNAUTHORIZED)** HTTP kodu döner.

---

## **Header Bilgileri**
Servis çağrılarında aşağıdaki header bilgileri kullanılmalıdır:

| Header          | Açıklama |
|----------------|----------|
| **x-session-id** | Login servisinden dönen oturum ID’sidir. |
| **x-channel-info** | `API` olarak gönderilmelidir. |

---

## **⏳ Oturum Süreleri**
Kullanıcılar belirli bir süre işlem yapmadıklarında oturumları sona erer ve tekrar giriş yapmaları gerekir. Alternatif olarak,Refresh Token servisi ile oturumlarını yenileyebilirler.

| Ortam  | Oturum Süresi |
|--------|--------------|
| **Canlı Ortam (PROD)** | 2 saat |
| **Test Ortamı (STAGING)** | 6 saat |

