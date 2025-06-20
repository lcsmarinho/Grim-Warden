# Grim Warden

**Um Roguelike Cooperativo com Curadoria Preditiva.**  
Jogadores e um "Guardião" (Oráculo) se unem contra um sistema imprevisível, usando cartas e estratégia para sobreviver em um tabuleiro tático.

---

## Visão Geral

**Grim Warden** é uma reimaginação dos RPGs de browser, com foco na cooperação, estratégia e uma forte dose de nostalgia. No seu núcleo, é um jogo de cartas tático, onde a ação se desenrola em um tabuleiro, não em um mapa de mundo aberto.

Em vez de competir, um grupo de 4 jogadores anônimos é pareado com um jogador especial, o **Guardião (Warden)**. O objetivo de todos é o mesmo: derrotar os desafios gerados proceduralmente por um "Sistema" impiedoso.

O Guardião tem a habilidade única de prever os desafios futuros, usando suas cartas de "Ajuda" para preparar o terreno e salvar os jogadores em momentos críticos.  
A comunicação é feita inteiramente através das ações no jogo, exigindo que os jogadores confiem uns nos outros e nas intervenções do Guardião para ter sucesso.

---

## Estética e Gameplay

Nossa inspiração é uma fusão de conceitos clássicos:

- **Estética Visual**: Inspirada em jogos de browser como *Tibia* (anos 90/2000).  
  Arte pixelada, sprites simples e interface direta, focada em funcionalidade e painéis de informação.

- **Apresentação do Jogo**: Inspirada em jogos de carta de console como *Yu-Gi-Oh! Forbidden Memories (PS1)*.  
  A tela é um tabuleiro estático, onde as cartas e os status dos monstros e jogadores são o foco principal. Animações são mínimas e diretas.

- **Ritmo da Batalha**: Combate tático por turnos inspirado em JRPGs clássicos como *Final Fantasy*.  
  A ordem das ações é determinada por um atributo de **Velocidade** dinâmico, criando um fluxo de batalha onde usar habilidades fortes pode custar agilidade no próximo turno.

---

## O Tabuleiro e a Informação

Toda a ação acontece em um tabuleiro. Cada jogador possui um "campo de status" com suas informações.

### Privacidade e Revelação (Névoa de Guerra)

- Informações como o nível exato de um jogador ou certos atributos podem ser mantidas privadas por padrão.
- Quando uma ação utiliza um atributo específico (ex: um ataque baseado em Força), o valor daquele atributo é revelado no log da partida.
- Status de monstros são ocultos inicialmente.  
  Após derrotar um tipo de monstro pela primeira vez, suas estatísticas completas (vida, fraquezas, etc.) ficam permanentemente visíveis no **bestíario** do jogador.

---

## Tecnologias Utilizadas

### Backend

- Java 17+
- Apache Tomcat (embutido via Spring Boot)
- Spring Boot (configuração de Tomcat, JPA, WebSockets)
- JPA (Hibernate) para persistência
- Lombok para reduzir boilerplate
- Maven ou Gradle para gerenciamento de dependências

### Frontend

- HTML5
- CSS3
- JavaScript (Vanilla, ES6+ Modules)

### Banco de Dados

- PostgreSQL (Produção)
- H2 (Desenvolvimento local)

### Dados do Jogo

- Arquivos JSON para definir cartas, monstros, módulos de campanha e recompensas  
  → Permite fácil adição de conteúdo sem recompilar o backend.

---

## Como Começar (Ambiente de Desenvolvimento)

### Clone o repositório

```bash
git clone https://github.com/lcsmarinho/grim-warden.git
````

### Configure o Backend

1. Importe o projeto Maven/Gradle na sua IDE de preferência (IntelliJ IDEA ou Eclipse).
2. Configure uma instância local do PostgreSQL ou utilize o perfil de desenvolvimento com H2.
3. Execute a classe principal da aplicação Java. O servidor Tomcat embutido será iniciado automaticamente.

### Execute o Frontend

A maneira mais simples de servir os arquivos estáticos:

1. Use a extensão **Live Server** no Visual Studio Code.
2. Abra o arquivo `frontend/index.html` no navegador.

