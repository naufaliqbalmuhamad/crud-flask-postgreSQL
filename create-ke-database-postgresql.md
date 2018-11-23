# Create ke Database PostgreSQL

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

```
{
    email: "makers@bandung.id",
    password: "makers123",
    role: "tech",
    token: "Bhabj7asiuansiuaghs_OAKJULAkaajo8sh999aanda2i2b*i987H"
}
```

Untuk mengakses objeknya:

```
email = request_data['email']
password = request_data['password']
role = request_data['role']
token = request_data['token']
```

Setelah itu, kita membuat variabel baru yang berisi data-data yang akan dimasukkan ke dalam database. Variabel baru ini mengacu kepada \_class \_saat membuat tabel. Misalnya, data yang dimasukkan ke dalam database adalah data user dengan mengacu kepada _class _`User`.

```
db_data = User(
    
)
```



