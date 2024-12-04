# Fitri Ramadhani
# 312410085
# TI.24.A.1

# Daftar Nilai Mahasiswa

# Deskripsi Program
Program Python ini adalah implementasi sederhana dari konsep Object-Oriented Programming (OOP) untuk mengelola data nilai mahasiswa. Program mencakup fitur untuk menambah, menampilkan, mengubah, dan menghapus data mahasiswa.

Fitur Program:
1. Menambah Data
Menambahkan nama dan nilai mahasiswa ke dalam daftar.
2. Menampilkan Data
Menampilkan semua data mahasiswa yang telah dimasukkan.
3. Menghapus Data
Menghapus data mahasiswa berdasarkan nama.
4. Mengubah Data
Mengubah nilai mahasiswa berdasarkan nama.

# Flowchart Program

# Kode Program
```python
vclass DaftarNilaiMahasiswa:
    def __init__(self):
        self.data = {}

    def tambah(self, nama, nilai):
        self.data[nama] = nilai
        print(f"Data {nama} dengan nilai {nilai} berhasil ditambahkan.")

    def tampilkan(self):
        if not self.data:
            print("Belum ada data yang ditambahkan.")
        else:
            print("Daftar Nilai Mahasiswa:")
            for nama, nilai in self.data.items():
                print(f"{nama}: {nilai}")

    def hapus(self, nama):
        if nama in self.data:
            del self.data[nama]
            print(f"Data {nama} berhasil dihapus.")
        else:
            print(f"Data dengan nama {nama} tidak ditemukan.")

    def ubah(self, nama, nilai_baru):
        if nama in self.data:
            self.data[nama] = nilai_baru
            print(f"Data {nama} berhasil diubah menjadi {nilai_baru}.")
        else:
            print(f"Data dengan nama {nama} tidak ditemukan.")


# Contoh penggunaan program
if __name__ == "__main__":
    daftar_nilai = DaftarNilaiMahasiswa()
    
    while True:
        print("\nMenu:")
        print("1. Tambah data")
        print("2. Tampilkan data")
        print("3. Hapus data")
        print("4. Ubah data")
        print("5. Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan == "1":
            nama = input("Masukkan nama: ")
            try:
                nilai = float(input("Masukkan nilai: "))  # Pastikan nilai adalah angka
                daftar_nilai.tambah(nama, nilai)
            except ValueError:
                print("Nilai harus berupa angka.")
        elif pilihan == "2":
            daftar_nilai.tampilkan()
        elif pilihan == "3":
            nama = input("Masukkan nama yang akan dihapus: ")
            daftar_nilai.hapus(nama)
        elif pilihan == "4":
            nama = input("Masukkan nama yang akan diubah: ")
            try:
                nilai_baru = float(input("Masukkan nilai baru: "))  # Pastikan nilai baru adalah angka
                daftar_nilai.ubah(nama, nilai_baru)
            except ValueError:
                print("Nilai baru harus berupa angka.")
        elif pilihan == "5":
            print("Program selesai.")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")
```

# Run Program
```
PS C:\Users\AXIOO\Documents\KULIAH\matkul b.pemrograman\praktikum 8> python -u "c:\Users\AXIOO\Documents\KULIAH\matkul b.pemrograman\praktikum 8\lab8.py"

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan nama: fitri
Masukkan nilai: 99
Data fitri dengan nilai 99.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan nama: ramadhani
Masukkan nilai: 89
Data ramadhani dengan nilai 89.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan nama: bongg
Masukkan nilai: 80
Data bongg dengan nilai 80.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan nama: kepin
Masukkan nilai: 100
Data kepin dengan nilai 100.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 2
Daftar Nilai Mahasiswa:
fitri: 99.0
ramadhani: 89.0
bongg: 80.0
kepin: 100.0

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 4
Masukkan nama yang akan diubah: bongg
Masukkan nilai baru: 90
Data bongg berhasil diubah menjadi 90.0.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 5
Program selesai.
PS C:\Users\AXIOO\Documents\KULIAH\matkul b.pemrograman\praktikum 8>
```

# Class Diagram
```
+-------------------------+
|  DaftarNilaiMahasiswa   |
+-------------------------+
| - data: dict            |
+-------------------------+
| + __init__()            |
| + tambah(nama, nilai)   |
| + tampilkan()           |
| + hapus(nama)           |
| + ubah(nama, nilai_baru)|
+-------------------------+
```

# Cara Kerja Program
Ketika program dijalankan:
Pengguna melihat menu utama.
Memilih salah satu opsi dengan memasukkan angka 1-5.
Program menjalankan metode yang sesuai dengan pilihan pengguna.
Program kembali ke menu utama setelah setiap aksi hingga pengguna memilih opsi keluar.
