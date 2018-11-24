# Read dan Edit

Langkah awal untuk mengedit data di database serupa seperti menambahkan data ke database. Untuk awal, kita perlu membuat routing terlebih dahulu

```py
@app.route('/edit', methods=['PUT'])
def edit():
    if request.method == 'PUT':
        .
        .
        .
        return 'success', 204
```

Untuk mengetahui data yang ingin diedit, kita perlu melakukan query database berdasarkan email atau data apapun yang dikirim. Metode ini dikenal dengan _Read_

#### 1. Read

Data yang masuk:

```py
request = {
    "email": "makers_institute@gmail.com"
}
```

_Class _yang didefinisikan di dalam file Python:

```py
class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    email = db.Column(db.String())
    password = db.Column(db.String())
    role = db.Column(db.String())
    token = db.Column(db.String())

```

Contoh tabel yang terdapat di database:

| id | email | password | role | token |
| :--- | :--- | :--- | :--- | :--- |
| 1 | makers\_institute@gmail.com | 1234 | Manager | hjakjHAB8787ah.aiAGYUUkij111kuhKUi |

Untuk melakukan query ke database menggunakan SQLAlchemy, definisikan terlebih dahulu request yang masuk. Kemudian, query menggunakan `filter_by`

```py
request_data = request.get_json()
userDB = User.query.filter_by(email=request_data).first()
```



