# Lab-7
Student

package lab_2;

import java.util.ArrayList;
import java.util.Scanner;
import java.util.Vector;

public class Lab5 {

  
    static class Ogrenci {
        String ad;
        double not;

        public Ogrenci(String ad, double not) {
            this.ad = ad;
            this.not = not;
        }
    }
    

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        
        ArrayList<Ogrenci> ogrenciler = new ArrayList<>();
        
        
        while (true) {
            System.out.print("Öğrencinin adını girin (bitirmek için 'tamam' yazın): ");
            String ad = scanner.nextLine();
            if (ad.equalsIgnoreCase("tamam")) break;

            System.out.print("Öğrencinin notunu girin: ");
            double not = scanner.nextDouble();
            scanner.nextLine(); 
            ogrenciler.add(new Ogrenci(ad, not));
        }

        
        System.out.println("\nÖğrenci Listesi:");
        for (Ogrenci ogrenci : ogrenciler) {
            System.out.println("Ad: " + ogrenci.ad + ", Not: " + ogrenci.not);
        }

        
        double toplam = 0;
        for (Ogrenci ogrenci : ogrenciler) {
            toplam += ogrenci.not;
        }
        double ortalama = toplam / ogrenciler.size();
        System.out.println("\nSınıf Ortalaması: " + ortalama);

        
        System.out.println("Ortalamanın üstünde olan öğrenciler:");
        for (Ogrenci ogrenci : ogrenciler) {
            if (ogrenci.not > ortalama) {
                System.out.println("Ad: " + ogrenci.ad + ", Not: " + ogrenci.not);
            }
        }

       
        
        
        
        Vector<Integer> girilenSayilar = new Vector<>();
        Vector<Integer> tekrarsizSayilar = new Vector<>();
        
        System.out.println("\nSayıları girin (bitirmek için -1 girin):");
        while (true) {
            int sayi = scanner.nextInt();
            if (sayi == -1) break;

         
            if (girilenSayilar.contains(sayi)) {
                tekrarsizSayilar.remove((Integer) sayi);
            } else {
                girilenSayilar.add(sayi);
                tekrarsizSayilar.add(sayi);
            }
        }

       
        System.out.println("Girilen tekrarsız sayılar:");
        for (int sayi : tekrarsizSayilar) {
            System.out.print(sayi + " ");
        }
        System.out.println();

        scanner.close();
    }
}

