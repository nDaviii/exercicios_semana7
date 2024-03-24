# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let x = 17
let y = 5
let z = 8

resultadoBooleano =  (x < y) && (z > x) || (x - y > z)
console.log(resultadoBooleano)

const listaDeNumeros = [1, 2, 3, 4, 5];
let soma = 0;

for (let i = 0; i < listaDeNumeros.length; i++) {
  soma += listaDeNumeros[i];
}

console.log("A soma dos números é:", soma);

```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime o resultado `false`, calcula a soma dos números de 1 a 5 e imprime o resultado no console.

<b>B) O código avalia a expressão booleana, imprime o resultado `true`, calcula a soma dos números de 1 a 5 e imprime o resultado no console.</b>

C) O código avalia a expressão booleana, imprime o resultado `true` e verifica se o número 5 está presente na lista de números.

D) O código avalia a expressão booleana, imprime o resultado `false` e ordena a lista de números em ordem crescente.

<b>Alternativa correta: b)</b>
______

**2)** Analise as funções calcularOrcamento() e calcularOrcamento2(). Num cenário em que a lista gastos fosse incializada como var gastos = [3600, 950, 620, 38] em ambas funções.

```javascript
//Versão 1 da função que calcula orçamento
function calculaOrcamento(){

    var gastos = [1800, 950, 620, 38];
    var totalGastos = gastos[0];
    var salario = 3500;
    var saldo = 0; 
    var statusSaldo =  'positivo';
    var i = 1;

    do{
        totalGastos += gastos[i];
        i++;
    } while(salario >= totalGastos && i<gastos.length)
    
    saldo = salario - totalGastos;

    if (saldo < 0 ){
        statusSaldo = 'negativo';
    } 
    console.log (`Seu saldo é ${statusSaldo} de ${saldo}. `);
}
```

```javascript
//Versão 2 da função que calcula orçamento
function calculaOrcamento2(){

    var gastos = [1800, 950, 620, 38];
    var totalGastos = gastos[0];
    var salario = 3500;
    var statusSaldo =  'positivo';
    var saldo = 0;
    var i = 1;

    while(salario >= totalGastos && i<gastos.length){
        totalGastos += gastos[i];
        i++;
    }

    saldo = salario - totalGastos;
    if (saldo < 0 ){
        statusSaldo = 'negativo';
    } 
    console.log (`Seu saldo é ${statusSaldo} de ${saldo}. `);
}
```

Escolha a opção que responde corretamente qual seria a saída após a execução de cada função:

A) As funções calcularOrcamento() e calcularOrcamento2() teriam a mesma saída: 'Seu saldo é negativo de -1050.'

<b>B) A saída de calcularOrcamento() seria: 'Seu saldo é negativo de -1050.' e a de calcularOrcamento2() seria: 'Seu saldo é negativo de -100.'</b>

C) A saída de calcularOrcamento() seria: 'Seu saldo é negativo de -100.' e a de calcularOrcamento2() seria: 'Seu saldo é negativo de -1050.'

D) As funções calcularOrcamento() e calcularOrcamento2() teriam a mesma saída: 'Seu saldo é negativo de -100.'

<b>Alternativa correta: b)</b>
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const numero = 10;

if (numero % 2 === 0) {
  console.log("O número é par!");
} else if (numero % 3 === 0) {
  console.log("O número é divisível por 3!");
} else {
  console.log("O número é ímpar e não é divisível por 3!");
}
```

 Qual das seguintes alternativas é a descrição mais precisa do que o código faz?


A) O código verifica se o número é divisível por 3 e, se for, exibe a mensagem "O número é divisível por 3!".

B) O código verifica se o número é par ou ímpar. Se for par, exibe a mensagem "O número é par!". Se for ímpar, exibe a mensagem "O número é ímpar!".

C) O código verifica se o número é par, ímpar ou divisível por 3. Se for par, exibe a mensagem "O número é par!". Se for divisível por 3, exibe a mensagem "O número é divisível por 3!". Se for ímpar, exibe a mensagem "O número é ímpar e não é divisível por 3!".

<b>D) O código verifica se o número é par, se é divisível por 3 ou se é ímpar. Se for par, exibe a mensagem "O número é par!". Se for divisível por 3 (e não for par), exibe a mensagem "O número é divisível por 3!". Se for ímpar (e não for divisível por 3), exibe a mensagem "O número é ímpar e não é divisível por 3!".</b>

<b>Alternativa correta: d)</b>
______

