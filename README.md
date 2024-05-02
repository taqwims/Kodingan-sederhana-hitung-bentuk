# Kodingan-sederhana-hitung-bentuk
Kodingan sederhana untuk mengukur luas dan keliling dari suatu bentuk menggunakan bahasa java dengan menggunakan encapculation, interheritance, polimorphism dan interface atau abstrak

// Interface untuk bentuk geometri
interface BentukGeometri {
    double hitungLuas();
    double hitungKeliling();
}

// Kelas abstrak untuk bentuk geometri
abstract class Bentuk implements BentukGeometri {
    // Tidak perlu mengimplementasi kembali metode yang sudah ada di interface
}

// Kelas persegi
class Persegi extends Bentuk {
    private double sisi;

    public Persegi(double sisi) {
        this.sisi = sisi;
    }

    // Implementasi metode menghitung luas untuk persegi
    @Override
    public double hitungLuas() {
        return sisi * sisi;
    }

    // Implementasi metode menghitung keliling untuk persegi
    @Override
    public double hitungKeliling() {
        return 4 * sisi;
    }
}

// Kelas lingkaran
class Lingkaran extends Bentuk {
    private double radius;

    public Lingkaran(double radius) {
        this.radius = radius;
    }

    // Implementasi metode menghitung luas untuk lingkaran
    @Override
    public double hitungLuas() {
        return Math.PI * radius * radius;
    }

    // Implementasi metode menghitung keliling untuk lingkaran
    @Override
    public double hitungKeliling() {
        return 2 * Math.PI * radius;
    }
}

// Kelas segitiga
class Segitiga extends Bentuk {
    private double alas;
    private double tinggi;
    private double sisi1;
    private double sisi2;
    private double sisi3;

    public Segitiga(double alas, double tinggi, double sisi1, double sisi2, double sisi3) {
        this.alas = alas;
        this.tinggi = tinggi;
        this.sisi1 = sisi1;
        this.sisi2 = sisi2;
        this.sisi3 = sisi3;
    }

    // Implementasi metode menghitung luas untuk segitiga
    @Override
    public double hitungLuas() {
        return 0.5 * alas * tinggi;
    }

    // Implementasi metode menghitung keliling untuk segitiga
    @Override
    public double hitungKeliling() {
        return sisi1 + sisi2 + sisi3;
    }
}

// Kelas utama
public class  Coba {
    public static void main(String[] args) {
        Persegi persegi = new Persegi(5);
        Lingkaran lingkaran = new Lingkaran(3);
        Segitiga segitiga = new Segitiga(4, 5, 3, 4, 5);

        // Menggunakan polimorfisme untuk memanggil metode-metode dari bentuk-bentuk yang berbeda
        BentukGeometri[] bentukArr = {persegi, lingkaran, segitiga};
        for (BentukGeometri bentuk : bentukArr) {
            System.out.println("Luas: " + bentuk.hitungLuas());
            System.out.println("Keliling: " + bentuk.hitungKeliling());
            System.out.println();
        }
    }
}
