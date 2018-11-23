# Create

Sebelum memasukkan data ke database PostgreSQL, kita perlu membuat endpoint yang spesifik untuk mengolah proses pemasukan data tersebut. Pembuatan endpoint dapat dilihat pada materi routing.

```py
@app.route('/insertToDB', methods=['POST'])
def insert_to_db():
    if request.method == 'POST':
        .
        .
        .
        return "Success", 201
```

Data request yang masuk dapat dibaca oleh Flask menggunakan library `request` yang diimport dari `flask` . Kemudian, untuk dapat diakses dengan lebih mudah, request tersebut dapat diubah menjadi format JSON.

```py
request_data = request.get_json()
```

Setiap object dari request yang masuk juga dapat diakses menggunakan key dari masing-masing object. Misalkan data request yang masuk adalah sebagai berikut:

```py
{
    email: "makers@bandung.id",
    password: "makers123",
    role: "tech",
    token: "Bhabj7asiuansiuaghs_OAKJULAkaajo8sh999aanda2i2b*i987H"
}
```

Untuk mengakses objeknya:

```py
email = request_data['email']
password = request_data['password']
role = request_data['role']
token = request_data['token']
```

Setelah itu, kita membuat variabel baru yang berisi data-data yang akan dimasukkan ke dalam database. Variabel baru ini mengacu kepada _class_ saat membuat tabel. Misalnya, data yang dimasukkan ke dalam database adalah data user dengan mengacu kepada _class _`User`.

```py
db_data = User(
    email = request_data['email']
    password = request_data['password']
    role = request_data['role']
    token = request_data['token']
)
```

Saat variabel data sudah dibuat, langkah berikutnya adalah dengan membuat session di database melalui SQLAlchemy. Session merepresentasikan koneksi antara aplikasi \(SQLAlchemy\) dan database \(PostgreSQL\) yang menyimpan object tetapnya.

Pada session kali ini, kita ingin membuat koneksi antara PostgreSQL dengan SQLAlchemy dengan membawa variabel yang berisi data request.

```py
db.session.add(db_data)
db.session.commit()
```

Secara keseluruhan, maka tampilan kode untuk menambahkan data ke database PostgreSQL adalah sebagai berikut.

```py
@app.route('/insertToDB', methods=['POST'])
def insert_to_db():
    if request.method == 'POST':
        request_data = request.get_json()
        # construct data to be sent to DB
        db_data = User(
            email = request_data['email']
            password = request_data['password']
            role = request_data['role']
            token = request_data['token']
        )
        # add data to DB
        db.session.add(sent_data)
        db.session.commit()
        return 'Success', 201
    else:
        return 'Method Not Allowed', 405
```



