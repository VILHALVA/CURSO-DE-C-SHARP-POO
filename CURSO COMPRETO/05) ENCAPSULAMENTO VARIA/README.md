# ENCAPSULAMENTO VARIA
Em C#, o encapsulamento é alcançado principalmente usando modificadores de acesso, como `public`, `private`, `protected` e `internal`, para controlar o acesso aos membros de uma classe.

Vou explicar o encapsulamento com exemplos de código em C#:

1. **Encapsulamento usando modificadores de acesso:**

```csharp
using System;

public class Carro
{
    // Variáveis privadas, acessíveis apenas dentro da classe Carro
    private string modelo;
    private int ano;

    // Propriedades públicas para acessar as variáveis privadas (getters e setters)
    public string Modelo
    {
        get { return modelo; }
        set { modelo = value; }
    }

    public int Ano
    {
        get { return ano; }
        set { ano = value; }
    }
}

class Program
{
    static void Main(string[] args)
    {
        Carro meuCarro = new Carro();
        
        // Atribuição direta não é possível devido ao encapsulamento
        // meuCarro.modelo = "Toyota"; // Erro de compilação

        // Mas podemos acessar e modificar os membros usando propriedades públicas
        meuCarro.Modelo = "Toyota";
        meuCarro.Ano = 2022;

        // Acesso aos valores usando propriedades públicas
        Console.WriteLine("Modelo: " + meuCarro.Modelo);
        Console.WriteLine("Ano: " + meuCarro.Ano);
    }
}
```

Neste exemplo, a classe `Carro` encapsula os detalhes de implementação, como o modelo e o ano, ocultando-os do mundo exterior. Os membros `modelo` e `ano` são declarados como privados para que não possam ser acessados diretamente de fora da classe. Em vez disso, eles são acessados e modificados através de propriedades públicas, o que permite que a classe controle e valide o acesso aos seus dados internos.

2. **Encapsulamento com métodos:**

```csharp
using System;

public class ContaBancaria
{
    private double saldo;

    // Método público para depositar dinheiro na conta
    public void Depositar(double valor)
    {
        saldo += valor;
    }

    // Método público para sacar dinheiro da conta
    public void Sacar(double valor)
    {
        if (valor <= saldo)
        {
            saldo -= valor;
        }
        else
        {
            Console.WriteLine("Saldo insuficiente.");
        }
    }

    // Método público para obter o saldo da conta
    public double ObterSaldo()
    {
        return saldo;
    }
}

class Program
{
    static void Main(string[] args)
    {
        ContaBancaria minhaConta = new ContaBancaria();
        
        minhaConta.Depositar(1000);
        minhaConta.Sacar(500);

        Console.WriteLine("Saldo atual: " + minhaConta.ObterSaldo());
    }
}
```

Neste exemplo, a classe `ContaBancaria` encapsula o saldo da conta e fornece métodos públicos (`Depositar`, `Sacar` e `ObterSaldo`) para interagir com ele. Isso garante que o saldo só possa ser modificado de acordo com a lógica definida nos métodos da classe.

O encapsulamento é crucial para manter a integridade dos dados e facilitar a manutenção e evolução do código, já que os detalhes de implementação são mantidos internos à classe e podem ser modificados sem afetar o restante do sistema.