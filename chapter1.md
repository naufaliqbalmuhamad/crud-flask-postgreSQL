# Membuat Tabel di Database PostgreSQL dengan Flask

Setelah selesai mengkonfigurasi Flask dengan PostgreSQL dengan SQLAlchemy, langkah selanjutnya adalah membuat tabel pada database yang dikonfigurasikan sebelumnya.

1. Tentukan nama tabel, jumlah kolom, nama tiap kolom, tipe data, dan key
2. Buat sebuah _class _yang merepresentasikan nama tabel
   ```py
   class User(db.Model):
       id = db.Column(db.Integer, primary_key=True)
       email = db.Column(db.String())
       password = db.Column(db.String())
       role = db.Column(db.String())
       token = db.Column(db.String())
   ```
3. Kita dapat menambahkan relationship jika tabel yang dibuat terhubung dengan tabel lain menggunakan foreign key. Misalkan, kita ingin menghubungkan tabel `User` tersebut dengan tabel `Tweets`
   ```py
   tweets = db.relationship('Tweets', backref='owner')
   ```
4. ```py
   class Tweets(db.Model):
       id = db.Column(db.Integer, primary_key=True)
       content = db.Column(db.String(140))
       date = db.Column(db.DateTime(), default=datetime.datetime.utcnow)
       person_id = db.Column(db.Integer, db.ForeignKey('person.id'))
   ```

   "backref" digunakan untuk menghubungkan antar tabel agar dapat dibaca dan dikenali oleh SQLAlchemy untuk dimasukkan ke dalam database PostgreSQL

5. Masuk ke dalam terminal Python![](/assets/get-into-python-terminal.png)
6. Import variabel `db` sebelumnya dari file Python yang sedang dikerjakan![](/assets/import-db-from-python.png)
7. Untuk membuat tabel, kita dapat menggunakan key `db.create_all()`
8. Refresh database untuk melihat tabel yang telah dibuat



