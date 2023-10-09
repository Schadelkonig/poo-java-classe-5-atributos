# Programação Orientada a Objetos
### (Exemplo realizado no Apache NetBeans IDE 18)

Crie uma classe com cinco atributos para a criação de objetos do tipo Computador. A classe deve possuir dois métodos construtores, um sem parâmetros (construtor default) e outro com os cinco parâmetros relacionados aos atributos da classe Computador. Além disso, a classe deve conter os métodos de acesso (setters e getters) para cada atributo e um método de exibição de todos os atributos denominado imprimir.
Crie uma outra aplicação (Classe) que instancie quatro objetos do tipo Computador, preencha os atributos com dados solicitados ao usuário e ao final exiba todos os atributos dos quatro objetos criados invocando o método imprimir. Para criar os quatro objetos, com a metade utilize o construtor default, e com a outra metade utilize o construtor que recebe todos os atributos.
Desenvolva a classe e a aplicação separadamente.


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
