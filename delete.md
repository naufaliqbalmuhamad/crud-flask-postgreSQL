# Delete

Sama seperti Read dan Edit, sebelum Delete kita perlu membuat routing terlebih dahulu

```py
@app.route('/delete', methods=['DELETE'])
def delete():
    if request.method == 'DELETE':
        .
        .
        .
        return 'success', 200
```

Setelah itu, kita melakukan query ke database menggunakan data yang masuk untuk mengetahi data mana yang akan dihapus di database. Data yang masuk perlu didefinisikan terlebih dahulu

```py
request = {
    'email': 'payung_seduh@gmail.com'
}

request_data = request.get_json()
request_email = request_data['email']
```

Query yang digunakan sama seperti sebelumnya

```py
dataDB = User.query.filter_by(email=request_email).first()
```

Delete data menggunakan SQLAlchemy dapat dilakukan dengan delete session dan commit

```py
db.session.delete(dataDB)
db.session.commit()
```

Sehingga tampilan routing untuk delete data di database menjadi seperti berikut

```py
@app.route('/delete', methods=['DELETE'])
def delete():
    if request.method == 'DELETE':
        request_data = request.get_json()
        request_email = request_data['email']

        dataDB = User.query.filter_by(email=request_email).first()
        db.session.delete(dataDB)
        db.session.commit()           

        return 'success', 200
```



