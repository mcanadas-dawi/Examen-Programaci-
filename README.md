# Examen-Programació-
1. 
public static void decimalBinari(int numero, boolean invertido) {
  if (numero == 0) {
    System.out.println("0");
    return;
  }

  if (invertido) {
    decimalBinari(numero / 2, false);
    System.out.println(numero % 2);
  } else {
    System.out.println(numero % 2);
    decimalBinari(numero / 2, true);
  }
}
}


2.
public static void binariDecimal(long binario) {
  long decimal = 0;
  int potencia = 0;

  while (binario > 0) {
    decimal += binario % 10 * Math.pow(2, potencia);
    binario /= 10;
    potencia++;
  }

  System.out.println(decimal);
}




3.

public static boolean esParell(int numero) {
  return numero % 2 == 0;
}



4.

public static void primersNombresParells(int n) {
  int i = 0;
  while (i <= n) {
    if (esParell(i)) {
      System.out.println(i);
    }
    i++;
  }
}

5.

public static int menu() {
  System.out.println("Tria una de les següents opcions:");
  System.out.println("1. Decimal a binari");
  System.out.println("2. Binari a decimal");
  System.out.println("3. Es parell?");
  System.out.println("4. Calcular parells de 0 fins a n");
  System.out.println("0. Sortir");

  int opcio = -1;

  while (opcio < 0 || opcio > 4) {
    System.out.print("Introdueix una opció (0-4): ");
    opcio = Integer.parseInt(System.console().readLine());
  }

  return opcio;
}


6.

public static void main(String[] args) {
    int opcio;

    do {
      opcio = menu();

      switch (opcio) {
        case 1:
          
          long binari;
          System.out.print("Introdueix un nombre decimal: ");
          binari = Long.parseLong(System.console().readLine());
          binariDecimal(binari);
          break;
        case 2:
          
          String binariString;
          System.out.print("Introdueix un nombre binari: ");
          binariString = System.console().readLine();
          binariDecimal(Long.parseLong(binariString, 2));
          break;
        case 3:
        
          int numero;
          System.out.print("Introdueix un nombre: ");
          numero = Integer.parseInt(System.console().readLine());
          System.out.println(esParell(numero) ? "És parell" : "No és parell");
          break;
        case 4:
          
          int n;
          System.out.print("Introdueix un nombre: ");
          n = Integer.parseInt(System.console().readLine());
          primersNombresParells(n);
          break;
        case 0:
        
          break;
        default:
          
          System.out.println("Opció no vàlida");
          break;
      }
    } while (opcio != 0);
  }


7.

public static double volumCilindre(double radi, double longitud) {
    return Math.PI * radi * radi * longitud;
  }

  public static double volumPrismaRectangular(double a, double b, double c) {
    return a * b * c;
  }
}


8.

public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    
    System.out.println("¿El transporte es de líquidos o sólidos?");
    System.out.println("1. Líquidos");
    System.out.println("2. Sólidos");
    int tipusTransport = sc.nextInt();

    
    while (tipusTransport < 1 || tipusTransport > 2) {
      System.out.println("Opción no válida");
      System.out.println("¿El transporte es de líquidos o sólidos?");
      System.out.println("1. Líquidos");
      System.out.println("2. Sólidos");
      tipusTransport = sc.nextInt();
    }

    
    System.out.println("Introduce el volumen a transportar (en metros cúbicos): ");
    double volum = sc.nextDouble();

    
    double capacitatCamio;
    if (tipusTransport == 1) {
      capacitatCamio = 1000; en metros cúbicos
    } else {
      capacitatCamio = 15; metros cúbicos
    }
    int numViatges = (int) Math.ceil(volum / capacitatCamio);

   
    System.out.println("El número de viajes necesarios es " + numViatges);
  }
}
