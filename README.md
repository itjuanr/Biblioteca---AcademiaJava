# 📚 Sistema de Gerenciamento de Biblioteca

> Um sistema robusto para controle de acervo e fluxo de empréstimos, desenvolvido com foco em Orientação a Objetos.

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-green)

## 💻 Sobre o Projeto

Este projeto consiste em um sistema backend para gerenciamento de bibliotecas. O objetivo principal foi aplicar pilares da **Programação Orientada a Objetos (POO)** para resolver um problema real de negócio: o controle de inventário e circulação de livros.

O sistema permite que bibliotecários realizem operações de CRUD (Create, Read, Update, Delete) no acervo, além de gerenciar o estado de cada exemplar (disponível/emprestado) de forma segura.

## 🛠️ Tecnologias e Conceitos

* **Java (JDK):** Linguagem core do projeto.
* **Java Collections Framework:** Uso de `ArrayList` para manipulação dinâmica de dados.
* **POO:** Encapsulamento, Métodos e Classes bem definidas.

## 📂 Estrutura do Projeto

O código foi arquitetado em classes com responsabilidades únicas:

### 1. Classe `Livro`
Representa a entidade principal. Responsável por manter o estado do objeto (se está emprestado ou não) e suas informações vitais.
* **Atributos:** Título, Autor, ISBN, Status.
* **Lógica:** O método `reservar()` possui validação interna para impedir que um livro já emprestado seja reservado novamente.

### 2. Classe `Biblioteca`
Atua como o **controller** do sistema. Ela gerencia a coleção de livros e expõe os métodos públicos para interação com o usuário.
* **Busca Inteligente:** Localiza livros por trechos do título.
* **Gestão de IDs:** Utiliza o ISBN como chave única para remoção e empréstimos.

## 🚀 Como Executar

### Pré-requisitos
Certifique-se de ter o [Java JDK](https://www.oracle.com/java/technologies/downloads/) instalado em sua máquina.

1. **Clone o repositório:**
```bash
git clone [https://github.com/seu-usuario/projeto-biblioteca.git](https://github.com/seu-usuario/projeto-biblioteca.git)

```

2. **Compile os arquivos:**
```bash
javac *.java

```


3. **Execute o sistema:**
```bash
java Main

```



☕ Exemplo de UsoAbaixo, um exemplo de como instanciar a biblioteca e realizar operações básicas:

```java
public class Main {
    public static void main(String[] args) {
        // 1. Instanciando o sistema
        Biblioteca biblioteca = new Biblioteca();

        // 2. Adicionando livros ao acervo
        biblioteca.adicionarLivro("Dom Casmurro", "Machado de Assis", "978-85-000");
        biblioteca.adicionarLivro("Clean Code", "Robert C. Martin", "978-01-323");

        // 3. Realizando um empréstimo pelo ISBN
        if(biblioteca.emprestarLivro("978-85-000")) {
            System.out.println("Livro emprestado com sucesso!");
        }

        // 4. Listando livros disponíveis
        System.out.println(biblioteca.listarLivros());
    }
}

```

🔮 Melhorias FuturasEste projeto serve como base e pode ser expandido com:

* [ ] Implementação de interface gráfica (Swing ou JavaFX).
* [ ] Persistência de dados em Banco de Dados (MySQL ou SQLite).
* [ ] Sistema de multas por atraso na devolução.

---
