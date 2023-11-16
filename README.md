# CaixaEletronico
Exemplo de caixa eletrônico 
package CaixaEletronico;

import java.util.Scanner;

public class CaixaEletronico {
    private static double saldo = 1000; 

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        boolean continuar = true;

        while (continuar) {
            exibirMenu();

            int opcao = sc.nextInt();

            switch (opcao) {
                case 1:
                    consultarSaldo();
                    break;
                case 2:
                    realizarSaque();
                    break;
                case 3:
                    realizarDeposito();
                    break;
                case 4:
                    System.out.println("Obrigado por usar o Caixa Eletrônico. Até a próxima!");
                    continuar = false;
                    break;
                default:
                    System.out.println("Opção inválida. Tente novamente.");
                    break;
            }
        }

        sc.close();
    }

    private static void exibirMenu() {
        System.out.println("\nCaixa Eletrônico \n da Unipaulistana");
        System.out.println("1 - Consultar Saldo");
        System.out.println("2 - Saque");
        System.out.println("3 - Depósito");
        System.out.println("4 - Sair");
        System.out.println("Digite a opção desejada:");
    }

    private static void consultarSaldo() {
        System.out.println("Seu saldo atual é: R$" + saldo);
    }

    private static void realizarSaque() {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite o valor que deseja sacar: ");
        double valorSaque = sc.nextDouble();

        if (valorSaque > 0 && valorSaque <= saldo) {
            saldo = valorSaque;
            System.out.println("Saque realizado com sucesso. Novo saldo: R$" + saldo);
        } else {
            System.out.println("Valor inválido ou saldo insuficiente.");
            sc.close();
        }
    }

    private static void realizarDeposito() {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite o valor que deseja depositar: ");
        double valorDeposito = sc.nextDouble();

        if (valorDeposito > 0) {
            saldo += valorDeposito;
            System.out.println("Depósito realizado com sucesso. Novo saldo: R$" + saldo);
        } else {
            System.out.println("Valor inválido para depósito.");
            sc.close();
        }
    } 
    
