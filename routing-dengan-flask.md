# Routing dengan Flask

#### 1. Menentukan Endpoint

Routing menggunakan Flask dilakukan dengan menentukan endpoint yang akan diakses dari user. 

```py
@app.route('/endpoint', methods=['GET', 'POST', 'PUT'])
```

Methods yang diassign ke dalam endpoint tersebut diisi sesuai kebutuhan. Jika endpoint tersebut hanya untuk mengubah data di database, maka methods yang diisi adalah `PUT`

#### 2. Membuat Fungsi

Setelah menentukan nama endpoint dan methods yang berlaku, langkah berikutnya adalah mendefinisikan fungsi. Fungsi ter

