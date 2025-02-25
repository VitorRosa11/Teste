

public class Carro {
    private String marca;
    private String modelo;
    private String cor;
    private boolean ligado;
    private int velocidade;

    // Construtor
    public Carro(String marca, String modelo, String cor) {
        this.marca = marca;
        this.modelo = modelo;
        this.cor = cor;
        this.ligado = false;
        this.velocidade = 0;
    }

    // Método para ligar o carro
    public void ligar() {
        if (!ligado) {
            ligado = true;
            System.out.println(modelo + " está ligado.");
        } else {
            System.out.println(modelo + " já está ligado.");
        }
    }

    // Método para desligar o carro
    public void desligar() {
        if (ligado && velocidade == 0) {
            ligado = false;
            System.out.println(modelo + " foi desligado.");
        } else if (velocidade > 0) {
            System.out.println("Reduza a velocidade antes de desligar o " + modelo + ".");
        } else {
            System.out.println(modelo + " já está desligado.");
        }
    }

    // Método para acelerar o carro
    public void acelerar(int aumento) {
        if (ligado) {
            velocidade += aumento;
            System.out.println(modelo + " acelerou para " + velocidade + " km/h.");
        } else {
            System.out.println("Ligue o carro antes de acelerar.");
        }
    }

    // Método para frear o carro
    public void frear(int reducao) {
        if (ligado && velocidade > 0) {
            velocidade -= reducao;
            if (velocidade < 0) {
                velocidade = 0;
            }
            System.out.println(modelo + " reduziu para " + velocidade + " km/h.");
        } else {
            System.out.println("O carro já está parado ou desligado.");
        }
    }

    // Método principal para testar a classe
    public static void main(String[] args) {
        Carro meuCarro = new Carro("Toyota", "Corolla", "Preto");

        meuCarro.ligar();
        meuCarro.acelerar(20);
        meuCarro.frear(10);
        meuCarro.desligar();
    }
}


 