**4)** Qual será o resultado impresso no console após a execução desse código?
```javascript
//EX04
var saldo = 1000;
var limiteCredito = 500;
var valorCompras = [200, 800, 300, 400, 600];

for (var i = 0; i < valorCompras.length; i++) {
    var valorCompra = valorCompras[i];

    if (valorCompra <= saldo) {
        console.log("Compra " + (i+1) + " aprovada. Saldo restante: " + (saldo - valorCompra));
        saldo -= valorCompra;
    } else if (valorCompra <= saldo + limiteCredito) {
        console.log("Compra " + (i+1) + " aprovada com limite de crédito. Saldo restante: " + ((saldo + limiteCredito) - valorCompra));
        saldo = 0;
        limiteCredito -= (valorCompra - saldo);
    } else {
        console.log("Compra " + (i+1) + " negada. Saldo insuficiente e limite de crédito excedido.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada com limite de crédito. Saldo restante: 700

Compra 3 aprovada. Saldo restante: 400

Compra 4 aprovada com limite de crédito. Saldo restante: 0

Compra 5 aprovada. Saldo restante: -200


B)
Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada com limite de crédito. Saldo restante: 700

Compra 3 aprovada. Saldo restante: 200

Compra 4 negada. Saldo insuficiente e limite de crédito excedido.

Compra 5 negada. Saldo insuficiente e limite de crédito excedido.


C)
Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada com limite de crédito. Saldo restante: 700

Compra 3 aprovada. Saldo restante: 400

Compra 4 negada. Saldo insuficiente e limite de crédito excedido.


<b>D)

Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada. Saldo restante: 0

Compra 3 aprovada com limite de crédito. Saldo restante: 200

Compra 4 negada. Saldo insuficiente e limite de crédito excedido.

Compra 5 negada. Saldo insuficiente e limite de crédito excedido.</b>

<b>Alternativa correta: d)</b>
______

**5)** Qual é o principal ciclo de vida de um jogo em Phaser.js?

Escolha a opção que responde corretamente:

A) Setup -> Update -> Draw

<b>B) Preload -> Create -> Update</b>

C) Load -> Initialize -> Render

D) Begin -> Play -> End

<b>Alternativa correta: b)</b>
______

**6)** Qual é o objetivo principal do módulo Arcade Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Renderizar gráficos 3D para jogos em HTML5.

<b>B) Simular interações físicas realistas, como colisões e movimentos, em jogos 2D.</b>

C) Criar efeitos de áudio para melhorar a experiência do usuário em jogos.

D) Gerenciar a lógica do jogo e a sincronização de eventos em jogos multiplayer.

<b>Alternativa correta: b)</b>

______

# Questões dissertativas

**7)** Implemente o pseudocódigo para o algoritmo representado no fluxograma da imagem.
![Uma imagem](assets/image.png)
______

```
idade <- entrada('insira sua idade')

se idade < 16:
  imprima('Não pode votar!')
senão, se 16 >= idade > 18 ou idade > 70 ou analfabeto = true: //acrescenta de além do pseudocódigo somente o fator de que o voto é facultativo também, em caso de idade maior que 70 anos e analfabetismo
  imprima('Pode votar! O voto é facultativo')
senão:
  imprima('O voto é obrigatório!')

```

**8)** Considere a implementação da classe base FormaGeometrica em um sistema de modelagem de formas geométricas. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Retangulo e Circulo, que herdam da classe FormaGeometrica, adicionando atributos específicos e métodos para calcular a área de um retângulo e de um círculo, respectivamente.

```
Classe FormaGeometrica:
    Atributos:
        - cor  # Cor da forma geométrica

    Método Construtor(cor):
        # define o valor do atributo cor com o valor passado como parâmetro
        DefineCor(cor)

    Método CalcularArea():
        # implementação genérica para cálculo de área, a ser sobrescrita pelas subclasses.

Classe Retangulo herdaDe FormaGeometrica:
    Atributos: # propriedades do retângulo
        - base  
        - altura  
        - area  

    Método Construtor(cor, base, altura):
        # chama o construtor da classe pai para definir a cor
        ChamarConstrutorDaClassePai(cor)

        # define os valores dos atributos base e altura
        esse.base = base
        esse.altura = altura

    Método CalcularArea():
        # calcula a área do retângulo multiplicando a base pela altura
        esse.area = base x altura

Classe Circulo herdaDe FormaGeometrica:
    Atributos:
        - raio  # raio do círculo
        - centro  # centro do círculo
        - area  # área do círculo

    Método Construtor(cor, raio):
        # chama o construtor da classe pai para definir a cor
        ChamarConstrutorDaClassePai(cor)

        # define o valor do atributo raio
        esse.raio = raio

    Método CalcularArea():
        # calcula a área do círculo utilizando a fórmula πr²
        esse.area = pi x raio²

```

______

**9)** Você foi contratado(a) como estagiário(a) da Tesla e está participando do desenvolvimento de um programa para simular o desempenho de um carro elétrico em uma corrida. Seu objetivo é determinar em quantos minutos o carro levará para completar uma determinada distância, levando em consideração uma velocidade inicial e uma taxa de aceleração constante. No entanto, você deseja garantir que o carro não exceda uma velocidade máxima nem que a corrida demore mais do que um tempo máximo. Implemente a lógica dessa simulação em pseudocódigo.

```

