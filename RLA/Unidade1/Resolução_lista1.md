# UNIFOR
**Nome**: Gustavo Mendonça <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma 


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
```
1  ALGORTIMO verifica_par_impar
2  DECLARE numero, resto: INTEIRO
3  ESCREVA "Digite um número: "
4  INICIO
4  LEIA numero
5  SE numero >= 0 ENTAO                  // verifica se o inteiro é positivo
6    resto = numero % 2                 // calcula o resto da divisão por 2
7    SE resto == 0 ENTAO                // verifica se o resto é igual a zero
8      ESCREVA "O número é par!"
9    SENAO
10     ESCREVA "O número é impar!"
11   FIM_SE
11  SENAO                                // caso inteiro for negativo (condição linha 5)
12    ESCREVA "O número deve ser postivo!"
13  FIM_SE
13 FIM
```
#### Teste de mesa (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

###  Exercício 02
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um salário:}}
B --> C[\ㅤ Sα ㅤ\]
C --> D{S >= 500}
D --TRUE--> E[Sα * 1.1 = Sβ]
D --FALSE--> F[Sα * 1.2 = Sβ]
E --> G{{Sβ}}
F --> G
G --> H([FIM])
```

#### PSEUDOCODIGO

```mermaid
flowchart TD
ALGORITMO verificar_NOVO SALARIO
DECLARE Sα, Sβ NUMERICOS
ESCREVA "Digite seu salario atual: "
LEIA Sα
SE Sα >= 500 ENTAO
	Sβ = Sα * 1.1
SENAO
	Sβ = Sα * 1.2
ESCREVA "Seu novo salario é: ", Sβ
FIM ALGORITMO
```

#### EXERCÍCIO 03

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite a primeira nota: }}
B --> C[/Nota1/]
A --> D{{Digite a segunda nota: }}
D --> E[/Nota2/]
C --> F[MEDIA == Nota1 + Nota2 / 2]
E --> F
F --> G{MEDIA >= 7}
G --TRUE--> H[O aluno está aprovado com media: MEDIA]
G --FALSE--> I[O aluno está reprovado com media: MEDIA]
H --> J([FIM])
I --> J

```  


#### PSEUDOCÓDIGO

```
ALGORITMO verificar_MEDIA
Declare Nota1, Nota2, MEDIA NUMERICO
ESCREVA "Digite a primeira nota do aluno: "
LEIA Nota1
ESCREVA "Digite a segunda nota do aluno: "
LEIA Nota2
MEDIA = (Nota1 +Nota2) / 2
SE MEDIA >= 7 ENTAO
	ESCREVA "O aluno foi aprovado com média igual: ", MEDIA
SENAO
	ESCREVA "O aluno foi reprovado com médiaa igual: ", MEDIA
FIM ALGORITMO 






```
