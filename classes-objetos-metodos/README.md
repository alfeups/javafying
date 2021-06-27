# Entendendo Classe, Objetos e Métodos

<p> Este artigo foi criado a partir da obra de *Java - Como programar -10th Ed*, do autor Deitel.</p><br/>

<p> Para entender os conceitos abordados, o autor utiliza a produção de uma carro como exemplo.</p>

## O carro como um objeto

<p>Para facilitar a compreensão, irei ordenar em ordem cronológica as ideias:</p>

<p>1- Deseja-se guiar um carro e fazê-lo andar mais rápido pisando no *pedal* acelerador.</p>
<p>1.1- O carro é projetado em desenhos de engenharia, como acontece em plantas de casas.</p>
<p>1.2- Ao projetar o carro o mecanismo de acelerar e freiar foram *ocultos* ao motorista, então, o mesmo não irá se preocupar como os mecanismos que acontecem.</p>
<p>1.3- Após ser projetado, o carro é construído.</p>
<p>1.4- Para que o carro seja acelerado, é necessário um motorista.</p>

<p> Pensando agora na elaboração do código, teríamos: </p>

```Public class Carro {}``` 
<p>Digamos que o projeto do desenho foi nomeado mas ainda está vázio. Para tornarmos essa classe em um objeto precisamos preenche-la com os atributos do objeto(fabricante, marca, modelo, cor, velocidadeMaxima) and so on. </p>

 ```
    Public class Carro {
        private String fabricante;
        private String marca;
        private String modelo;
        private String cor;
        private Int velocidadeMaxima;
    }
``` 

## Classes e métodos

<p> Uma <b>classe</b> é similar em termos do conceito aos desenhos de engenharia de um carro, que armazenam o projeto de um pedal de
acelerador, freio e volante.</p>

<p> No entanto, para realizar a ação de *acelerar, freiar, guiar* é preciso usar <b>métodos</b>. </p>

<p> "O <b>método</b> armazena as declarações do programa que, na verdade, executam as tarefas; além disso, ele oculta essas declarações do usuário, assim como o pedal do acelerador de um carro oculta do motorista os mecanismos para fazer o veículo ir mais rápido."</p>

<p> Para exemplificar, pensemos numa conta bancária com funções simples como consultar saldo, depótiso e saque:


 ```
    Public class Conta {
        protected int numero;
        protected String nomeCliente;
        protected double saldo;

        public double getSaldo()
        {
            return this.getSaldo;
        }

        void depositar(double quantidade)
        {
            this.saldo += quantidade;
        }

        void sacar(double quantidade)
        {
            double novoSaldo = this.saldo - quantidade;
            this.saldo = novoSaldo;
        }
    }
 ```


REFERENCES

Deitel, P. J., & Deitel, H. M. (2017). Java: How to Program, Late Objects (p. 1248). New York City, NY: Pearson.

Prof. Fernando de Siqueira - Programação Orientada a Objetos. Disponível em:https://sites.google.com/site/anhangueraniteroipoo/aulas/aula-1---orientacao-a-objetos