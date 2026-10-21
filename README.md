# Exercício 4 (E4) - Análise Sintática com Bison

Considere a linguagem de expressões aritméticas do exercício E1,
com números inteiros e reais
(com '.') e os operadores aritméticos ```+  -  *  e  / ```,
e a função *yylex* implementada no exercício E1.

Considere a gramática G = (N,T,P,S), com N = {E}, S = E,
T = {num, +, -, *, /}, sendo os operadores aritméticos
associativos à esquerda,
e com * e / com precedência maior que + e -.

```
P:
E ::= E + E | E - E | E * E | E / E | num
```


## Instruções para Configuração do Repositório da Equipe

- [Leia com atenção!](./instructions.md)

---

## Descrição Geral

O programa recebe uma expressão aritmética digitada na entrada padrão, 
apenas uma expressão por linha, 
e mostra, na saída padrão, uma mensagem:
"expressão sem erro sintático"
ou 
"expressão com erro sintático".
Se houver erro léxico, ele será reportado como erro sintático.

###  Exemplos

#### Entrada válida

- Entrada:

```90 * 100 / 18.0 - 48 + 77```

- Saída esperada (seguir o padrão):

```
expressão sem erro sintático.
```

#### Entrada com dois operadores sem operando entre eles.

- Entrada inválida:

```90 * 100 / 18.0 - + 77```

- Saída esperada:

```
expressão com erro sintático.
```

#### Entrada com erro léxico

- Entrada inválida:

```90 ! 100 / 18.0 ```

- Saída esperada:

```
expressão com erro sintático.
```

### Testes

Considerar, no mínimo os cenários indicados em \tests\cenarios.md.
Os arquivos de teste devem ser texto simples. Os arquivos de entrada, com uma linha contendo uma expressão aritmética,
devem ter extensão '.in'; os arquivos com a saída esperada (oráculo) devem ter extensão '.ora' e seguir o formato de
saída ilustrado nos exemplos anteriores.

- Definir uma função main() que chama a função yyparse().

### Testes

Colocar mais testes na pasta \tests para os cenários indicados em \tests\cenarios.md

### Entrega

A entrega do exercício E4 deve ser feita apenas via GitHub,
com o código fonte de sua implementação e arquivos indicados a seguir.

Arquivos:
- ./README-E4.md, com nomes dos membros da equipe (primeiras linhas, como comentário e orientações para compilar, executar e testar seu código.
- ./makefile, com opções 'compile' e 'test'
- ./<arquivos com código fonte>
- Pasta ./'tests', contendo seus testes I/O para os cenários indicados em \tests\cenarios.md

