# El-caso-de-los-vinilos

package com.company.Main;

public class vinilos {
    public static void main(String[] args) {

        String vinilos[][] = new String[100][3];

        llenarMatriz(vinilos);

        agregarVinilo(vinilos, "Iron Maiden", "Iron Maiden", "1980");
        agregarVinilo(vinilos, "Iron Maiden", "Killers", "1981");
        agregarVinilo(vinilos, "Iron Maiden", "The number of the beast", "1982");
        agregarVinilo(vinilos, "AC-DC", "Back in black", "1980");
        agregarVinilo(vinilos, "AC-DC", "Highway to Hell", "1979");
        agregarVinilo(vinilos, "AC-DC", "Who mde who", "1986");
        agregarVinilo(vinilos, "Judas Priest", "British steel", "1980");
        agregarVinilo(vinilos, "Judas Priest", "Painkiller", "1990");
        agregarVinilo(vinilos, "Judas Priest", "Defenders of the faith", "1984");
        agregarVinilo(vinilos, "Kiss", "Destroyer", "1976");

        System.out.println("Espacio máximo colección: "+vinilos.length);

        mostrarTotal(vinilos);
        mostrarDisponibles(vinilos);

        String artista = "AC-DC";
        System.out.println("Buscar artista: "+artista);
        mostrarBusquedaArtista(vinilos, artista);

        buscarArtista(vinilos, artista);
        mostrarColeccion(vinilos);

    }

    public static void mostrarColeccion(String[][] vinilos) {
    }

    public static void buscarArtista(String[][] vinilos, String artista) {
    }

    public static void mostrarBusquedaArtista(String[][] vinilos, String artista) {
    }

    public static void mostrarDisponibles(String[][] vinilos) {
    }

    public static void mostrarTotal(String[][] vinilos) {
    }

    public static String[][] agregarVinilo(String coleccion[][], String alb, String art, String año) {
        int filavacia = 0;
        for (int i = 0; i < coleccion.length; i++) {
            String fila = coleccion[i][0];
            if (fila == "-") {
                filavacia = i;
                break;

            }
        }

        String[] datos = new String[3];
        datos[0] = alb;
        datos[1] = art;
        datos[2] = año;

        for (int j = 0; j < coleccion[filavacia].length; j++) {
            coleccion[filavacia][j] = datos[j];

        }

        return coleccion;

    }

    public static void mostrarMatriz(String[][] matriz) {
        int comp=0;
        System.out.println("\n Su coleccion seria la siguiente \n");
        for (int i = 0; i < matriz.length; i++) {
            for (int j = 0; j < matriz[i].length; j++) {
                if (matriz[i][j] != "-") {
                    System.out.print(matriz[i][j] + "\t ");
                    comp=0;
                }else{
                    comp=1;
                }


            }
            if (comp==0) {
                System.out.println();
            }

        }
    }

    public static void buscarColeccion(String[][] matriz, String busqueda) {
        int resp = 0;
        System.out.println("Buscar en la coleccion: "+ busqueda);
        for (int i = 0; i < matriz.length; i++) {
            for (int j = 0; j < matriz[i].length; j++) {
                if (matriz[i][j] == busqueda) {
                    System.out.println("Su busqueda si esta en la coleccion");

                    resp = 1;
                    System.out.println();
                    break;
                }

            }
            if (resp==1) {
                break;

            }
        }
        if (resp == 0) {
            System.out.println("Su busqueda no esta en la coleccion");
            System.out.println();

        }

    }

    public static void verificador(String[][] coleccion) {
        int filavacia = 0;

        for (int i = 0; i < coleccion.length; i++) {
            String fila = coleccion[i][0];
            if (fila == "-") {
                filavacia += 1;


            }
        }
        int filaocupada = coleccion.length-filavacia;
        System.out.println("Existen "+filaocupada+" vinilos en la coleccion");
        System.out.println("Existen "+filavacia+" espacios para nuevos vinilos en la coleccion");
        System.out.println();
    }
    public static String[][] llenarMatriz(String[][] matriz) {
        for (int i = 0; i < matriz.length; i++) {
            for (int j = 0; j < matriz[i].length; j++) {
                matriz[i][j] = "-";

            }
        }
        return matriz;
    }

}
