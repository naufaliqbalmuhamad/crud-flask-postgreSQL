# Routing dengan Flask

#### 1. Menentukan Endpoint

Routing menggunakan Flask dilakukan dengan menentukan endpoint yang akan diakses dari user.

```py
@app.route('/endpoint', methods=['GET', 'POST', 'PUT'])
```

Methods yang diassign ke dalam endpoint tersebut diisi sesuai kebutuhan. Jika endpoint tersebut hanya untuk mengubah data di database, maka methods yang diisi adalah `PUT`

#### 2. Membuat Fungsi

Setelah menentukan nama endpoint dan methods yang berlaku, langkah berikutnya adalah mendefinisikan fungsi. Fungsi tersebut akan dieksekusi saat endpoint diakses

```py
def edit_profile():
    .
    .
    .
    return "OK", 200
```

Tampilan akhir dari sebuah endpoint untuk routing adalah sebagai berikut

```py
@app.route('/endpoint', methods=['PUT'])
def edit_profile():
    .
    .
    .
    return "OK", 200
```

> Suatu endpoint dapat ditambahkan beberapa fungsi sesuai kebutuhan



