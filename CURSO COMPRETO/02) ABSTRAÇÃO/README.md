# ABSTRAÇÃO 
A abstração é um dos pilares fundamentais da programação orientada a objetos (POO). Ela permite que você represente os aspectos essenciais de um objeto do mundo real em um modelo simplificado no seu programa, ocultando os detalhes desnecessários e destacando apenas as informações relevantes para a interação.

Em C#, a abstração é frequentemente alcançada através do uso de classes abstratas e interfaces.

## Classes Abstratas:
Uma classe abstrata é uma classe que não pode ser instanciada diretamente, ou seja, você não pode criar objetos dessa classe. Em vez disso, ela serve como um modelo para outras classes que estendem (herdam) dela. Uma classe abstrata pode conter métodos abstratos (métodos sem implementação) e métodos concretos (com implementação). Métodos abstratos são definidos na classe abstrata, mas sua implementação é deixada para as subclasses.

Exemplo de uma classe abstrata em C#:

```csharp
abstract class Animal {
    // Método abstrato (sem implementação)
    public abstract void FazerSom();

    // Método concreto
    public void Dormir() {
        Console.WriteLine("Zzzz...");
    }
}
```

## Interfaces:
Uma interface é semelhante a uma classe abstrata, mas pode conter apenas métodos abstratos e constantes (variáveis ​​final). Ela define um conjunto de métodos que uma classe que a implementa deve fornecer. As interfaces permitem a implementação de múltiplas heranças em C#, o que significa que uma classe pode implementar várias interfaces.

Exemplo de uma interface em C#:

```csharp
interface IAnimal {
    // Método abstrato (sem implementação)
    void FazerSom();

    // Constante
    int NumeroDePernas { get; }
}
```

## Benefícios da Abstração:
1. **Simplificação**: A abstração permite simplificar modelos complexos, focando apenas nos aspectos relevantes.

2. **Reutilização de código**: Classes abstratas e interfaces promovem a reutilização de código, pois definem um contrato que outras classes podem seguir.

3. **Manutenção**: Ao usar abstração, você pode separar as preocupações e manter partes do código de forma isolada, facilitando a manutenção e a evolução do sistema.
