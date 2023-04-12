     import java.util.Scanner;

      public class Hesap {

       public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("Mesafeyi km türünden giriniz : ");
        int mesafe = input.nextInt();

        System.out.print("Yaşınızı giriniz : ");
        int yas = input.nextInt();

        System.out.print("Yolculuk tipini giriniz (1 => Tek Yön , 2 => Gidiş Dönüş ): ");
        int yolculukTipi = input.nextInt();

        if (mesafe <= 0 || yas <= 0 || (yolculukTipi != 1 && yolculukTipi != 2)) {
            System.out.println("Hatalı Veri Girdiniz !");
        } else {
            double normalTutar = mesafe * 0.10;

            if (yas < 12) {
                normalTutar *= 0.50;
            } else if (yas <= 24) {
                normalTutar *= 0.90;
            } else if (yas >= 65) {
                normalTutar *= 0.70;
            }

            if (yolculukTipi == 2) {
                normalTutar *= 0.80;
            }

            double toplamTutar = yolculukTipi == 2 ? (normalTutar * 2) : normalTutar;
            System.out.printf("Toplam Tutar = %.1f TL", toplamTutar);
        }

        input.close();
    }

}
