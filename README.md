# Python Projesindeki Tüm Paketleri Otomatik Güncelleme

Bu betik, Python projenizdeki tüm kurulu paketleri `pip` kullanarak otomatik olarak güncellemenize olanak tanır. Özellikle projenizde kullanılan kütüphanelerin güncel kalmasını sağlamak istediğinizde veya belirli bir paket güncelleme komutu çalıştırmadan tüm paketlerin en son sürümlerini yüklemek için kullanışlıdır.

## Nasıl Çalışır?

Betik, Python `pkg_resources` modülünü kullanarak projenizde yüklü olan tüm paketleri listeler. Ardından, her bir paketi `pip install --upgrade <paket_adi>` komutu ile günceller.

## Kod

```python
import pkg_resources
from subprocess import call

# Yüklü tüm paketleri listele
packages = [dist.project_name for dist in pkg_resources.working_set]

# Her paketi güncelle
for package in packages:
    call(f"pip install --upgrade {package}", shell=True)
