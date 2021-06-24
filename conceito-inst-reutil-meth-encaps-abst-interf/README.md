# Instanciar, Reutilizar, Métodos, Encapsulamento, Abstração e Interfaces.

## Instância
<p>"Uma instância de uma classe é um novo objeto criado dessa classe, com o operador new. Instanciar uma classe é criar um novo objeto do mesmo tipo dessa classe. Uma classe somente poderá ser utilizada após ser instanciada."</p>

<p> Utilizando o exemplo do carro, que foi mencionado em "Classes,Objetos e Métodos", teríamos:</p>

```
   Carro carro1 = new Carro();
<classe><objeto>= new <objeto>
```

## Reutilização

<p>"A reutilização de classes existentes ao construir novas classes e programas economiza tempo e esforço. Também ajuda a construir sistemas mais confiáveis e eficientes, porque classes e componentes existentes costumam passar por extensos testes, depuração e ajuste de desempenho."<p>

## Mensagens e chamadas de método

<p>Ao acelerar o carro uma mensagem é enviada para o veículo realizar uma tarefa — ir mais rápido. Da mesma forma, você envia mensagens para um objeto.</p>

<p>Cada mensagem é implementada como uma chamada de método que informa a um método do objeto a maneira de realizar sua tarefa.</p>

<p>"Quando criado um método com a ação de depositar um valor para uma conta bancária, dentro desse método são incluídas as ações que irão retornar algum valor, trabalhar em uma variável ou até mesmo chamar outro método já criado."</p>

```
public class Conta {

	private Double saldo;

	public void setSaldo(Double saldo) {
		this.saldo = saldo;
	}

	public Double getSaldo() {
		return saldo;
	}

	public void depositar(Double valor){
		saldo += valor;
	}

	public void verificaSaldo(){
		System.out.println("Valor do Saldo: "+getSaldo());
	}
}

```

Exemplificando chamar o método e instanciação, temos:

```
public static void main(String[] args) {

	//INSTANCIA A CLASSE
	Conta conta = new Conta();

	//DEFINE UM VALOR DE SALDO
	conta.setSaldo(633.00);

	//DEFINE VALOR PARA DEPOSITAR
	conta.depositar(555.0);

	//RESGATA VALOR
	conta.verificaSaldo();

}

```

## Encapsulamento e ocultamento de informações

<p> A ocultação de informações é esconder, ou ocultar os dados, critério primário para a modularização de sistemas.<p>

<p>Protegendo as informações desta maneira, retiramos a exigência de um conhecimento íntimo do projeto por parte dos clientes</p>

<p> Encapsular significa esconder a implementação dos objetos. O encapsulamento favorece principalmente dois aspectos de um sistema: a manutenção e a evolução.</p>

<p> Considerando um trecho do exemplo da conta bancária, teríamos:</p>

```
public class Conta {

	private Double saldo;

	public void setSaldo(Double saldo) {
		this.saldo = saldo;

```

<p> No entanto é preciso tomar bastante cuidado pois ao tornar algum método privado pode fazer com que ele deixe de ser "callable", ou seja, que seja impossibilidade de chamar o método.</p>

<p> Sem ocultação de informações e encapsulamento seria inviável de se ter abstração, que por sua vez faria com que o código não pudesse ser reutilizado.</p>

<p> O que seria então abstração?</p>

## Abstração
<p>Habilidade de concentrar-se nos aspectos essenciais de um domínio, ignorando características menos importantes ou acidentais. Nesse contexto, objetos são abstrações de entidades existentes no domínio em questão.</p>

## Interfaces
O Java também suporta interfaces — coleções de métodos relacionados que normalmente permitem informar aos objetos o que fazer, mas não como fazer (veremos uma exceção a isso no Java SE 8).</p>

<p> Na analogia do carro, uma interface das capacidades “básicas de dirigir” consistindo em um volante, um pedal de acelerador e um pedal de freio permitiria que um motorista informasse ao carro o que fazer. Depois que você sabe como usar essa interface para virar, acelerar e frear, você pode dirigir muitos tipos de carro, embora os fabricantes possam implementar esses sistemas de forma diferente.</p>

<p> Uma classe implementa zero ou mais interfaces — cada uma das quais pode ter um ou mais métodos —, assim como um carro implementa interfaces separadas para as funções básicas de dirigir, controlar o rádio, controlar os sistemas de aquecimento, ar-condicionado e afins. Da mesma forma que os fabricantes de automóveis implementam os recursos de forma distinta, classes podem implementar métodos de uma interface de maneira diferente.</p>

<p> Por exemplo, um sistema de software pode incluir uma interface de “backup” que ofereça os métodos save e restore. As classes podem implementar esses métodos de modo diferente, dependendo dos tipos de formato em que é feito o backup, como programas, textos, áudios, vídeos etc., além dos tipos de dispositivo em que esses itens serão armazenados.</p>







REFERENCES

Deitel, P. J., & Deitel, H. M. (2017). Java: How to Program, Late Objects (p. 1248). New York City, NY: Pearson.

https://www.devmedia.com.br/conceitos-da-linguagem-java/5341

https://www.devmedia.com.br/trabalhando-com-metodos-em-java/25917