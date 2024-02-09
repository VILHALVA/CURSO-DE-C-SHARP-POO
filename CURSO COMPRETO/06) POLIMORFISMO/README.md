# POLIMORFISMO 
Polimorfismo permite que objetos de diferentes classes sejam tratados de forma uniforme, proporcionando flexibilidade e extensibilidade ao código. Em C#, existem duas formas principais de polimorfismo: polimorfismo de subtipo (ou polimorfismo de herança) e polimorfismo de sobrecarga (ou polimorfismo estático). Vou explicar cada um deles:

## Polimorfismo de Subtipo (Herança):
O polimorfismo de subtipo ocorre quando uma classe herda de outra classe e substitui (ou sobrescreve) um método da classe base. Isso permite que um objeto da classe derivada seja tratado como um objeto da classe base.

Exemplo:

```csharp
using System;

// Superclasse
class Animal {
    public virtual void FazerSom() {
        Console.WriteLine("Animal fazendo som");
    }
}

// Subclasse
class Cachorro : Animal {
    public override void FazerSom() {
        Console.WriteLine("Cachorro latindo");
    }
}

// Exemplo de uso
class ExemploPolimorfismo {
    static void Main(string[] args) {
        Animal animal = new Cachorro(); // Polimorfismo de subtipo
        animal.FazerSom(); // O método FazerSom() do Cachorro é chamado
    }
}
```

Neste exemplo, a classe `Cachorro` herda da classe `Animal` e sobrescreve o método `FazerSom()`. Ao criar um objeto do tipo `Cachorro` e atribuí-lo a uma referência do tipo `Animal`, podemos chamar o método `FazerSom()` e obter o comportamento específico da classe `Cachorro`. Isso é polimorfismo de subtipo.

## Polimorfismo de Sobrecarga (Estático):
O polimorfismo de sobrecarga ocorre quando duas ou mais classes têm métodos com o mesmo nome, mas diferentes parâmetros. Isso permite que métodos com o mesmo nome se comportem de maneira diferente com base nos argumentos fornecidos.

Exemplo:

```csharp
using System;

class Calculadora {
    public int Somar(int a, int b) {
        return a + b;
    }

    public double Somar(double a, double b) {
        return a + b;
    }
}

// Exemplo de uso
class ExemploPolimorfismo {
    static void Main(string[] args) {
        Calculadora calc = new Calculadora();
        int resultadoInteiro = calc.Somar(5, 3); // Chama o método com inteiros
        double resultadoDouble = calc.Somar(2.5, 3.5); // Chama o método com doubles
        Console.WriteLine("Resultado Inteiro: " + resultadoInteiro);
        Console.WriteLine("Resultado Double: " + resultadoDouble);
    }
}
```

Neste exemplo, a classe `Calculadora` tem dois métodos `Somar()`, um que aceita dois inteiros e outro que aceita dois doubles. Dependendo dos tipos dos argumentos fornecidos, o compilador C# selecionará automaticamente o método apropriado para chamar. Isso é polimorfismo de sobrecarga.

Em resumo, o polimorfismo em C# permite que objetos de diferentes classes sejam tratados de forma uniforme, aumentando a flexibilidade e extensibilidade do código. Ele é alcançado através de herança (polimorfismo de subtipo) e sobrecarga de métodos (polimorfismo de sobrecarga).
