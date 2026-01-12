# ✅ JUnit 5 (JUnit Jupiter)

## 📌 JUnit 5 Nedir?
JUnit 5, Java projelerinde **unit test** yazmak için kullanılan modern test framework’üdür.  
JUnit 5 temelde 3 parçadan oluşur:
- **JUnit Platform**: Testleri çalıştıran altyapı
- **JUnit Jupiter**: JUnit 5 test API’si (en çok kullandığımız kısım)
- **JUnit Vintage**: JUnit 4 testlerini çalıştırma desteği

---

## 🎯 Neden Test Yazarız?
- Kodun doğru çalıştığını kanıtlamak
- Refactor yaparken güvenli ilerlemek
- Hataları erken yakalamak
- Kod kalitesini ve sürdürülebilirliği artırmak

---

## ⚙️ Maven Dependency
Spring Boot kullanıyorsan genelde zaten gelir (`spring-boot-starter-test`).  
Eklemek istersen:

![alt text](images/image-1.png)

Sadece JUnit 5 istersem:

![alt text](images/image.png)

🧩 Temel Anotasyonlar

✅ @Test

Test metodu olduğunu belirtir.

![alt text](images/image-3.png)

Assertions (Beklenen Sonuç Kontrolü)

Assertions, testin pass/fail olmasına karar verir.

assertEquals

![alt text](images/image-4.png)

assertTrue / assertFalse

![alt text](images/image-5.png)

assertNotNull / assertNull

![alt text](images/image-6.png)

assertThrows

Beklenen exception’ı kontrol eder.

![alt text](images/image-7.png)

assertAll

Birden fazla assertion’ı birlikte çalıştırır (hepsi raporlanır).

![alt text](images/image-8.png)

🔁 Test Lifecycle (Ömür Döngüsü)

@BeforeEach / @AfterEach

Her testten önce/sonra çalışır.

![alt text](images/image-9.png)

@BeforeAll / @AfterAll

Tüm testlerden önce/sonra 1 kez çalışır. static olmalıdır.

![alt text](images/image-10.png)

Testleri Daha Okunaklı Yapmak

@DisplayName

Test ismini daha anlaşılır gösterir.

![alt text](images/image-11.png)

@Disabled

Testi geçici olarak devre dışı bırakır.

![alt text](images/image-12.png)

🔂 Parametrized Test (Bir Testi Farklı Verilerle Çalıştırma)

@ValueSource

![alt text](images/image-13.png)

@CsvSource

![alt text](images/image-14.png)


Unit Test Mantığı (Arrange - Act - Assert)

Test yazarken en net yaklaşım:

Arrange: Test verisini hazırla

Act: Metodu çalıştır

Assert: Beklenen sonucu doğrula

![alt text](images/image-15.png)


Spring Boot ile Test (Kısa Notlar)

@SpringBootTest

Uygulamayı ayağa kaldırarak test eder (integration test’e yakındır).

![alt text](images/image-16.png)

Not: @SpringBootTest ağır olabilir, her testte kullanmak yerine gerekli yerde kullanılır.

⚠️ Sık Yapılan Hatalar

- Assertion yazmadan test bırakmak (test “geçer” ama doğrulama yok)

- Her testte @SpringBootTest kullanmak (testleri yavaşlatır)

- Testlerin birbirine bağımlı olması (sıra değişince patlar)

✅ Özet

JUnit 5 ile:

- @Test ve assertions kullanarak unit test yazılır

- @BeforeEach / @AfterEach ile hazırlık ve temizlik yapılır

- Parametrized test ile aynı test farklı verilerle çalıştırılır

- Spring Boot tarafında @SpringBootTest ile uygulama context’i test edilebilir