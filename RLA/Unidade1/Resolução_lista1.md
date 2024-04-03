<img src="https://drive.google.com/uc?id=1SOzRTjUt7cuBJpSqoK90fcAiKBrnpUJo" width="400">
**Nome**: Gustavo Mendonça de Sousa Meneses <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo
```java
ALGORTIMO verifica_par_impar
DECLARE numero, resto: INTEIRO

INICIO

    // Exibe a mensagem para a entrada de dados
    ESCREVA "Digite um número: "
    
    // armazena a variável numero como dado de entrada
    LEIA numero
    
    // executa as instruções caso a condição "numero >= 0" seja verdadeira
    SE numero >= 0 ENTAO

        // Calcula o resto da divisão de "numero" por 2
        resto <- numero % 2

        // executa a instrução se o resto for igual a 0
        SE resto == 0 ENTAO
            ESCREVA "O número é par!"

        // executa a instrução se o resto não for igual a zero
        SENAO
          ESCREVA "O número é impar!"

        FIM_SE

    // // Executa a instrução caso a variável tenha atribuido valor negativo
    SENAO             
        ESCREVA "O número não é postivo!"

    FIM_SE

FIM
```

#### Tabela de testes (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite seu salário atual:"}}
B --> C[/sal_atual/]
C --> D{sal_atual <= 500}
D --FALSE--> E[sal_reaj = sal_atual * 1.1]
D --TRUE--> F[sal_reaj = sal_atual * 1.2]
E --> G{{O novo salário é, sal_reaj}}
F --> G
G --> H([FIM])
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO ReajusteSalario
DECLARE sal_atual, sal_reaj: REAL

INICIO

    // exibe a mensagem para a entrada de dados
    ESCREVA "Digite seu salário atual:"

    // armazena a variável "sal_atual" como dado de entrada
    LEIA sal_atual

    // Executa instruções caso a condição "sal_atual <= 500" for verdadeira
    SE sal_atual <= 500 ENTAO
        sal_reaj = sal_atual * 1.2

    // executa a instrução caso o salário atual seja superior a R$500
    SENAO
        sal_reaj = sal_atual * 1.1

    FIM_SE

    // Exibe a mensagem relativa ao novo salário estabelecido
    ESCREVA "O novo salário é R$", sal_reaj

FIM
```

#### Tabela de testes (1.0 ponto)

| sal_atual | sal_atual >= 500 |sal_reaj       | saída                   | 
| --        | --               | --            | --                      | 
| 400       | False            | 400*1.2 = 480 | O novo salário é R$ 480 |
| 500       | True             | 500*1.2 = 600 | O novo salário é R$ 600 |
| 600       | True             | 600*1.1 = 660 | O novo salário é R$ 660 |

## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a nota 1:"}}
B --> C[/nota1/]
C --> D{{"Digite a nota 2:"}}
D --> E[/nota2/]
E --> F{nota1 >= 0<br> OU <br>nota2 >= 0}  
F --FALSE--> K{{"A nota deve ser maior que zero!"}}
K --> L([FIM])
F --TRUE--> G["media = (nota1 + nota2)/2"]
G --> H{media >= 7}
H --FALSE--> I{{"O aluno está reprovado!"}}
H --TRUE--> J{{"O aluno está aprovado!"}}
I --> L
J --> L
```

#### Pseudocódigo (1 ponto)

```java
ALGORTIMO SituacaoAluno
DECLARE nota1, nota2, media: REAL

INICIO

    // Mensagem para a entrada de dados na primeira variável
    ESCREVA "Digite a nota 1:"

    // Armazena a variável nota1
    LEIA nota1

    // Mensagem para a entrada de dados na segunda variável
    ESCREVA "Digite a nota 2:"

    // Armazena a variável nota2
    LEIA nota2

    // Executa as instruções caso as condições "nota1 >= 0" e "nota1 >= 0" forem verdadeiras
    SE nota1 >= 0 E nota2 >= 0 ENTAO

        // calcula a média da soma das vatiáveis nota1 e nota2
        media =  (nota1 + nota2)/2

        // executa as instruções caso a condição "media >= 7" seja verdadeira
        SE media >= 7 ENTAO
            ESCREVA "O aluno está aprovado!"

        // executa as instruções caso a média das notas seja menor que 7
        SENAO
            "O aluno está reprovado!"

        FIM_SE

    // executa as instruções caso ambas ou uma das notas seja negativa
    SENAO
        ESCREVA "A nota deve ser maior que zero!"

    FIM_SE

FIM
```

#### Tabela de testes (1 ponto)

| nota1 | nota2 | nota1 >= 0 E nota2 >= 0 | media        | saĩda | 
| --    | --    | --                      | --           | --    | 
| -1    | 0     | False                   |              | A nota deve ser maior que zero! | 
| 0     | 0     | True                    | (0+0)/2 = 0  | O aluno está reprovado!|
| 4     | 8     | True                    | (4+8)/2 = 6  | O aluno está reprovado!|
| 4     | 10    | True                    | (4+10)/2 = 7 | O aluno está aprovado!|

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a sua idade:"}}
B --> C[/idade/]
C --> D{idade < 0}
D --FALSE--> E{idade >= 18}
E --FALSE--> F[anos_apto = 18 - idade]
F --> G{{Faltam, anos_apto, anos para o candidato estar apto!}}
G --> H([FIM])
E --TRUE--> I{{"O candidato está apto a tirar a CNH!"}}
I --> H
D --TRUE--> J{{"A idade deve ser maior que zero!"}}
J --> H 
```

#### Pseudocódigo (1.0 ponto)

```java
ALGORTIMO AptoCNH
DECLARE idade, anos_apto: INTEIRO

INICIO

    // exibe a mensagem para a entrada de dados
    ESCREVA ""Digite a sua idade:"

    // armazena a variável "idade" como dado de entrada
    LEIA idade

    // exibe a mensgem caso a variável seja negativa
    SE idade < 0 ENTAO
        ESCREVA "A idade deve ser maior que zero!"

    // executa as instruções caso a condição "idade < 0" seja falsa
    SENAO

        // exibe a mensagem caso a condição "idade >= 18" seja verdadeira
        SE idade >= 18 ENTAO
            ESCREVA "O candidato está apto a tirar a CNH!"

        // executa as instruções caso a idade do candidado seja inferior a 18 anos
        SENAO

            // calcula o tempo restante para tirar a CNH subtraindo 18 pela idade do candidato
            anos_apto <- 18 - idade

            // exibe uma mensagem informando quantos anos faltam para o candidato tirar a CNH
            ESCREVA "Faltam", anos_apto, "ano(s) para o candidato estar apto!"

        FIM_SE

    FIM_SE

FIM
```

#### Tabela de testes (1.0 ponto)

| idade | idade < 0 | idade >= 18 | anos_apto | saída                                         | 
| --    | --        | --          | --        | --                                            | 
| -1    | True      |             |           |                                               |
| 0     | False     | False       | 18-0 = 18 | Faltam 18 ano(s) para o candidato estar apto! |
| 17    | False     | False       | 18-17 = 1 | Faltam 1 ano(s) para o candidato estar apto!  |
| 18    | False     | True        |           | O candidato está apto a tirar a CNH!          |
