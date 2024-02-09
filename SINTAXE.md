# SINTAXE POO
POO (Programação Orientada a Objetos) é um paradigma de programação que se baseia na ideia de "objetos", que podem conter dados na forma de campos, também conhecidos como atributos, e código, na forma de procedimentos, geralmente chamados de métodos. Esses objetos são instâncias de classes, que funcionam como modelos para criar objetos.

Os quatro pilares da programação orientada a objetos são:

1. **Encapsulamento:**
   - O encapsulamento em C# é similar ao Java, usando modificadores de acesso para controlar o acesso aos membros de uma classe.
   
   Exemplo:
   ```csharp
   public class ContaBancaria {
       private double saldo;
       
       public void Depositar(double valor) {
           saldo += valor;
       }
       
       public double GetSaldo() {
           return saldo;
       }
   }
   ```
   Neste exemplo, `saldo` é encapsulado com o modificador `private`, impedindo o acesso direto de outras classes a ele.

2. **Herança:**
   - A herança em C# permite que uma classe herde características (métodos e atributos) de outra classe, promovendo a reutilização de código.
   
   Exemplo:
   ```csharp
   public class Animal {
       public void EmitirSom() {
           Console.WriteLine("Som do animal");
       }
   }
   
   public class Cachorro : Animal {
       public void Latir() {
           Console.WriteLine("Au Au!");
       }
   }
   ```
   Na classe `Cachorro`, o símbolo `:` é usado para indicar que `Cachorro` herda de `Animal`.

3. **Polimorfismo:**
   - O polimorfismo em C# permite que objetos de diferentes classes sejam tratados de maneira uniforme. Isso pode ser alcançado por meio de sobrecarga (overloading) e substituição (overriding) de métodos.
   
   Exemplo:
   ```csharp
   public class Animal {
       public virtual void EmitirSom() {
           Console.WriteLine("Som do animal");
       }
   }
   
   public class Cachorro : Animal {
       public override void EmitirSom() {
           Console.WriteLine("Au Au!");
       }
   }
   ```
   Aqui, o método `EmitirSom` é substituído na classe `Cachorro`, alterando seu comportamento.

4. **Abstração:**
   - A abstração em C# é alcançada usando classes abstratas e interfaces, permitindo a definição de métodos sem implementação.
   
   Exemplo:
   ```csharp
   public abstract class Forma {
       public abstract double CalcularArea();
   }
   
   public class Circulo : Forma {
       private double raio;
       
       public override double CalcularArea() {
           return Math.PI * raio * raio;
       }
   }
   ```
   A classe `Forma` é abstrata e define um método `CalcularArea` que deve ser implementado por suas subclasses, como `Circulo`.

Estes são os quatro pilares da programação orientada a objetos implementados em C#. Cada pilar desempenha um papel fundamental na criação de sistemas orientados a objetos robustos e reutilizáveis.