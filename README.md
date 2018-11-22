# Menghubungkan Flask dengan database PostgreSQL

Materi berikut akan menjelaskan bagaimana cara melakukan CRUD \(_Create, Read, Update_, dan _Delete_\) menggunakan Flask, yang berbasis Python ke database PostgreSQL.

Sebelumnya, kerjakan terlebih dahulu langkah-langkah berikut:

1. Membuat file dengan ekstensi .py \(Python\)
2. Melakukan import beberapa library, seperti flask, flask\_sqlalchemy, flask\_restful, dan lainnya![](/assets/import_flask.png)
   Jika library belum tersedia di root Python, download terlebih dahulu library-library tersebut pada terminal dengan menggunakan package manager "pip".
   ```
   pip install flask_sqlalchemy
   ```
3. Setelah itu, pastikan database sudah dibuat di PostgreSQL, dengan nama database, user, password, host, dan port yang benar.
4. Inisiasi flask di dalam file tersebut dengan menuliskan
   ```
   app = Flask(__name__)
   ```
5. Konfigurasi 







