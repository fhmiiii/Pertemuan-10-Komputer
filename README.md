# Pertemuan-10-Komputer

Nama : Fahmi Ferdiansyah
Nim  : 352310865
Kelas: IE.23.C12


Program Pengolah Data Nilai Akhir Mahasiswa

 Deskripsi Program
 Program ini adalah program yang dibuat mengguanakan Dictionary untuk mengolah data nilai akhir mahasiswa. Program ini
 dibuat untuk mengelola data mahasiswa termasuk menampilkan, menambah, mengubah, menghapus, dan mencari data
 nilai mereka. Program ini dibuat dengan menggunakan NIM sebagai Key dan data mahasiswa (Nama, Nilai Tugas, Nilai
 UTS, Nilai UAS) sebagai Value. Program ini menggunakan perhitungan nilai akhir dengan bobot sebesar Nilai Tugas 30%
 lalu Nilai UTS 35% dan Nilai UAS 35%

![Screenshot 2024-11-29 235703](https://github.com/user-attachments/assets/f18605c6-3ae2-4946-92a0-65b5a6a67214)



Kode Program :

data_mahasiswa = {}

def hitung_nilai_akhir(tugas, uts, uas):
    return (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)

def tampilkan_data():
    if not data_mahasiswa:
        print("\nDaftar Nilai")
        print("="*57)
        print("| NO |  NIM  |   NAMA   | TUGAS |  UTS  |  UAS  | AKHIR |")
        print("="*57)
        print("|                    TIDAK ADA DATA                     |")
        print("="*57)
    else:
        print("\nDaftar Nilai")
        print("="*57)
        print("| NO |  NIM  |   NAMA   | TUGAS |  UTS  |  UAS  | AKHIR |")
        print("="*57)
        for i, (nim, data) in enumerate(data_mahasiswa.items(), start=1):
            print(f"| {i:<2} | {nim:<5} | {data['nama']:<8} | {data['tugas']:<5} | {data['uts']:<5} | {data['uas']:<5} | {data['akhir']:<0.2f} |")
        print("="*57)

def tambah_data():
    nim = input("NIM: ")
    nama = input("Nama: ")
    tugas = float(input("Nilai Tugas: "))
    uts = float(input("Nilai UTS: "))
    uas = float(input("Nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
    data_mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": nilai_akhir}
    print("Data berhasil ditambahkan!")

def ubah_data():
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    if nim in data_mahasiswa:
        print("Masukkan data baru:")
        nama = input("Nama: ")
        tugas = float(input("Nilai Tugas: "))
        uts = float(input("Nilai UTS: "))
        uas = float(input("Nilai UAS: "))
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        data_mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": nilai_akhir}
        print("Data berhasil diubah!")
    else:
        print("Data tidak ditemukan!")

def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    if nim in data_mahasiswa:
        del data_mahasiswa[nim]
        print("Data berhasil dihapus!")
    else:
        print("Data tidak ditemukan!")

def cari_data():
    nim = input("Masukkan NIM yang dicari: ")
    if nim in data_mahasiswa:
        data = data_mahasiswa[nim]
        print("\nData Mahasiswa")
        print(f"NIM: {nim}")
        print(f"Nama: {data['nama']}")
        print(f"Nilai Tugas: {data['tugas']}")
        print(f"Nilai UTS: {data['uts']}")
        print(f"Nilai UAS: {data['uas']}")
        print(f"Nilai Akhir: {data['akhir']:.2f}")
    else:
        print("Data tidak ditemukan!")

while True:
    print("\nProgram Input Nilai")
    print("===================")
    print("[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]")
    pilihan = input("Pilih menu: ").lower()

    if pilihan == "l":
        tampilkan_data()
    elif pilihan == "t":
        tambah_data()
    elif pilihan == "u":
        ubah_data()
    elif pilihan == "h":
        hapus_data()
    elif pilihan == "c":
        cari_data()
    elif pilihan == "k":
        print("Program selesai. Terima kasih!")
        break
    else:
        print("Pilihan tidak valid! Silakan coba lagi.")



Menu Program

 Program ini mempunyai beberapa menu yang akan ditampilkan di awal ketika dijalankan, diantaranya
 L: Melihat daftar nilai mahasiswa.
 T: Menambahkan data mahasiswa baru.
 U: Mengubah data mahasiswa berdasarkan NIM.
 H: Menghapus data mahasiswa berdasarkan NIM.
 C: Mencari data mahasiswa berdasarkan NIM.
 K: Keluar dari program.
 
 Fungsi Program
 1. Menghitung Nilai
  Program ini menghitung Nilai Akhir berdasarkan formula yang ada.
  
    ![Screenshot 2024-11-29 213240](https://github.com/user-attachments/assets/003811e4-e93a-40f4-925c-bead9da23540)

 2. Menampilkan Data
 Program ini menampilkan data mahasiswa dalam bentuk tabel. Apabila data di dalam program kosong maka tampilan tabel
 tersebut juga kosong.

![Screenshot 2024-11-29 213529](https://github.com/user-attachments/assets/fb4a23a1-142e-49b0-9c0b-a5d18422a2e4)

 3. Menambahkan Data
 Program ini akan meminta untuk memasukan data mahasiswa (Nama, Nilai Tugas, Nilai UTS, Nilai UAS) untuk selanjutnya
 akan dihitung menjadi data nilai akhir. Apabila program ini berhasil maka program akan menampilkan "Data berhasil
 ditambahkan!" dan program akan kembali ke menu awal.

![Screenshot 2024-11-29 235158](https://github.com/user-attachments/assets/633fc587-3e15-4e38-9be6-149b9641ce8c)


4. Mengubah Data
 Program ini akan meminta untuk memasukan NIM mahasiswa sebagai Key. Selanjutnya program akan meminta untuk
 memasukan data (Nama, Nilai Tugas, Nilai UTS, Nilai UAS) untuk kemudian akan diganti menjadi data yang baru. Apabila
 program ini berhasil maka program akan menampilkan "Data berhasil diubah!", namun apabila NIM yang dimasukan salah
 maka tambilan program "Data tidak ditemukan!".

![Screenshot 2024-11-29 235327](https://github.com/user-attachments/assets/0d529fa2-e875-4f1a-af7d-e497c7eddf6b)


 5. Menghapus Data
 Program ini akan meminta untuk memasukan NIM mahasiswa sebagai Key. Selanjutnya apabila program ini berhasil maka
 program akan menampilkan "Data berhasil dihapus!", namun apabila NIM yang dimasukan salah maka tambilan program
 "Data tidak ditemukan!".

![Screenshot 2024-11-29 214201](https://github.com/user-attachments/assets/247c5040-1674-4ee0-9883-3baf1b74232d)

 6. Mencari Data
 Program ini akan meminta untuk memasukan NIM mahasiswa sebagai Key. Selanjutnya apabila program ini berhasil maka
 program akan menampilkan data yang dicari, namun apabila NIM yang dimasukan salah maka tampilan program "Data tidak
 ditemukan!".

![Screenshot 2024-11-29 235457](https://github.com/user-attachments/assets/ec2512bc-fde5-4c24-af8c-cba44e7e303c)


 Alur Penggunaan Program

 ![Screenshot 2024-11-29 214609](https://github.com/user-attachments/assets/993c21e3-2369-456b-9070-ec9d7f3d0f33)

  1. Menjalankan Program
 Program akan menampilkan menu ketika dijalankan.
 Ketika menu yang dipilih salah maka akan menampilkan "Pilihan tidak valid! Silakan coba lagi."

 2. Memilih Menu
 Ketik huruf sesuai pilihan menu:
 L: Melihat daftar nilai mahasiswa.
 T: Menambahkan data mahasiswa baru.
 U: Mengubah data mahasiswa berdasarkan NIM.
 H: Menghapus data mahasiswa berdasarkan NIM.
 C: Mencari data mahasiswa berdasarkan NIM.
 K: Keluar dari program.

 3. Menambahkan Data
 Pilih menu T (Tambah).
 Masukkan informasi berikut:
 NIM: Nomor Induk Mahasiswa.
 Nama: Nama mahasiswa.
 Nilai Tugas, UTS, UAS: Nilai numerik.
 Program akan otomatis menghitung nilai akhir dan menyimpan data.

 4. Melihat Data
 Pilih menu L (Lihat).
 Data akan ditampilkan dalam tabel, termasuk NIM, nama, nilai tugas, UTS, UAS, dan nilai akhir.

 5. Mengubah Data
 Pilih menu U (Ubah).
 Masukkan NIM mahasiswa yang ingin diubah.
 Jika ditemukan, masukkan data baru (nama, nilai tugas, UTS, UAS).
 Data akan diperbarui.

 6. Menghapus Data
 Pilih menu H (Hapus).
 Masukkan NIM mahasiswa yang ingin dihapus.
 Jika ditemukan, data akan dihapus dari daftar.

 7. Mencari Data
 Pilih menu C (Cari).
 Masukkan NIM mahasiswa yang dicari.
 Jika ditemukan, data akan ditampilkan.

 8. Keluar dari Program
 Pilih menu K (Keluar).
 Program akan berhenti dengan pesan terima kasih.
 Kesimpulan

 Program ini sangat cocok untuk mengelola data sederhana, seperti nilai akhir semester, dengan fitur CRUD (Create, Read,
 Update, Delete). Dengan mengikuti alur di atas, pengguna dapat dengan mudah mengelola data mahasiswa.
