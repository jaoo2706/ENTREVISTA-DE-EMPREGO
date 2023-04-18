# ENTREVISTA-DE-EMPREGO
import java.util.ArrayList;
import java.util.Scanner;

class Genre {
    private String nome;

    public Genre(String nome) {
        this.nome = nome;
    }

    public String getNome() {
        return nome;
    }
}

class Game {
    private String titulo;
    private String descricao;
    private String dataLancamento;
    private String desenvolvedora;
    private ArrayList<Genre> generos;

    public Game(String titulo, String descricao, String dataLancamento, String desenvolvedora, ArrayList<Genre> generos) {
        this.titulo = titulo;
        this.descricao = descricao;
        this.dataLancamento = dataLancamento;
        this.desenvolvedora = desenvolvedora;
        this.generos = generos;
    }

    public String getTitulo() {
        return titulo;
    }

    public String getDescricao() {
        return descricao;
    }

    public String getDataLancamento() {
        return dataLancamento;
    }

    public String getDesenvolvedora() {
        return desenvolvedora;
    }

    public ArrayList<Genre> getGeneros() {
        return generos;
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Genre> genres = new ArrayList<>();
        Scanner sc = new Scanner(System.in);

        // Lê os gêneros de jogos
        System.out.print("Digite o número de gêneros: ");
        int nGeneros = sc.nextInt();
        sc.nextLine(); // Consome o restante da linha após o nextInt

        for (int i = 0; i < nGeneros; i++) {
            System.out.print("Digite o nome do gênero " + (i+1) + ": ");
            String nomeGenero = sc.nextLine();
            Genre genero = new Genre(nomeGenero);
            genres.add(genero);
        }

        // Lê os dados do jogo
        System.out.println("\nCadastro de jogo");
        System.out.print("Título: ");
        String titulo = sc.nextLine();
        System.out.print("Descrição: ");
        String descricao = sc.nextLine();
        System.out.print("Data de lançamento: ");
        String dataLancamento = sc.nextLine();
        System.out.print("Desenvolvedora: ");
        String desenvolvedora = sc.nextLine();
        ArrayList<Genre> generos = new ArrayList<>();

        System.out.println("\nEscolha o(s) gênero(s) do jogo:");
        for (Genre genero : genres) {
            System.out.print(genero.getNome() + " (S/N)? ");
            String escolha = sc.nextLine().toLowerCase();
            if (escolha.equals("s")) {
                generos.add(genero);
            }
        }

        Game jogo = new Game(titulo, descricao, dataLancamento, desenvolvedora, generos);

        // Exibe os dados do jogo
        System.out.println("\nDados do jogo cadastrado:");
        System.out.println("Título: " + jogo.getTitulo());
        System.out.println("Descrição: " + jogo.getDescricao());
        System.out.println("Data de lançamento: " + jogo.getDataLancamento());
        System.out.println("Desenvolvedora: " + jogo.getDesenvolvedora());
        System.out.print("Gêneros: ");
        ArrayList<Genre> generosDoJogo = jogo.getGeneros();
        for (int i = 0; i < generosDoJogo.size(); i++) {
            System.out.println(generosDoJogo.get(i).getNome() + " ");
}
System.out.println();
sc.close();
}
}
