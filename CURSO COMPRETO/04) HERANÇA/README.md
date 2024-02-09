# HERANÇA 
Herança permite que uma classe herde características (métodos e atributos) de outra classe. A classe que herda é chamada de subclasse (ou classe derivada), e a classe da qual ela herda é chamada de superclasse (ou classe base). Vou explicar os conceitos básicos da herança em C# e fornecer um exemplo para ilustrar seu uso.

## Conceitos básicos:
1. **Superclasse (Classe Base)**: É a classe que fornece os métodos e atributos a serem herdados. Ela define o comportamento básico que será compartilhado por suas subclasses.

2. **Subclasse (Classe Derivada)**: É a classe que herda os métodos e atributos da superclasse. Ela pode adicionar novos métodos e atributos, ou modificar o comportamento dos métodos herdados.

3. **Relação "é-um"**: A herança é frequentemente modelada quando uma classe é um tipo mais específico da classe base. Por exemplo, se tivermos uma classe `Animal` como superclasse e uma classe `Cachorro` como subclasse, podemos dizer que um cachorro é um tipo de animal.

## Exemplo em C#:
```csharp
using System;

// Superclasse (Classe Base)
class Animal {
    public string Nome { get; set; }
    public int Idade { get; set; }

    public Animal(string nome, int idade) {
        Nome = nome;
        Idade = idade;
    }

    public void Comer() {
        Console.WriteLine(Nome + " está comendo.");
    }
}

// Subclasse (Classe Derivada)
class Cachorro : Animal {
    public string Raca { get; set; }

    public Cachorro(string nome, int idade, string raca) : base(nome, idade) {
        Raca = raca;
    }

    public void Latir() {
        Console.WriteLine(Nome + " está latindo.");
    }
}

// Exemplo de uso
class ExemploHeranca {
    static void Main(string[] args) {
        Cachorro cachorro = new Cachorro("Rex", 3, "Labrador");
        cachorro.Comer(); // Método herdado da superclasse Animal
        cachorro.Latir(); // Método da subclasse Cachorro
    }
}
```

Neste exemplo, a classe `Animal` é a superclasse que possui as propriedades `Nome` e `Idade`, bem como o método `Comer()`. A classe `Cachorro` é a subclasse que herda essas propriedades e métodos da superclasse e adiciona a propriedade `Raca` e o método `Latir()`.

Quando criamos um objeto `Cachorro`, ele pode acessar tanto os membros da classe `Animal` quanto os membros adicionais da classe `Cachorro`, graças à herança.

A herança é útil para promover a reutilização de código, estabelecer uma hierarquia entre classes relacionadas e modelar relações do mundo real de forma mais eficiente. No entanto, é importante usar herança com moderação e entender suas implicações, pois uma hierarquia de classes muito profunda pode tornar o código complexo e difícil de manter.
