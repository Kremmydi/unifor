# CONTEÚDO PRÁTICO
## Dadas duas variáveis, a e b, implemente e teste um algoritmo para trocar os valores atribuídos a elas.

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite dois números}} 
B --> C[/a , b/]
C --> D[b == c]
D --> E[a == b]
E --> F[c == a]
F --> G{{a , b}}
G --> H([FIM])
```

#### Pseudocódigo
```
1 ALGORITMO TrocaValores
2 DECLARE a , b : inteiro;
3 b ← c
4 a ← b
5 c ← a
6 ESCREVA a , b
7 FIM_ALGORITMO

```
### Questão 2 - Contagem (1 ponto)

Dado um conjunto $n$ de notas de alunos em um exame, implemente e teste um algoritmo para fazer uma contagem $cont$ do número de alunos que foram aprovados no exame. 
Será considerado aprovado o aluno que tirar $nota$ 50 ou maior (no intervalo de 0 a 100).

#### Descrição geral do algoritmo

1. Obter o número de notas $n$ a serem processadas;
2. Inicializar a contagem $cont$ com zero;
3. Enquanto houver notas a serem processadas, fazer repetidamente:
    - obter a próxima nota;
    - se a nota for suficiente para passar no exame ($n ≥ 50$) então adicionar 1 (um) à contagem $cont$;
4. Exibir a contagem $cont$ (número total de aprovações).

#### Fluxograma 01
Fluxograma conforme descrição do algoritmo acima, usando o loop ENQUANTO.

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de alunos: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[\i = 1\]
E --> F{i <= n}
F --FALSE--> W{{Número de alunos aprovados: cont}}
W --> Z([FIM])
F --TRUE--> G{{Digite a nota do aluno, i}}
G --> H[\nota\]
H --> I{"nota >= 50 <br>E <br>nota <=100"}
I --TRUE--> J[\cont =+ 1\]
I --FALSE--> K[\i =+ 1\]
J --> K
K --LOOP--> F
```
#### Pseudocódigo 01 (1 ponto)

```
Algoritimo aprovação
DECLARE N_ver, N_aprov, N_notas, i: Int
	notas: Float
INICIO
N_aprov = 0 
ESCREVA "Digite a quanidade de notas para avaliar"
LEIA N_notas
ENQUANTO N_notas <= 0 REPITA
	ESCREVA "Digite uma quantidade válida"
	LEIA N_notas
PARA N_ver DE 1 ATÉ N_notas FAÇA [PASSO 1]
	ESCREVA "Insira a nota"
	LEIA nota
	SE nota >= 50 E nota <= 100
		N_aprov =+ 1
		N_ver =+ 1
	SENÃO
		N_ver =+ 1
	FIM_SE
FIM_PARA
ESCREVA "A quantidade de notas aprovadas foi", N_aprov
FIM_ALGORÍRIMO
```

### Questão 3 - Soma de um conjunto de números (1 ponto)

Dado um conjunto de $n$ números, implemente e teste um algoritmo para calcular a soma desses números. <br>
Aceite apenas $n$ maior ou igual a zero.

#### Descrição geral do algoritmo

1. Obter a quantidade de números $n$ a serem somados.
2. Inicializar a variável $soma$ com 0 (zero).
3. Enquanto menos do que $n$ números tiverem sido somados, fazer repetidamente:
    - obter o próximo número $i$;
    - calcular a soma atual, adicionando o número $i$ obtido à soma mais recente;
4. Exibir a soma dos $n$ números

#### Fluxograma

```mermaid
flowchart TD
A([INICIO])
A --> C[soma = 0]
C --> D{{Digite o número de elementos do conjunto que você quer somar}}
D --> E[/num_som/]
E --> F{num_som > 0}
F--FALSE--> G{{Digite uma quantidade válida}}
G --> E
G --TRUE--> H{num_som = num_somados}
H --FALSE--> I{{Digite um número}}
I --> J[/num/]
J --> K[soma = soma + num]
K --> L[num_somados =+ 1]
L --> H
H --TRUE--> M{{A valor da soma total é soma}}
M --> N([FIM])
```

