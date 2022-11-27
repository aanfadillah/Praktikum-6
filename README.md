## Nama  : Aan Fadillah Putra  
## NIM   : 312210327
## Kelas : TI.22.A3
# PERTEMUAN 10

# Latihan 1

![soal3](https://user-images.githubusercontent.com/115542704/203886224-ca19720b-7b3b-4008-9676-a86524bc0ab8.png)

- Pertama buat daftar kontak awal menggunakan dictionary, dengan format nama (key) dan nomor (value)
- Variable p disini di deklarasikan sebagai perintah print agar lebih mudah
- Variable b digunakan untuk menyimpan dictionary

```python
p=print
```

```python

b={'ari':'085267888','dina':'087677776'}
p('Kontak awal')
p('==============================')
p('#    nama    |   nomor telepon')
p('==============================')
p('#    ari     |   085267888','\n#    dina    |   087677776')
```
- Untuk menampilkan kontak gunakan format berikut

```python
p(b['ari'])
```

<img width="198" alt="screenshot9" src="https://user-images.githubusercontent.com/115542704/203890552-e24cbf97-fa3b-4bcb-9571-5924bc3df05f.png">

- Untuk menambahkan kontak baru (element dictionary) gunakan format berikut

```python
b['riko']='087654544'
```

<img width="201" alt="screenshot8" src="https://user-images.githubusercontent.com/115542704/203901153-338174d1-1d06-4ae3-bef8-7f70617f275e.png">

- Untuk mengubah nomor (value) gunakan format berikut

```python
b['dina']='088999776'
```

<img width="194" alt="Cuplikan layar_20221125_090601" src="https://user-images.githubusercontent.com/115542704/203902338-432349a6-f86c-4059-bbe3-55fc5f007c25.png">

- Untuk menampilkan semua nama (key) gunakan format berikut

```python
p(b.keys())
```

- Untuk menampilkan semua nomor (value) gunakan format berikut

```python
p(b.values())
```

- Untuk menampilkan semua daftar nama (key) dan nomor (value) gunakan format berikut

```python
p(b)
```

- Untuk menghapus kontak (element dictionary) gunakan format berikut

```python
del b['dina']
```

<img width="399" alt="screenshot10" src="https://user-images.githubusercontent.com/115542704/203908691-a072e8c8-4c6a-4d85-8b6d-a991f86cc5be.png">

# Tugas Praktikum

## Soal

![soal2](https://user-images.githubusercontent.com/115542704/203814727-a04667fb-b65b-4f53-b7b4-cd89b118bdbb.png)

# flowchart

![flowchart (1)](https://user-images.githubusercontent.com/115542704/203925218-1e0c8771-2b49-44bf-9780-a6e9ff464867.png)

# jawab

- Pertama buat dictionary kosong

```python
dataMhs = {}
```
- Penggunaan while True

    while True berfungsi untuk mendeteksi jika format yang diinputkan bukan berupa type maka akan muncul error
    
- Saya membuat looping agar program terus berjalan

```python
    while True:
    c = input("\n(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar: ")
```

- Penggunaan if c.lower()

    if c.lower() fungsinya apabila user menginputkan denga huruf besar, maka otomatis akan menjadi huruf kecil sehingga kondisi yang digunakan tercapai

- Lalu saya membuat format if untuk memasukkan pilihan, sebagai contoh apabila memilih (t) akan menambah data
```python
    if (c.lower() == 't'):
        print('\nTambah Data Mahasiswa Baru')
        nama= input("Masukkan Nama\t\t: ")
        nim= input("Masukkan NIM\t\t: ")
        nilaiTugas= int(input("Masukkan Nilai Tugas\t: "))
        nilaiUts= int(input("Masukkan Nilai UTS\t: "))
        nilaiUas= int(input("Masukkan Nilai UAS\t: "))
        nilaiAkhir= (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)
        dataMhs[nama]= nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir
        print("\nData Berhasil Ditambahkan!")
```

- Saya juga melakukan percabangan if (elif) untuk melaksanakan pilihan yang lain
- Berikut program untuk mengubah data

```python
    elif (c.lower() == 'u'):
        print('\nMengedit Data Mahasiswa')
        nama = input("Masukkan Nama: ")
        if nama in dataMhs.keys():
            nim= input("Masukkan NIM Baru\t: ")
            nilaiTugas= int(input("Masukkan Nilai Tugas\t: "))
            nilaiUts= int(input("Masukkan Nilai UTS\t: "))
            nilaiUas= int(input("Masukkan Nilai UAS\t: "))
            nilaiAkhir= (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)
            dataMhs[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir
            print("\nData Berhasil Di Update!")
        else:
            print("Data tidak ditemukan!")
```            

- Berikut program untuk mencari data
            
```python
    elif (c.lower() == 'c'):
        print('\nCari Data Mahasiswa')
        nama = input("Masukan Nama:  ")
        if nama in dataMhs.keys():
            print("\n                   DAFTAR NILAI MAHASISWA                   ")
            print("==============================================================")
            print("|     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==============================================================")
            print("| {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(nama, nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir))
            print("==============================================================")
        else:
            print("Datanya {0} Tidak Ada ".format(nama))
```

- Berikut program untuk menghapus data

```python
    elif (c.lower() == 'h'):
        nama = input("Masukkan Nama:  ")
        if nama in dataMhs.keys():
            del dataMhs[nama]
            print("Data Telah dihapus!")
        else:
            print("Data Mahasiswa Tidak Ada".format(nama))
```

- Berikut program untuk melihat data

```python
    elif (c.lower() == 'l'):
        if dataMhs.items():
            print("\n                      DAFTAR NILAI MAHASISWA                    ")
            print("==================================================================")
            print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==================================================================")
            i = 0
            for x in dataMhs.items():
                i += 1
                print("| {6:2} | {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(x[0], x[1][0], x[1][1], x[1][2], x[1][3], x[1][4], i))
            print("==================================================================")
        else:
            print("\n                      DAFTAR NILAI MAHASISWA                    ")
            print("==================================================================")
            print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==================================================================")
            print("|                          TIDAK ADA DATA!                       |")
            print("==================================================================")
```

- Berikut program untuk keluar dari program

```python
    elif (c.lower() == 'k'):
        print('\n')
        print(21*'=')
        print("Nama\t: Aan Fadillah Putra\nKelas\t: TI.22.A3\nNIM\t: 312210327")
        print(21*'=')
        break
```

- Dan saya juga menggunakan else yang digunakan apabila salah memasukkan pilihan inputan
```python
    else:
        print("Pilih menu yang tersedia: ")
```

# output 
ini adalah output apabila memilih tambah (t)

![t](https://user-images.githubusercontent.com/115763475/204143810-20f478bb-5794-4228-86b4-66cda69b9e63.png)


ini adalah output apabila memilih  diubah (u)

![U](https://user-images.githubusercontent.com/115763475/204143923-b40ad59d-124d-4c69-ad44-f0e4cb54148a.png)


ini adalah output apabila memilih  mencari (c)

![C](https://user-images.githubusercontent.com/115763475/204143966-96c665eb-9564-4ac1-a525-5218f59b5a12.png)


ini adalah output apabila memilih lihat (l)

![outputL](https://user-images.githubusercontent.com/115763475/204143983-49962ab3-0d2d-47da-bbc4-bbff4b16c641.png)

ini adalah output apabila memilih hapus (h) 

 ![outputH](https://user-images.githubusercontent.com/115763475/204143998-6de98587-2a4c-4f2c-b711-f37ceaa5afa1.png)

ini adalah output apabila memilih keluar (k)

![IMG-20221127-WA0036](https://user-images.githubusercontent.com/115763475/204144056-bc9b7717-bb6d-4c15-b6f3-4d8bbabc550f.jpg)


## SEKIAN TERIMAKASIH




