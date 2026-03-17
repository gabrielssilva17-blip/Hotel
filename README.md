import java.util.ArrayList;
import java.util.Scanner;

public class hotel {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        ArrayList <Integer> hotel = new ArrayList<>();
        ArrayList <Integer> camas = new ArrayList<>();
        ArrayList <String> hospedes = new ArrayList<>();

        int op = 1;

        while (op != 0) {
            System.out.println("1. Informe o número dos quartos: ");
            System.out.println("2. Reservar quarto:");
            System.out.println("3. Consultar quartos reservados:");
            System.out.println("4. Consultar reservas por hospedes:");
            System.out.println("0. Sair");
            op = sc.nextInt();
            
            switch (op) {
                case 1:
                    for (int i = 0; i <5; i++) {
                        System.out.println("Informe o número do quarto: " + (i + 1));
                        hotel.add(sc.nextInt());
                        
                        System.out.println("Digite o número de camas disponiveis: ");
                        camas.add(sc.nextInt());
                    }
                    break;
                    
                case 2:
                        System.err.println("Número dos quartos: " + hotel);
                        System.err.println("Número de camas disponiveis: " + camas);
                        System.out.println("Escolha o número do quarto: ");
                        int escolha = sc.nextInt();
                            
                        System.out.println("Digite o nome do hóspede: ");
                        hospedes.add(sc.next());

                        int escolha2 = camas.get(escolha);
                        escolha = hotel.get(escolha);
                        System.err.println("Olá, " + hospedes+ "! Você reservou o quarto " + escolha + " com " + escolha2 + " camas.");
                            
                        break;
                        
                case 3:
                    System.out.println("Digite o número do quarto para consultar: ");
                    int consulta = sc.nextInt();
                    
                    if(hotel.contains(consulta)){
                        System.out.println("O quarto " + consulta + " está reservado para " + hospedes);
                    }
                    break;
                    
                
                case 4:
                    System.out.println("Digite o nome do hóspede para consultar: ");
                    String consulta2 = sc.next();
                    
                    int indiceHospede = hospedes.indexOf(consulta2);
                    if(indiceHospede != -1 && indiceHospede < hotel.size()) {
                        int quartoReservado = hotel.get(indiceHospede);
                        System.out.println("O hóspede " + consulta2 + " tem uma reserva no quarto " + quartoReservado);
                    }
                }
        
            }
            sc.close();
}}
