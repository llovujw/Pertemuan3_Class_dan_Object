# Pertemuan3_Class_dan_Object

## Profil
| Variable | Isi |
| -------- | --- |
| **Nama** | Intan Virginia Aulia Putri |
| **NIM** | 312310657 |
| **Kelas** | TI.23.A.6 |
| **Mata Kuliah** | Pemrograman Orientasi Objek |

### Latihan 1
- Apa yang harus didefinisikan sebelum membuat objek?
1. Class (Kelas): Ini adalah template atau cetakan dari objek. Misalnya, dalam diagram pertama, Anda punya kelas **AkunBank**, dan dalam diagram kedua, Anda punya kelas **Person**.
2. Atribut: Variabel yang menyimpan data untuk setiap objek yang dibuat. Sebagai contoh, untuk **AkunBank**, atribut-atributnya adalah `Saldo`, sedangkan untuk **Person**, atribut-atributnya adalah `Nama`, `Jenis Kelamin`, dan `Umur`.
3. Metode (Fungsi): Ini adalah perilaku yang dapat dilakukan oleh objek. Misalnya, pada **AkunBank**, metode yang didefinisikan adalah `SimpanUang()`, `CekSaldo()`, dan `AmbilUang()`. Pada **Person**, ada metode `TampilkanInfo()`.
- Buatlah gambar diagram class dan dua buah objek dari class Person bernama Antor dan Riko
![3](ss/dia1.png)
- Buatlah gambar diagram objek AkunBank dengan instance method simpanUang, ambilUang dan cekSaldo
![4](ss/dia2.png)

### Latihan 2
Buatlah kode program java untuk:
- Mendeklarasikan class Person, dengan atribut Nama, JenisKelamin, Umur
- Buatlah dua buah objek dari class Person bernama Anton dan Riko
``` Java
public class Person {
    // Atribut dari class Person
    String nama;
    String jenisKelamin;
    int umur;

    // Konstruktor untuk inisialisasi atribut
    public Person(String nama, String jenisKelamin, int umur) {
        this.nama = nama;
        this.jenisKelamin = jenisKelamin;
        this.umur = umur;
    }

    // Method untuk menampilkan informasi person
    public void tampilkanInfo() {
        System.out.println("Nama: " + nama);
        System.out.println("Jenis Kelamin: " + jenisKelamin);
        System.out.println("Umur: " + umur);
    }

    public static void main(String[] args) {
        // Membuat objek Anton dan Riko dari class Person
        Person anton = new Person("Anton", "Laki-laki", 25);
        Person riko = new Person("Riko", "Laki-laki", 30);

        // Menampilkan informasi Anton
        System.out.println("Informasi Anton:");
        anton.tampilkanInfo();

        // Menampilkan informasi Riko
        System.out.println("\nInformasi Riko:");
        riko.tampilkanInfo();
    }
}
```
#### Tampilan output
![6](ss/output3.png)

### Latihan 3
Buatlah kode java untuk:
- Mendeklarasikan class AkunBank dengan instance method simpanUang, ambilUang dan cekSaldo
- Buat objek AkunBank dan tetapkan nilai saldo awal Rp. 100000, kemudian panggil 3 method tersebut dan tampilkan proses berikut:
Selamat Datang di Bank ABC<br>
Saldo saat ini: Rp. 100000<br>
Simpan uang: Rp. 500000<br>
Saldo saat ini: Rp. 600000<br>
Ambil uang: Rp. 150000<br>
Saldo saat ini: Rp. 450000
``` Java
public class AkunBank {
    int saldo = 100000; // Saldo awal

    // Method untuk menyimpan uang
    public void SimpanUang(int depo) {
        if (depo > 0) {
            saldo += depo;
            System.out.println("Simpan uang: Rp. " + depo);
            System.out.println("Saldo saat ini: Rp. " + saldo);
        } else {
            System.out.println("Jumlah yang disimpan harus lebih dari 0.");
        }
    }

    // Method untuk mengecek saldo
    public void CekSaldo() {
        System.out.println("Saldo saat ini: Rp. " + saldo);
    }

    // Method untuk mengambil uang
    public void AmbilUang(int tarik) {
        if (tarik > 0 && tarik <= saldo) {
            saldo -= tarik;
            System.out.println("Ambil uang: Rp. " + tarik);
            System.out.println("Saldo saat ini: Rp. " + saldo);
        } else if (tarik > saldo) {
            System.out.println("Saldo tidak mencukupi untuk penarikan.");
        } else {
            System.out.println("Jumlah yang ditarik harus lebih dari 0.");
        }
    }

    public static void main(String[] args) {
        // Menampilkan pesan selamat datang
        System.out.println("Selamat Datang di Bank ABC");

        // Membuat objek AkunBank dengan saldo awal Rp. 100000
        AkunBank akun = new AkunBank();

        // Menampilkan saldo awal
        akun.CekSaldo();

        // Simpan uang Rp. 500000
        akun.SimpanUang(500000);

        // Ambil uang Rp. 150000
        akun.AmbilUang(150000);
    }
}
```
#### Tampilan output
![5](ss/output2.png)

