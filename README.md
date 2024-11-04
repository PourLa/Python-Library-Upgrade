# Python Projesindeki Tüm Paketleri Otomatik Güncelleme

Bu betik, Python projenizdeki tüm kurulu paketleri `pip` kullanarak otomatik olarak güncellemenize olanak tanır. Özellikle projenizde kullanılan kütüphanelerin güncel kalmasını sağlamak istediğinizde veya belirli bir paket güncelleme komutu çalıştırmadan tüm paketlerin en son sürümlerini yüklemek için kullanışlıdır.

---

## 📌 Nasıl Çalışır?

Bu betik, Python `pkg_resources` modülünü kullanarak projenizde yüklü olan tüm paketleri listeler. Ardından, her bir paketi `pip install --upgrade <paket_adi>` komutu ile günceller.

---

## 📜 Kod

Aşağıdaki kod, tüm yüklü paketleri güncellemek için kullanılmaktadır:

```python
import pkg_resources
from subprocess import call

# Yüklü tüm paketleri listele
packages = [dist.project_name for dist in pkg_resources.working_set]

# Her paketi güncelle
for package in packages:
    call(f"pip install --upgrade {package}", shell=True)
```

🚀 Kullanım

Bu betiği çalıştırmak için aşağıdaki adımları izleyin:

	1.	Python’ın kurulu olduğundan emin olun.
	2.	Terminal veya komut satırında aşağıdaki komutu çalıştırarak bu betiği çalıştırın:

```bash
python update_all_packages.py
```
	3.	Betik, tüm yüklü paketleri tek tek güncelleyerek en güncel sürümlerini yükleyecektir.

	Not: Bu betiği çalıştırmadan önce sanal bir ortam (virtual environment) kullanmanız tavsiye edilir. Tüm sistem paketlerini güncellemek yerine, yalnızca proje gereksinimlerinizi güncellemek daha güvenlidir.

⚠️ Uyarılar

	•	Bağımlılık Uyum Sorunları: Bu betik, güncellenen bazı paketlerin bağımlılık uyumsuzluğu veya hata yaratması durumunda proje üzerinde istenmeyen etkilere neden olabilir. Güncellemeden önce yedek almak veya sanal bir ortamda çalışmak en iyisidir.
	•	Komut Uyumsuzlukları: call() komutu işletim sistemine özgüdür ve bu nedenle bazı işletim sistemlerinde veya Python sürümlerinde farklı davranışlar gösterebilir.

💬 Geri Bildirim

Herhangi bir sorun yaşarsanız, lütfen bir issue oluşturun veya katkıda bulunun!

Bu README.md, projeye açıklık getirir ve kodun nasıl çalıştığını, kullanım adımlarını ve bazı önemli uyarıları içeren bilgiler sağlar.
```python
Bu düzenleme ile başlıklar ve kod blokları daha belirgin hale getirildi. Her bölüm arasına ayırıcı çizgiler eklendi ve simgelerle başlıklar dikkat çekici hale getirildi.
```
