# ENCAPSULAMENTO
Encapsulamento é o processo de esconder os detalhes internos de como um objeto funciona e restringir o acesso direto aos seus componentes internos. Em C#, isso é geralmente alcançado usando modificadores de acesso (public, private, protected) para controlar o acesso aos membros de uma classe (métodos e atributos).

## Exemplo de Encapsulamento em C#:
Considere a seguinte classe em C# que representa uma conta bancária:

```csharp
public class ContaBancaria {
    private double saldo;

    public ContaBancaria(double saldoInicial) {
        this.saldo = saldoInicial;
    }

    // Método para depositar dinheiro na conta
    public void Depositar(double valor) {
        if (valor > 0) {
            this.saldo += valor;
            Console.WriteLine("Depósito de " + valor + " realizado com sucesso.");
        } else {
            Console.WriteLine("Valor inválido para depósito.");
        }
    }

    // Método para sacar dinheiro da conta
    public void Sacar(double valor) {
        if (valor > 0 && valor <= saldo) {
            this.saldo -= valor;
            Console.WriteLine("Saque de " + valor + " realizado com sucesso.");
        } else {
            Console.WriteLine("Saldo insuficiente ou valor inválido para saque.");
        }
    }

    // Propriedade para acessar o saldo da conta
    public double Saldo {
        get { return saldo; }
    }
}
```

Neste exemplo, a variável `saldo` é declarada como `private`, o que significa que ela só pode ser acessada dentro da própria classe `ContaBancaria`. Isso garante que o saldo só pode ser modificado por métodos da própria classe, como `Depositar()` e `Sacar()`, e não diretamente por outros objetos.

A propriedade `Saldo` é fornecida para permitir que outros objetos obtenham o saldo da conta, mas sem a capacidade de modificá-lo diretamente. Isso é um exemplo de encapsulamento, onde os detalhes internos da implementação da classe são ocultos e o acesso aos dados é controlado através de métodos públicos.

## Diferenças entre `get` e `set`:
Os métodos `get` e `set`, frequentemente chamados de getters e setters, são usados em programação orientada a objetos para acessar (get) e modificar (set) os valores dos atributos de uma classe. Vou explicar as diferenças entre eles:

### Método `get` (Getter):
- **Objetivo**: O método `get` é usado para obter o valor de um atributo de uma classe.
- **Convenção de nomenclatura**: O nome do método `get` geralmente começa com o nome da propriedade (com a primeira letra em maiúscula).
- **Retorno de valor**: Um método `get` geralmente retorna o valor atual do atributo.
- **Exemplo**:

```csharp
public class Exemplo {
    private int numero;

    public int Numero {
        get { return numero; }
    }
}
```

### Método `set` (Setter):
- **Objetivo**: O método `set` é usado para definir (setar) o valor de um atributo de uma classe.
- **Convenção de nomenclatura**: O nome do método `set` geralmente começa com o nome da propriedade (com a primeira letra em maiúscula).
- **Parâmetros**: Um método `set` geralmente recebe um parâmetro que é o novo valor a ser atribuído ao atributo.
- **Exemplo**:

```csharp
public class Exemplo {
    private int numero;

    public int Numero {
        set { numero = value; }
    }
}
```

## Diferenças entre `private`, `public` e `protected`:
Em C#, os modificadores de acesso (`private`, `public` e `protected`) são usados para controlar o acesso aos membros de uma classe (métodos e atributos) por outras classes. Vou explicar as diferenças entre esses modificadores:

### `private`:
- **Acesso restrito**: Os membros declarados como `private` só podem ser acessados dentro da própria classe onde foram declarados.
- **Encapsulamento**: É útil para garantir o encapsulamento, pois permite que os detalhes internos de uma classe sejam ocultados e protegidos de acesso externo.
- **Exemplo**:

```csharp
public class Exemplo {
    private int numero;

    private void MetodoPrivado() {
        // Este método só pode ser chamado dentro da classe Exemplo
    }
}
```

### `public`:
- **Acesso irrestrito**: Membros declarados como `public` podem ser acessados de qualquer lugar, dentro ou fora da classe onde foram declarados.
- **Visibilidade global**: É útil para fornecer uma interface pública para os usuários da classe, permitindo que eles acessem seus métodos e atributos.
- **Exemplo**:

```csharp
public class Exemplo {
    public int Numero { get; set; }

    public void MetodoPublico() {
        // Este método pode ser chamado de qualquer lugar
    }
}
```

### `protected`:
- **Acesso na mesma classe e subclasses**: Os membros declarados como `protected` podem ser acessados dentro da mesma classe e também por subclasses (mesmo que estejam em namespaces diferentes).
- **Exemplo**:

```csharp
public class Exemplo {
    protected int numero;

    protected void MetodoProtegido() {
        // Este método pode ser chamado dentro da classe Exemplo e suas subclasses
    }
}
```

## Benefícios do Encapsulamento:
1. **Segurança dos dados**: Encapsular os dados dentro de uma classe, controlando o acesso a eles, protege-os contra modificações acidentais ou não autorizadas.

2. **Modularidade e manutenção**: O encapsulamento promove a modularidade do código, tornando mais fácil entender, modificar e manter o sistema, pois os detalhes internos de uma classe são isolados do restante do programa.

3. **Reutilização de código**: Ao encapsular os detalhes de implementação dentro de classes, é possível reutilizar essas classes em diferentes partes do sistema sem modificar seu comportamento externo.
