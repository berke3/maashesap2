# maashesap2
java
package hafta4;

import java.util.Scanner;

import hafta4.jh.fonksiyonlar;

public class jh {
	public class fonksiyonlar {

	}

	public static void main(String[] args, Object arananAd) {
		Scanner scn = new Scanner(System.in);
		System.out.println("kişi sayısını girin");
		byte ks = scn.nextByte();
		String ad[] = new String[ks];
		String medenidurum[] = new String[ks];
		byte cs[] = new byte[ks];
		int maas[] = new int[ks];
		int elinegecen[] = new int[ks];
		byte menu;
		for (int i = 0; i < ks; i++) {
			System.out.print("ismi giriniz");
			ad[i] = scn.next();
			System.out.print("medeni durumu giriniz");
			medenidurum[i] = scn.next();
			System.out.print("cocuk sayısı giriniz");
			cs[i] = scn.nextByte();
			System.out.print("Maaşı giriniz");
			maas[i] = scn.nextInt();
			elinegecen[i] = maas[i];
			if (medenidurum[i].equalsIgnoreCase("e") || medenidurum[i].equalsIgnoreCase("E"))
				elinegecen[i] = +500;
			if (cs[i] > 3)
				cs[i] = 3;
			elinegecen[i] = elinegecen[i] + cs[i] * 250;
		}
		while (true) {
			fonksiyonlar2.Menu();
			menu = scn.nextByte();
			switch (menu) {
			case 1:
				fonksiyonlar2.Listeleme(ad, cs, medenidurum, maas, elinegecen);
				break;
			case 2:
				System.out.println("Aranacak ismi giriiz : ");
				String arananAd1 = scn.next();
				fonksiyonlar2.Arama(ad, cs, medenidurum, maas, elinegecen, arananAd1);

				break;
			case 3:
			
			int ortalama = scn.nextInt();
			fonksiyonlar2.ortalama(maas, elinegecen , ortalama);
			System.out.println("maaş ortalamanız : " + ortalama);
				break;
			case 4:
				break;
			case 5:
				break;
			case 6:
				break;
			default:
				System.out.println("Program bitti");
				System.exit(menu);

			}//fonksiyonda enb enk yap ve ortalama yap

		}
	}
}
--------------------------------------------
//fonksiyonlar
package hafta4;

public class fonksiyonlar2 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

	}

	public static void Menu() {
		// TODO Auto-generated method stub
		System.out.println("1-Listeleme\n2-isimarama\n3-ortalamalar\n4-enb\5-enk\n6-çıkış");
	}

	public static void Arama(String[] ad, byte[] cs, String[] medenidurum, int[] maas, int[] elinegecen,
			String arananAd) {
		// TODO Auto-generated method stub
		for (int i = 0; i < elinegecen.length; i++) {
			if (arananAd.equalsIgnoreCase(ad[i])) {
				System.out.println("ismi :" + ad[i]);
				if (medenidurum[i].equalsIgnoreCase("E"))
				System.out.println("Medeni durumu : Evli");
				else System.out.println("Medeni durum : Bekar");
				System.out.println("Çocuk sayısı : "+ cs[i]);
				System.out.println("Maşşı : "+maas[i]);
				System.out.println("Eline Geçen : "+elinegecen[i]);
			}
		}
		
	}

	public static void Listeleme(String[] ad, byte[] cs, String[] medenidurum, int[] maas, int[] elinegecen) {
		// TODO Auto-generated method stub
		for (int i = 0; i < elinegecen.length; i++) {
			System.out.println("ismi :" + ad[i]);
			if (medenidurum[i].equalsIgnoreCase("E"))
			System.out.println("Medeni durumu : Evli");
			else System.out.println("Medeni durum : Bekar");
			System.out.println("Çocuk sayısı : "+ cs[i]);
			System.out.println("Maşşı : "+maas[i]);
			System.out.println("Eline Geçen : "+elinegecen[i]);
			
		}
		
	}

	public static void ortalama(int[] maas, int[] elinegecen, int ortalama) {
		// TODO Auto-generated method stub
		
	}


}