#### Pseudocódigo (1 ponto)
```
Algoritmo soma_de_valores
DECLARE num_somados, num_soma: Int
	num, soma: Float
INICIO
soma = 0
ESCREVA "Digite o número de elementos do conjunto que você quer somar"
LEIA num_soma
ENQUANTO num_soma <= 0 FAÇA
	ESCREVA "Digite uma quantidade válida"
	LEIA num_soma
FIM_ENQUANTO
PARA num_somados DE 1 até Num_soma [PASSO 1] FAÇA
	ESCREVA "Digite um número"
	LEIA num
	soma =+ num
FIM_PARA
ESCREVA "O valor da soma total é", soma
FIM_ALGORITMO
```

### Questão 4 - Cálculo de uma série (1 ponto)

Dado um conjunto de $n$ termos da série, implemente e teste um algoritmo para calcular o valor de S, conforme definido abaixo:

$$ S = \frac{1}{2} + \frac{3}{4} + \frac{5}{6} + \frac{7}{8} + \dots $$

#### Descrição geral do algoritmo

1. Obter o número de termos $n$;
2. Inicializar a variável $S$ com 0 (zero).
3. Iterar o valor de $n$ na variável $i$ iniciando com 0 (zero), de acordo com as instruções abaixo:
    - calcular o numerador na variável $numerador$;
    - calcular o denominador  na variável $denominador$;;
    - calcular o termo da série na variável $termo$, onde $termo = numerador/denominador$;
    - adicionar esse termo à variável $S$.
4. Exibir o valor da série $S$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B[S = 0]
B --> D{{Digite a quantidade de termos da série que voce quer somar}}
D --> E[/Num_termo/]
E --> F{Num_termo > 0}
F --FALSE--> G{{Digite uma quantidade válida}}
G --> E
F --TRUE--> H{Num_termo = termo}
H --FALSE--> I[termo =+ 1]
I --> J["S =+ (2 * termo - 1)/(2 * termo)"]
J --> H
H --TRUE--> K{{"O valor da soma de Num_termos termo(s) da série é S"}}
K --> L([FIM])
```

#### Pseudocódigo (1 ponto)

```
Algoritmo soma_da_serie
DECLARE Num_termo, termo: Int
	S: Float
INICIO
S = 0
ESCREVA "Digite a quantidade de termos da série que você quer somar"
LEIA Num_termo // 3 
ENQUANTO Num_termo < 0 FAÇA
	ESCREVA "Digite uma quantidade válida"
	LEIA Num_termo
FIM_ENQUANTO
PARA termo DE 1 ATÉ Num_termo [PASSO 1] FAÇA
	S =+ (2 * termo - 1)/(2 * termo)
FIM_PARA
ESCREVA "O valor da soma de", Num_termo, "termo(s) da série é", S
FIM_ALGORITMO
```


### Questão 5 - Cálculo fatorial (2 pontos)

Dado um número $n$, implemente e teste um algoritmo para calcular o fatorial de $n$ (escrito como $n!$), onde $n ≥ 0$.

#### Descrição geral do algoritmo

1. Obter o número $n$, onde $n \geq 0$;
2. Inicializar a variável $fator$ com 1 (um) para armazenar o resultado do cálculo do fatorial;
3. Iterar o valor de $n$ na variável $i$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Incrementar o valor atual $fator$ multiplicando pelo valor de $i$;
4. Exibir o resultado ($n!$).

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B[fato = 1]
B --> R[n_mult = 0]
R-->C{{Digite o numero do fatorial que voce quer calcular}}
C --> D[/n/]
D --> E{n >= 0}
E --FALSE--> F{{Digite um fatorial válido}}
F --> D
E --TRUE--> G{n = n_mult}
G --FALSE--> H[n_mult =+ 1]
H --> I[fato = fato * n_mult]
I --> G
G --TRUE--> Y{{O valor do fatorial de n é fato}}
Y --> Z([FIM]) 
```
#### Pseudocódigo (2 pontos)

