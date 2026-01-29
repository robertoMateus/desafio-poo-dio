# Desafio POO - DIO

Um projeto educacional que demonstra conceitos de **Programação Orientada a Objetos (POO)** em Java, implementando um sistema de gerenciamento de bootcamps, cursos e mentorias.

## 📋 Descrição

Este desafio implementa um sistema de bootcamp que permite:

- **Criar bootcamps** com conteúdos (cursos e mentorias)
- **Inscrever desenvolvedores** em bootcamps
- **Rastrear progresso** dos desenvolvedores
- **Calcular experiência (XP)** ganha ao completar conteúdos

## 🏗️ Arquitetura

### Classes Principais

#### `Conteudo` (Abstrata)
Classe base que representa qualquer conteúdo do bootcamp.
- **XP_PADRAO**: 10 pontos de experiência padrão
- **calcularXp()**: Método abstrato para calcular XP

#### `Curso`
Extends `Conteudo` - Representa um curso com duração.
- **cargaHoraria**: Horas de duração do curso
- **XP**: Calculado como `XP_PADRAO * cargaHoraria`

#### `Mentoria`
Extends `Conteudo` - Representa uma sessão de mentoria.
- **data**: Data da mentoria

#### `Dev`
Representa um desenvolvedor inscrito em bootcamps.
- **conteudosInscritos**: Cursos/mentorias em andamento
- **conteudosConcluidos**: Conteúdos já finalizados
- **inscreverBootcamp()**: Inscreve em um bootcamp
- **progredir()**: Move o primeiro conteúdo de inscritos para concluídos
- **calcularTotalXp()**: Calcula XP total ganha

#### `Bootcamp`
Representa um programa de capacitação.
- **conteudos**: Lista de cursos e mentorias
- **devsInscritos**: Desenvolvedores inscritos
- **dataInicio** / **dataFim**: Duração do bootcamp (45 dias por padrão)

## 💻 Como Usar

### Exemplo de Uso

```java
// Criar cursos
Curso curso1 = new Curso();
curso1.setTitulo("Curso Java");
curso1.setCargaHoraria(8);

// Criar mentoria
Mentoria mentoria = new Mentoria();
mentoria.setTitulo("Mentoria de Java");
mentoria.setData(LocalDate.now());

// Criar bootcamp e adicionar conteúdos
Bootcamp bootcamp = new Bootcamp();
bootcamp.setNome("Bootcamp Java Developer");
bootcamp.getConteudos().add(curso1);
bootcamp.getConteudos().add(mentoria);

// Inscrever desenvolvedor
Dev dev = new Dev();
dev.setNome("João");
dev.inscreverBootcamp(bootcamp);

// Progredir (conclui conteúdos)
dev.progredir();

// Verificar progresso e XP
System.out.println("XP Total: " + dev.calcularTotalXp());
```

## 🎯 Conceitos de POO Implementados

- **Herança**: `Curso` e `Mentoria` herdam de `Conteudo`
- **Polimorfismo**: Implementação de `calcularXp()` diferente em cada classe
- **Encapsulamento**: Uso de getters/setters para acesso aos atributos
- **Abstração**: Classe abstrata `Conteudo` define o contrato
- **Collections**: Uso de `Set` para gerenciar coleções sem duplicatas

## 📂 Estrutura de Pastas

```
desafio-poo-dio/
├── src/
│   ├── Main.java
│   └── br/com/dio/desafio/dominio/
│       ├── Bootcamp.java
│       ├── Conteudo.java
│       ├── Curso.java
│       ├── Dev.java
│       └── Mentoria.java
└── README.md
```

## 🚀 Como Executar

1. Compile o projeto:
   ```bash
   javac -d bin src/**/*.java
   ```

2. Execute a classe Main:
   ```bash
   java -cp bin Main
   ```

## 📊 Saída Esperada

O programa demonstra dois desenvolvedores progredindo em um bootcamp:
- **Camila**: Conclui 1 conteúdo
- **João**: Conclui 3 conteúdos

Com cálculo automático de XP ganha em cada progresso.

## 🎓 Objetivo de Aprendizado

Este desafio foi criado para praticar:
- Design de classes com POO
- Uso de Collections (Set)
- Manipulação de datas (LocalDate)
- Streams e lambdas (Java 8+)
- Tratamento de erros com Optional

## 📝 Sobre

**Desafio Proposto por**: [DIO - Digital Innovation One](https://www.dio.me)

**Implementado por**: **Roberto Mateus de Melo Silva**

📱 Conecte-se comigo: [![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/roberto-mateus-de-melo-silva)

---

**Última atualização**: 29 de janeiro de 2026
