# Menghubungkan Flask dengan database PostgreSQL

Materi berikut akan menjelaskan bagaimana cara melakukan CRUD \(_Create, Read, Update_, dan _Delete_\) menggunakan Flask, yang berbasis Python ke database PostgreSQL.

Sebelumnya, kerjakan terlebih dahulu langkah-langkah berikut:

1. Membuat file dengan ekstensi .py \(Python\)
2. Melakukan import beberapa library, seperti flask, flask\_sqlalchemy, flask\_restful, dan lainnya![](/assets/import_flask.png)
   Jika library belum tersedia di root Python, download terlebih dahulu library-library tersebut pada terminal dengan menggunakan package manager `pip install`.
   ```
   pip install flask_sqlalchemy
   ```
3. Setelah itu, pastikan database sudah dibuat di PostgreSQL, dengan nama database, user, password, host, dan port yang benar.
4. Inisiasi flask di dalam file tersebut dengan menuliskan
   ```
   app = Flask(__name__)
   ```
5. Tambahkan konfigurasi`['SQLALCHEMY_DATABASE_URI']` padd variabel`app` sebelumnya dengan alamat, user, password, host, post, dan nama database yang telah dibuat sebelumnya
   ```
   app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://postgres:KadaL123@localhost:5432/Twitter'
   ```
6. Pada case ini, kita menggunakan SQLAlchemy sebagai tools untuk menghubungan Python dengan database PostgreSQL. Untuk dapat menggunakannya, deklarasikan ketiganya dalam suatu variabel baru.
   ```
   db = SQLAlchemy(app)
   ```

   Variabel `db` tersebut akan digunakan pada kode-kode selanjutnya untuk melakukan CRUD ke database.