```
Algoritmo fatorial
DECLARE fato, n_mult, n: Int
INICIO
n_mult = 0
ESCREVA "Digite o numero do fatorial que voce quer calcular"
LEIA n
ENQUANTO n < 0 FAÇA
	ESCREVA "Digite um fatorial válido"
	LEIA n
FIM_ENQUANTO
PARA n_mult DE 1 PARA n [PASSO 1] FAÇA
	n_mult =+ 1
	fato = fato * n_mult
FIM_PARA
ESCREVA "O valor do fatorial de", n, "é", fato 
FIM_ALGORITMO
```


### Questão 6 - Geração da sequência de Fibonacci (2 pontos)

Gerar e imprimir os $n$ primeiros termos da sequência de Fibonacci, onde $n ≥ 1$. <br>
Os primeiros termos são: $0, 1, 1, 2, 3, 5, 8, 13, \dots$. Cada termo, além dos dois primeiros, é derivado da soma dos seus dois antecessores mais próximos.

#### Descrição geral do algoritmo

1. Obter o número de termos $n$, onde $n \geq 1$;
2. Inicializar os dois primeiros termos da série nas variável $a$ e $b$ com 0 (zero);
3. Iterar o valor de $n$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Imprimir o termo inicial $a$ (instrução para exibir a sequência ao atualizar a variável $a$);
    - Somar os termos $a$ e $b$ na variável $termo_atual$;
    - Atribuir a variável $a$ o valor da variável $b$;
    - Atribuir a variável $b$ o valor da variável $termo_atual$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Número de termos da série Fibonacci:"}}
B --> C[a = 0]
C --> D[b = 1]
D --> E[[i=1 ATÉ n PASSO 1]]
E --"i > n"--> J([FIM])
E --"i=1,2,...,n"--> F{{a}}
F --> G[termo_atual = a + b]
G --> H[a = b]
H --> I[b = T_atual]
I --LOOP--> E 
```

#### Pseudocódigo (2 pontos)

```
Algoritimo fibonacci
DECLARE a, b, T_atual, n, i: Int
INICIO
a = 0
b = 1
ESCREVA "Digite qual termo de fibonacci você quer calcular"
LEIA TS
ENQUANTO n <= 0 FAÇA
	ESCREVA "Digite um termo válido"
	LEIA n
FIM_ENQUANTO
PARA i DE 1 ATÉ TS [PASSO 1] FAÇA
	ESRCREVA a
	Tmem = a + b
	a = b
	b = T_atual
FIM_PARA
FIM_ALGORITIMO
```

### Questão 7 - Inversão dos dígitos de um número inteiro (2 pontos)

Implemente e teste um algoritmo para inverter a ordem dos dígitos de um número inteiro positivo.

#### Descrição geral do algoritmo

1. Obter o número inteiro positivo $num$ a ser invertido;
2. Inicializar a variável $num \textunderscore inv$ com 0 (zero);
3. Enquanto o número for maior que zero ($num > 0$), faça repetidamente:
    - Calcular o último dígito do número na variável $digito$;
    - Adicionar o dígito ao número invertido $num \textunderscore inv$;
    - Remover o último dígito do número original $num$; 
4. Exibir o número invertido.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número inteiro: }}
B --> C[\num\]
C --> D{num >= 0}
D --TRUE--> G[num_inv = 0]
G --> H{num > 0}
H --FALSE--> Z{{"Número invertido:", numero_inv}}
Z --> W([FIM])
H --TRUE--> I[digito = num % 10]
I --> J[num_inv = num_inv * 10 + digito]
J --> K[numero = numero // 10]
K --LOOP--> H
D --FALSE--> E{{O número deve ser positivo!}}
E --> W
```

#### Pseudocódigo (2 pontos)

```
Algoritimo Inver
DECLARE Num, Num_inv, mem, mem2: Int
INICIO
ESCREVA "Digite o número que voce quer inverter"
LEIA Num
mem2 = Num
ENQUANTO Num <= 9 FAÇA
	ESCREVA "O número precisa ser positivo e ter mais de dois algarismos"
	ESCREVA "Digite o número que voce quer inverter"
FIM_ENQUANTO
ENQUANTO Num > 0 FAÇA
	mem = Num % 10
        Num =// 10
	Num_inv =* 10
	Num_inv =+ mem
FIM_ENQUANTO
ESCREVA "O número", mem2, "após inverter os algarismos é", Num_inv
FIM_ALGORITIMO 
```
