# poo-java-classe-5-atributos

##(Realizado no Apache NetBeans IDE 18)

## Classe main:

´´´
package project1;

import java.util.Scanner;

public class Project1 {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        Computador[] computadores = new Computador[4];

        for (int i = 0; i < 2; i++) {
            computadores[i] = new Computador(); // Usando construtor default
        }

        for (int i = 2; i < 4; i++) {
            System.out.println("Digite a marca do computador " + (i - 1) + ": ");
            String marca = scanner.nextLine();

            System.out.println("Digite o modelo do computador " + (i - 1) + ": ");
            String modelo = scanner.nextLine();

            System.out.println("Digite o ano do computador " + (i - 1) + ": ");
            int ano = Integer.parseInt(scanner.nextLine());

            System.out.println("Digite o preço do computador " + (i - 1) + ": ");
            double preco = Double.parseDouble(scanner.nextLine());

            System.out.println("O computador " + (i - 1) + " está ligado? (true/false): ");
            boolean ligado = Boolean.parseBoolean(scanner.nextLine());

            computadores[i] = new Computador(marca, modelo, ano, preco, ligado);
        }

        for (Computador computador : computadores) {
            computador.imprimir();
            System.out.println();
        }
    }
}

´´´

## Classe Computador:

´´´
package project1;
public class Computador {
    private String marca;
    private String modelo;
    private int ano;
    private double preco;
    private boolean ligado;

    public Computador() {
    }

    public Computador(String marca, String modelo, int ano, double preco, boolean ligado) {
        this.marca = marca;
        this.modelo = modelo;
        this.ano = ano;
        this.preco = preco;
        this.ligado = ligado;
    }

    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public int getAno() {
        return ano;
    }

    public void setAno(int ano) {
        this.ano = ano;
    }

    public double getPreco() {
        return preco;
    }

    public void setPreco(double preco) {
        this.preco = preco;
    }

    public boolean isLigado() {
        return ligado;
    }

    public void setLigado(boolean ligado) {
        this.ligado = ligado;
    }

    public void imprimir() {
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Ano: " + ano);
        System.out.println("Preço: " + preco);
        System.out.println("Ligado: " + ligado);
    }
}

´´´
