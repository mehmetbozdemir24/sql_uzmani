# SQL Uzmanı (sql_uzmani) Ollama Modeli

Bu proje, doğal dilde yazılan Türkçe soruları **adım adım bir düşünce zinciri (Chain-of-Thought) oluşturarak** SQL sorgularına çevirmek için fine-tune edilmiş bir yapay zeka modelidir. Model, Qwen2.5-14B temel alınarak özel bir SQL veri seti ile eğitilmiştir ve Ollama üzerinde çalışmak üzere GGUF formatında paketlenmiştir.

## Hızlı Başlangıç

Bu modeli kullanmak için bilgisayarınızda [Ollama](https://ollama.com)'nın yüklü olması gerekmektedir.

1.  **Modeli İndirin (Pull):**
    Terminalde aşağıdaki komutu çalıştırarak modeli Ollama Hub'dan bilgisayarınıza indirin:
    ```bash
    ollama pull nypgd/sql_uzmani
    ```

2.  **Modeli Çalıştırın (Run):**
    Modeli interaktif modda çalıştırmak için aşağıdaki komutu kullanın:
    ```bash
    ollama run nypgd/sql_uzmani
    ```

## Örnek Kullanım

Modeli çalıştırdıktan sonra, aşağıdaki gibi bir prompt formatı kullanarak SQL sorgusu üretebilirsiniz:

```text
### Soru:
En çok sipariş veren 5 müşterinin adını ve sipariş sayısını göster.

### Şema:
CREATE TABLE customers (
  customer_id INTEGER PRIMARY KEY,
  customer_name TEXT NOT NULL
);
CREATE TABLE orders (
  order_id INTEGER PRIMARY KEY,
  customer_id INTEGER,
  order_date TEXT,
  FOREIGN KEY (customer_id) REFERENCES customers (customer_id)
);
```
### Gerekçelendirme ve SQL:

## Örnek Çalışma Çıktısı

Aşağıda modelin bir soruya verdiği örnek cevap, düşünce zinciri (Chain-of-Thought) sürecini göstermektedir:

![SQL Uzmanı Modelinin Örnek Çıktısı](https://github.com/mehmetbozdemir24/sql_uzmani/blob/main/resim.jpg)
