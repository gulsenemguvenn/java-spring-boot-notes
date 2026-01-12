# ⚙️ Property File Configuration (application.properties / application.yml)

## 📌 Nedir?
Spring Boot’ta uygulama ayarları (config) genellikle:
- `application.properties`
- `application.yml`

dosyalarında tutulur.

Bu dosyalar sayesinde:
- port, database bağlantısı, log seviyesi gibi ayarlar yönetilir
- ortam (dev/test/prod) bazlı farklı config yapılabilir
- kodu değiştirmeden davranış değiştirilebilir

Bu yapı spring projesi oluşturulduğunda default olarak projenin içinde gelir.
![alt text](images/image-11.png)

---

## 🧩 application.properties vs application.yml

### ✅ application.properties
Anahtar = değer şeklinde yazılır.

server.port=8080
spring.application.name=demo-app

✅ application.yml

Hiyerarşik (indentation) yapı sunar.

![alt text](images/image.png)

YML’de boşluk (indent) önemlidir.

Sık Kullanılan Ayarlar
🌐 Server Port

![alt text](images/image-1.png)

🗄️ Database Connection (Örnek: PostgreSQL)

![alt text](images/image-2.png)

📌 Environment (Profile) Kullanımı
✅ Profile Nedir?

Aynı uygulamanın farklı ortamlarda (dev/test/prod) farklı ayarlarla çalışmasını sağlar.

1️⃣ application-dev.properties
src/main/resources/ içine eklenir:
![alt text](images/image-3.png)

2️⃣ application-prod.properties
![alt text](images/image-4.png)

Aktif Profile Belirleme
application.properties üzerinden:
![alt text](images/image-5.png)

Terminal ile:
![alt text](images/image-6.png)

@Value ile Property Okuma
Config dosyasından değer almak için:
![alt text](images/image-7.png)

![alt text](images/image-8.png)
@Value küçük kullanımlarda pratik, ama büyüdükçe yönetmesi zorlaşabilir.

✅ @ConfigurationProperties (Daha Profesyonel Kullanım)
1️⃣ properties
![alt text](images/image-9.png)

2️⃣ class
![alt text](images/image-10.png)
Bu yöntem, çok sayıda config değerini yönetmek için daha temizdir.

🔐 Gizli Bilgiler (Şifre vs) için Not

Şifreleri doğrudan repoya yazmak risklidir.

.env, secrets veya CI/CD secret yönetimi kullanılmalıdır.

GitHub’a açık repo atarken password gibi bilgileri paylaşmamak gerekir.

⚠️ Sık Yapılan Hatalar

YML’de indent hatası (boşluklar)

Yanlış profile aktif etmek

Key isimlerinde yazım hatası (Spring değeri bulamaz)


✅ Özet

Property file configuration sayesinde:

uygulama ayarlarını koddan ayırırız

ortam bazlı farklı yapılandırma yaparız (profiles)

daha temiz ve yönetilebilir bir backend yapısı kurarız

applicaiton.yml
![alt text](images/image-12.png)

