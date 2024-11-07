Vamos iniciar sua jornada com POO (Programação Orientada a Objetos) em Java! Vou dividir o conteúdo em seções para facilitar o aprendizado. Vou explicar os principais conceitos e incluir exemplos práticos, exercícios e, no final, um projeto para aplicar o que você aprendeu.

### Estrutura do Estudo

1. **Conceitos Fundamentais de POO**
   - Classes e Objetos
   - Atributos e Métodos
   - Encapsulamento
   - Herança
   - Polimorfismo
   - Abstração

2. **Exercícios de Fixação**
   - Exercícios práticos para aplicar cada conceito.

3. **Projeto Final**
   - Um projeto que envolva a criação de um sistema básico aplicando todos os conceitos.

Vamos começar com os conceitos fundamentais e exemplos básicos!

---

### 1. Conceitos Fundamentais de POO

#### 1.1 Classes e Objetos

- **Classe**: é a estrutura ou molde de um objeto.
- **Objeto**: é uma instância de uma classe, ou seja, uma “cópia” da classe em si.

**Exemplo Prático**

Imagine uma classe chamada `Carro`. Nessa classe, vamos definir algumas propriedades (atributos) e comportamentos (métodos) comuns aos carros.

```java
public class Carro {
    // Atributos
    String modelo;
    String cor;
    int ano;

    // Método
    void ligar() {
        System.out.println("O carro está ligado.");
    }
}
```

Para criar um **objeto** dessa classe:

```java
public class Main {
    public static void main(String[] args) {
        Carro meuCarro = new Carro(); // Instância de Carro
        meuCarro.modelo = "Civic";
        meuCarro.cor = "Preto";
        meuCarro.ano = 2020;

        System.out.println("Modelo: " + meuCarro.modelo);
        System.out.println("Cor: " + meuCarro.cor);
        System.out.println("Ano: " + meuCarro.ano);

        meuCarro.ligar();
    }
}
```

**Exercício 1:** Crie uma classe chamada `Livro` com os atributos `titulo`, `autor` e `anoPublicacao`. Em seguida, crie um objeto da classe `Livro`, defina os valores para os atributos e exiba-os no console.

---

#### 1.2 Atributos e Métodos

- **Atributos**: Características ou propriedades de uma classe.
- **Métodos**: Comportamentos ou ações que a classe pode realizar.

No exemplo anterior, `modelo`, `cor`, e `ano` são atributos, enquanto `ligar()` é um método. Vamos expandir nossa classe `Carro` para incluir um método `acelerar()`.

```java
public class Carro {
    String modelo;
    String cor;
    int ano;

    void ligar() {
        System.out.println("O carro está ligado.");
    }

    void acelerar() {
        System.out.println("O carro está acelerando.");
    }
}
```

---

#### 1.3 Encapsulamento

Encapsulamento é o conceito de proteger os dados da classe, tornando-os acessíveis apenas através de métodos específicos. Em Java, usamos modificadores de acesso, como `private`, `public`, e `protected`.

**Exemplo Prático**

```java
public class Carro {
    private String modelo;
    private String cor;
    private int ano;

    // Métodos Getters e Setters
    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public String getCor() {
        return cor;
    }

    public void setCor(String cor) {
        this.cor = cor;
    }

    public int getAno() {
        return ano;
    }

    public void setAno(int ano) {
        this.ano = ano;
    }

    void ligar() {
        System.out.println("O carro está ligado.");
    }
}
```

**Exercício 2:** Modifique a classe `Livro` criada anteriormente para encapsular seus atributos e crie métodos `get` e `set` para cada um deles.

---

#### 1.4 Herança

A herança permite que uma classe herde características e comportamentos de outra.

**Exemplo Prático**

Vamos criar uma classe `Veiculo` e fazer com que `Carro` herde dela:

```java
public class Veiculo {
    String marca;

    void ligar() {
        System.out.println("O veículo está ligado.");
    }
}

public class Carro extends Veiculo {
    String modelo;
}
```

**Exercício 3:** Crie uma classe `LivroFisico` que herde de `Livro`, e adicione o atributo `peso`. Depois, crie um objeto dessa nova classe.

---

#### 1.5 Polimorfismo

O polimorfismo permite que um mesmo método se comporte de maneiras diferentes, dependendo da classe que o implementa.

**Exemplo Prático**

Vamos adicionar uma classe `Moto` que também herda de `Veiculo` e sobrescreve o método `ligar()`:

```java
public class Moto extends Veiculo {
    @Override
    void ligar() {
        System.out.println("A moto está ligada.");
    }
}
```

**Exercício 4:** Crie uma nova classe chamada `Bicicleta`, que também herda de `Veiculo`, mas sem motor, e sobrescreva o método `ligar()` para indicar que ela não possui um.

---

#### 1.6 Abstração

Abstração é o processo de ocultar detalhes complexos e exibir apenas a funcionalidade essencial.

Vamos transformar `Veiculo` em uma classe abstrata:

```java
public abstract class Veiculo {
    String marca;

    abstract void ligar();
}
```

**Exercício 5:** Crie uma classe abstrata chamada `Animal` com um método `emitirSom()`. Crie classes `Cachorro` e `Gato` que herdam de `Animal` e implementam `emitirSom()` de forma diferente para cada animal.

---

### 2. Projeto Final: Sistema de Biblioteca

**Descrição**: Crie um sistema básico para gerenciar uma biblioteca. O sistema deve ter as seguintes classes e funcionalidades:

- **Classes Principais**:
  - `Livro` (com atributos encapsulados como título, autor, ano de publicação, etc.)
  - `Usuario` (representa o usuário da biblioteca, com atributos como nome e ID)
  - `Emprestimo` (representa o empréstimo de um livro, com atributos como data do empréstimo e data de devolução)

- **Funcionalidades**:
  - Permitir que um usuário faça o empréstimo de um livro.
  - Registrar a devolução de um livro.
  - Mostrar a lista de livros disponíveis e a lista de livros emprestados.
  
**Dicas para Organização**:
- Crie métodos que encapsulem a lógica do sistema (ex.: `realizarEmprestimo()`, `devolverLivro()`).
- Use polimorfismo para tratar diferentes tipos de usuários (ex.: `Aluno`, `Professor`).
- Lembre-se de encapsular os atributos e usar herança e abstração onde for necessário.

---

Com esses fundamentos, você terá um projeto bem estruturado e um código pronto para ser publicado no GitHub.
