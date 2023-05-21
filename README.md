# NotHesap
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class NotHesaplama {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        List<Ders> dersListesi = new ArrayList<>();

        System.out.print("Kaç dersiniz var? ");
        int dersSayisi = input.nextInt();

        for (int i = 1; i <= dersSayisi; i++) {
            System.out.println("Ders " + i);
            System.out.print("Ders adı: ");
            String dersAdi = input.next();
            System.out.print("Vize notu: ");
            int vizeNotu = input.nextInt();
            System.out.print("Final notu: ");
            int finalNotu = input.nextInt();

            Ders ders = new Ders(dersAdi, vizeNotu, finalNotu);
            dersListesi.add(ders);
        }

        System.out.println("Ders Notları:");
        for (Ders ders : dersListesi) {
            System.out.println(ders.getDersAdi() + ": " + ders.getOrtalama());
        }
    }
}

class Ders {
    private String dersAdi;
    private int vizeNotu;
    private int finalNotu;

    public Ders(String dersAdi, int vizeNotu, int finalNotu) {
        this.dersAdi = dersAdi;
        this.vizeNotu = vizeNotu;
        this.finalNotu = finalNotu;
    }

    public String getDersAdi() {
        return dersAdi;
    }

    public int getVizeNotu() {
        return vizeNotu;
    }

    public int getFinalNotu() {
        return finalNotu;
    }

    public double getOrtalama() {
        return 0.4 * vizeNotu + 0.6 * finalNotu;
    }
}
