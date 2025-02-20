# Peralatan--Darurat
DAFTAR PERALATAN DARURAT PT. INTERA LESTARI POLIMER
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Data Alat Peralatan Darurat</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        table, th, td {
            border: 1px solid black;
        }
        th, td {
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #f8b400;
            color: white;
        }
        .form-group {
            margin-top: 20px;
        }
        .form-group input {
            padding: 10px;
            width: 100%;
            margin: 5px 0;
        }
        .form-group button {
            background-color: #f8b400;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Data Alat Peralatan Darurat</h2>
        <label for="search">Cari Alat:</label>
        <input type="text" id="search" placeholder="Cari nama alat..." onkeyup="searchTable()">
        
        <table id="equipmentTable">
            <thead>
                <tr>
                    <th>Nama Alat</th>
                    <th>Jenis</th>
                    <th>Kondisi</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>APAR</td>
                    <td>Alat Pemadam</td>
                    <td>Baik</td>
                </tr>
                <tr>
                    <td>First Aid Kit</td>
                    <td>Kotak P3K</td>
                    <td>Baik</td>
                </tr>
            </tbody>
        </table>
        
        <div class="form-group">
            <h3>Tambah Alat Baru</h3>
            <input type="text" id="namaAlat" placeholder="Nama Alat">
            <input type="text" id="jenisAlat" placeholder="Jenis Alat">
            <input type="text" id="kondisiAlat" placeholder="Kondisi">
            <button onclick="tambahAlat()">Tambah</button>
        </div>
    </div>

    <script>
        function searchTable() {
            let input = document.getElementById("search").value.toLowerCase();
            let rows = document.querySelectorAll("#equipmentTable tbody tr");
            
            rows.forEach(row => {
                let text = row.textContent.toLowerCase();
                row.style.display = text.includes(input) ? "" : "none";
            });
        }

        function tambahAlat() {
            let nama = document.getElementById("namaAlat").value;
            let jenis = document.getElementById("jenisAlat").value;
            let kondisi = document.getElementById("kondisiAlat").value;
            
            if (nama && jenis && kondisi) {
                let table = document.getElementById("equipmentTable").getElementsByTagName('tbody')[0];
                let newRow = table.insertRow();
                newRow.innerHTML = `<td>${nama}</td><td>${jenis}</td><td>${kondisi}</td>`;
                
                // Bersihkan input setelah tambah data
                document.getElementById("namaAlat").value = "";
                document.getElementById("jenisAlat").value = "";
                document.getElementById("kondisiAlat").value = "";
            } else {
                alert("Harap isi semua kolom!");
            }
        }
    </script>
</body>
</html>
