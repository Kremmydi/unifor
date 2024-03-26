# UNIFOR
**Nome**: Gustavo Mendonça <br>
**Disciplina**: Raciocínio lógico algorítmico

 ## Lista de exercícios

### Exercício 01 (2.5 pontos)
Calcule a média de quatro números inteiros dados.

#### FLUXOGRAMA
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite quatro numeros inteiros}}
B --> C[/N1, N2, N3, N4/]
C --> D[M = N1 + N2 + N3 + N4 / 4]
D --> E{{"A media desses quatro numeros é: " M}}
E --> F([FIM])



```

#### PSEUDOCODIGO

```
ALGORITMO media
DECLARE N1, N2, N3, N4 INTEIROS
INICIO
ESCREVA "Digite quatro numeros inteiros: "
LEIA N1, N2, N3, N4
M = N1 + N2 + N3 + N4 / 4 
	ESCREVA "A media desses quatro numeros é: ", M
FIM


```

#### Teste de mesa (0.5 ponto)

| N1 | N2 | N3 | N4 | M | SAIDA | 
|      --      |      --      |      --      |      --      |      --      |      --      | 
| 2     | 4       | 6    |  8     | 5    |      Média = 5      |
| 1   | 3          | 5        | 7 | 4  |      Média = 4      |

### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### FLUXOGRAMA
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite uma temperatura em celcius: }}
B --> C[/  C , F  /]
C --> D[F = 9 / 5 * C + 32]
D --> E{{"A temperatura em fahrenheit é: ", F}}
E --> F([FIM])

```

#### PSEUDOCODIGO


```
ALGORITMO temperatura
DECLARE C, F REAIS
INICIO
ESCREVA "Digite uma temperatura em celcius: "
LEIA C
F = 9 / 5 * C + 32 ENTAO
	ESCREVA "A temperatura em fahrenheit é: ", F
FIM




```

#### Teste de mesa (0.5 ponto)

|C | F = 9 / 5 * C + 32 | F | 
|      --      |      --      |      --      |    
| 30     |   F = 9 / 5 * 30 + 32      | 86   |  
| 60   |  F = 9 / 5 * 60 + 32          | 140       | 



### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Operações válidas: 1(soma), 2(subtração), 3(multiplicação) e 4(divisão)"}}
B --> C{{Digite uma operação:}}
C --> D[/op/]
D --> E{{Digite um número:}}
E --> F[/num1/]
F --> G{{Digite outro número:}}
G --> H[/num2/]
H --> I{op == 1}
I --FALSE--> J{op == 2}
J --FALSE--> L{op == 3}
L --FALSE--> O{op == 4}
O --FALSE--> Q{{Operação inválida!}}
Q --> R([FIM])
I --TRUE--> M[res = num1 + num2]
M --> S{{num1, + , num2, =, res}}
J --TRUE--> K[res = num1 - num2]
K --> T{{num1, - , num2, =, res}}
L --TRUE--> N[res = num1 * num2]
N --> U{{num1, * , num2, =, res}}
O --TRUE--> P{num2 != 0}
P --FALSE--> X{{Impossível dividir!}}
P --TRUE--> Z[res = num1 / num2]
Z --> V{num1, / , num2, =, res}
X --> R
S --> R
T --> R
U --> R
V --> R
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORITMO CalculadoraSimples
DECLARE op: INTEIRO; num1,num2: REAL
INICIO
  ESCREVA "Operações válidas: 1(soma), 2(subtração), 3(multiplicação) e 4(divisão)"
  ESCREVA "Digite uma operação:"
  LEIA op
  ESCREVA "Digite um número:"
  LEIA num1
  ESCREVA "Digite outro número:"
  LEIA num2
  ESCOLHA
    CASO op == 1
      res = num1 + num2
      ESCREVA num1, "+", num2, "=", res
    CASO op == 2
      res = num1 - num2
      ESCREVA num1, "-", num2, "=", res
    CASO op == 3
      res = num1 * num2
      ESCREVA num1, "*", num2, "=", res
    CASO op == 4
      SE num2 != 0 ENTAO
        res = num1 / num2
        ESCREVA num1, "/", num2, "=", res
      SENAO
        ESCREVA "Impossível dividir!"
      FIM_SE
  SENAO
    ESCREVA "Operação inválida!"
  FIM_ESCOLHA
FIM
```

#### Teste de mesa (0.5 ponto)

| num1 | num2 | op | num2 != 0 | res | saída               | 
| --   | --   | -- | --        | --  | --                  |
| 1    | 0    | 1  |           | 1   | 1 + 0 = 1           |
| 1    | 0    | 2  |           | 1   | 1 - 0 = 1           |
| 1    | 0    | 3  |           | 0   | 1 * 0 = 0           |
| 1    | 0    | 4  | False     |     | Impossível dividir! |
| 1    | 2    | 4  | True      | 0.5 | 1 / 2 = 0,5         |
| 1    | 2    | 5  |           |     | Operação inválida!  |

### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a idade do aluno:"}}
B --> C[/idade/]
C --> D{idade >=5 <br>E <br>idade <= 7}
D --FALSE--> F{idade >=8 <br>E <br>idade <= 10}
F --FALSE--> G{idade >=11 <br>E <br>idade <= 13}
G --FALSE--> H{idade >=14 <br>E <br>idade <= 17}
H --FALSE--> I{idade >=18}
I --FALSE--> P{{"Digite uma idade válida!"}}
P --> Z([FIM])
F --TRUE--> K{{"Infantial A"}}
G --TRUE--> L{{Infantial B}}
H --TRUE--> M{{Infantial C}}
I --TRUE--> N{{Adulto}}
K --> Z
L --> Z
M --> Z
N --> Z
```

#### Pseudocódigo (1.0 ponto)

```
ALGORTIMO ClassificaCategoria
DECLARE idade: INTEIRO
INICIO
  ESCREVA "Digite a idade do aluno:"
  LEIA idade
  ESCOLHA 
    CASO idade >=8 E idade <= 10
      ESCREVA "Infantial A"
    CASO idade >=11 E idade <= 13
      ESCREVA "Infantial B"
    CASO idade >=14 E idade <= 17
      ESCREVA "Infantial C"
    CASO idade >=18
      ESCREVA "Adulto"
  SENAO
    ESCREVA "Digite uma idade válida!"
  FIM_ESCOLHA
FIM
```

#### Teste de mesa (0.5 ponto)

| idade | idade >=8 E idade <= 10 | idade >=11 E idade <= 13 | idade >=14 E idade <= 17 | idade >=18 | saída                       | 
| --    | --                      | --                       | --                       | --         | --                          |
| 4     | False                   | False                    | False                    | False      | Digite uma idade válida!    |
| -4    | False                   | False                    | False                    | False      | Digite uma idade válida!    |
| 8     | True                    | False                    | False                    | False      | Infantial A                 |
| 11    | False                   | True                     | False                    | False      | Infantial B                 |
| 17    | False                   | False                    | True                     | False      | Infantial C                 |
| 21    | False                   | False                    | False                    | True       | Adulto                      |