# faz a entrada das variáveis
Velocidade0 <- entrada("Velocidade inicial: ")
Aceleracao <- entrada("Taxa de aceleração: ")
Distancia <- entrada("Distância da corrida: ")
VelocidadeMax <- entrada("Velocidade máxima permitida: ")
TempoMax <- entrada("Tempo máximo em minutos permitido para a corrida: ")

# converter o tempo máximo de minutos pra segundos (fica melhor pro contador)
TempoMaxSeg <- TempoMax * 60

# define as variáveis de tempo e velocidade e inicializa o tempo no 0 e a velocidade na velocidade inicial coletada
Tempo <- 0
Velocidade <- Velocidade0

# iteração para simular o desempenho do carro até a distância ser alcançada ou o tempo máximo ser excedido
enquanto Distancia > 0 e Tempo < TempoMaxSeg
    # calcula a nova velocidade do carro após o tempo que passou
    Velocidade <- Velocidade + Aceleracao * (Tempo / 60)
    
    # checa a nova velocidade excede a velocidade máxima permitida
    se Velocidade > VelocidadeMax
        Velocidade <- VelocidadeMax  # limita a velocidade à velocidade máxima
        
    # calcula a distância percorrida no intervalo de tempo, utilizando a média das velocidades
    DistanciaPercorrida <- (VelocidadeMax + Velocidade0) * Tempo / 2
    
    # verifica se a distância percorrida é maior que a distância total da corrida
    se DistanciaPercorrida > Distancia:
        Distancia <- 0  # O carro alcançou ou ultrapassou a distância total:
    senão:
        Distancia <- Distancia - DistanciaPercorrida  # Reduzir a distância restante
        
    Tempo <- Tempo + 1  # Aumentar o tempo em 1 segundo

# checa o resultado da simulação
se Distancia <= 0:
    print("O carro completou a corrida da simulação em ", Tempo / 60 # divide por 60 pra converter de volta pra minutos, " minutos.")
senão:
    print("O carro não conseguiu completar a corrida dentro do tempo máximo permitido.") # o tempo chegou no tempo máx e a distância não foi percorrida

```


______

**10)** Uma matriz é uma coleção bidimensional de elementos, organizados em linhas e colunas. A seguir, é fornecida a implementação da função SomaDeMatrizes(matrizA, matrizB), que calcula a soma de duas matrizes. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação de duas matrizes.

```
Função SomaDeMatrizes(matrizA, matrizB):
    # verifica se as duas matrizes têm o mesmo número de linhas e colunas
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."
    Senão:
        linhas <- tamanho(matrizA)
        colunas <- tamanho(matrizA[0]) # Considerando que todas as linhas têm o mesmo número de colunas
        matrizResultado <- novaMatriz(linhas, colunas)

        # iteração para percorrer cada elemento das matrizes e calcular a soma
        Para i de 0 até linhas-1 faça:
            Para j de 0 até colunas-1 faça:
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]

        Retornar matrizResultado

# exemplo de uso da função
matrizA <- [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
matrizB <- [[9, 8, 7], [6, 5, 4], [3, 2, 1]]

matrizSoma <- SomaDeMatrizes(matrizA, matrizB)
Escrever("Soma das matrizes:")
ImprimirMatriz(matrizSoma)



# função para criar uma nova matriz com dimensões especificadas
função criarMatriz(linhas, colunas):
    matriz <- novaMatriz(linhas)
    para i de 0 até linhas-1 faça:
        matriz[i] <- novaMatriz(colunas).preencher(0)
    retornar matriz

função multiplicacaoDeMatrizes(matrizA, matrizB):
    # verifica se o número de colunas de matrizA é igual ao número de linhas de matrizB
    se tamanho(matrizA[0]) ≠ tamanho(matrizB) então:
        retornar "as matrizes não podem ser multiplicadas. o número de colunas de matrizA não é igual ao número de linhas de matrizB."
    senão:
        linhasA <- tamanho(matrizA)
        colunasA <- tamanho(matrizA[0])
        colunasB <- tamanho(matrizB[0])
        matrizResultado <- criarMatriz(linhasA, colunasB)

        # iteração do tipo for para percorrer cada elemento da matriz resultado
        para i de 0 até linhasA-1 faça:
            para j de 0 até colunasB-1 faça:
                soma <- 0
                # variáveis no escopo local da função para armazenar os elementos das matrizes
                elemento_matrizA <- matrizA[i]
                elemento_matrizB <- matrizB[0]
                # iteração para multiplicar e somar os elementos correspondentes das matrizes A e B
                para k de 0 até colunasA-1 faça:
                    soma <- soma + (elemento_matrizA[k] * elemento_matrizB[j])
                    elemento_matrizB <- matrizB[k + 1]  # avançar para o próximo elemento da coluna de matrizB
                matrizResultado[i][j] <- soma

        retornar matrizResultado
