# Spring Data JPA – Pagination & Sorting

Pagination (sayfalama), Sorting (sıralama)

![alt text](images/image-8.png)

Pagination ve Sorting,  
büyük veri setleriyle çalışırken  
**performansı artırmak** ve  
**kullanıcıya kontrollü veri sunmak**  
için kullanılan yapılardır.

---

## Pagination Nedir?

Pagination, verilerin **parça parça (sayfa sayfa)** getirilmesini sağlar.

Amaç:
- Tüm veriyi tek seferde çekmemek
- Performans problemlerini önlemek
- Kullanıcı deneyimini artırmak

Örnek:
- 1000 kayıt var
- Her sayfada 10 kayıt
- Toplam 100 sayfa

---

## Sorting Nedir?

Sorting, verilerin belirli bir alana göre  
**artan (ASC)** veya **azalan (DESC)** şekilde sıralanmasını sağlar.

Örnek:
- İsme göre sırala
- Tarihe göre azalan sırala

---

## Spring Data JPA’da Pagination Nasıl Yapılır?

Spring Data JPA, pagination için  
`Pageable` ve `Page` yapılarını sunar.

---

## Pageable Nedir?

`Pageable`, sayfalama bilgisini tutar:
- Sayfa numarası
- Sayfa boyutu
- Sıralama bilgisi


---

## Repository’de Pageable Kullanımı

![alt text](images/image.png)

📌 `findAll(Pageable pageable)` metodu otomatik olarak gelir.

---

## Service Katmanında Pagination

![alt text](images/image-1.png)

📌 Sayfa numarası **0’dan** başlar.

---

## Controller Katmanında Pagination

![alt text](images/image-2.png)

📌 Örnek istek:

![alt text](images/image-3.png)

---

## Sorting Kullanımı

![alt text](images/image-4.png)

📌 Azalan sıralama:

![alt text](images/image-5.png)

---

## Pagination + Sorting Birlikte Kullanımı

![alt text](images/image-6.png)

---

## Page Nesnesi İçeriği

`Page<T>` aşağıdaki bilgileri içerir:

- `getContent()` → Sayfadaki veriler
- `getTotalElements()` → Toplam kayıt sayısı
- `getTotalPages()` → Toplam sayfa sayısı
- `getNumber()` → Mevcut sayfa numarası
- `isFirst()` / `isLast()`

---

## Pagination + DTO Kullanımı

Pagination entity yerine DTO ile de kullanılabilir.

![alt text](images/image-7.png)

---

## Pagination Kullanmanın Avantajları

- Büyük veri setlerinde performans artar
- Bellek kullanımı azalır
- Daha kontrollü API response’ları sağlanır
- Frontend tarafı için idealdir

---

## Dikkat Edilmesi Gerekenler

- Page index **0’dan** başlar
- Büyük page size performans sorunlarına yol açabilir
- Sorting alanı entity field adıyla aynı olmalıdır

---

## Özet

- Pagination veriyi sayfa sayfa getirir
- Sorting veriyi sıralar
- Spring Data JPA’da `Pageable` ve `Page` kullanılır
- Pagination ve Sorting birlikte kullanılabilir
- Profesyonel REST API’lerde standarttır
