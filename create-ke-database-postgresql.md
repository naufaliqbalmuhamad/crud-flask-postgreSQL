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



