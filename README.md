# MaquinasTuring
 As máquinas de Turing, conceituadas por Alan Turing em 1936, representam um
modelo fundamental para o estudo da computação teórica e da teoria da computabilidade e
são amplamente estudadas por sua capacidade de simular qualquer algoritmo computável.
Uma máquina de Turing é composta por uma fita que serve como memória, dividida em
células consecutivas onde são armazenados símbolos. A cabeça de leitura/escrita percorre
a fita, modificando os símbolos de acordo com um conjunto de regras definidas por uma
função de transição. Enquanto as máquinas de Turing de fita única utilizam uma única
sequência linear de células, as de fita múltipla possuem várias fitas, cada uma com sua
própria cabeça de leitura/escrita, potencialmente aumentando a eficiência da computação
ao separar diferentes tipos de dados e operações entre as fitas.

## LINGUAGENS IMPLEMENTADAS 
1 a) L = {a^i b^j c^k | i, j, k ∈ N e i × j = k}

1 b) L = {a^n b^m c^p d^q | n < m, m̸ = p + q e p > q}

2 a) L = {xyxRyR | x, y ∈ {a, b}∗} (xR é o reverso da cadeia x e yR é o reverso da cadeia y)

2 b) L = {a^i b^j c^k | i, j, k ∈ N e i^j = k}

3 a) Algoritmo de Euclides para o Máximo Divisor Comum

3 b) Fatorial de n

## EXPLICAÇÃO DO ALGORITMOS IMPLEMENTADOS

### 1a
- Verifique se a fita está vazia; se sim, aceite, pois i=j=k=0 é válido.
- Marque o primeiro "a" e mova para o primeiro "b":
- Comece do primeiro "a" não marcado, marque-o (por exemplo, convertendo
"a" para "A") e avance para o primeiro "b" após todos os "a"s.
- Para cada "b", marque "c"s:
- Para cada "b", retroceda para o "A" mais próximo (à esquerda) e, para cada
"a", marque um "c" como "C". Use as transições para mover-se entre "a"s e
"c"s.
- Percorra a fita da esquerda para a direita:
- Se encontrar um "b" não marcado, desmarque os “A”s e volte ao passo 3.
- Se todos os "a"s e "b"s estão marcados e o número adequado de "c"s foi
marcado para cada grupo de "a"s e "b"s, aceite a entrada.
- Caso contrário, se houver "a"s, "b"s ou "c"s não marcados ou marcados
incorretamente, rejeite

![image](https://github.com/user-attachments/assets/18b70f1d-0813-4735-98a7-2f75583b5d0d)

### 1b
- Primeiro é feita a verificação da ordem das letras.
- Então é feito a verificação de que n<m, marcado um "a" como "A" e é
percorrido a fita até o próximo "b" e é marcado como "B". A fita então
percorre para a esquerda até o primeiro "A" que encontrar para poder marcar
um novo "a" e "b". Caso todos os "a" estiverem marcados e sobrar um "b",
continue.
- Então é feito a verificação p>q, que é muito similar a etapa anterior. É
marcado um "c" como "C", é percorrido a fita até o primeiro "d" e o marca
como "D". Se ainda tiver um "c" e não tiver "d", a fita é percorrida até o
espaço em branco e vai para a próxima etapa.
- É percorrido a fita até o início, desmarcando todas as letras.
- É percorridos todos os "a".
- É marcado "b" como "B", percorre até o primeiro "c" ou "d" e é marcado como
"C" ou "D", é voltado a fita até o "B" e é marcado um novo "B" e feito o loop
de "c" ou "d" até o fim da fita.
- Caso a fita esteja já no fim, pode aceitar, se não mova a fita até o fim e
aceite.

![image](https://github.com/user-attachments/assets/a79634fc-fceb-4353-a254-b433603410f2)

### 2a
- A máquina percorre a fita 1 criando para cada elemento da fita uma nova
computação onde ela assume que X seja composto pelos elementos até o elemento atual
em que o cabeçote da máquina se encontra; Para isso a máquina escreve o elemento atual
na fita 2 (fita 2 representará X);
- Assim ao assumir X a máquina entra no mesmo processo para assumir Y
"chutando" que o Y comece no fim de X e termine no elemento atual em que o cabeçote
está posicionado; Para isso a máquina escreve o elemento atual na fita 3 (fita 3
representará Y);
- Para cada "chute" da máquina ocorrerá o teste de se X(e Y) é equivalente a X^r(e
Y^r) quando revertido;
- Para fazer esse teste a máquina vai ler a fita 2 de trás para frente e andar pelo
comprimento da fita 2 checando se os elementos da fita 1 equivalem aos elementos
presente na fita 2 quando lidos de trás para frente(Ou seja, ler a fita 1 da esquerda para
direita e a 2 da direita para esquerda);
- Caso a fita 2 acabe e não houve nenhum erro, ou seja o X e X^r estão corretos,
fazemos o mesmo processo para a fita 3 (Y e Y^r);
- Caso a checagem de Y e Y^r também funcione, chegaremos ao fim da fita 1 e
podemos aceitar.

![image](https://github.com/user-attachments/assets/29d226c6-9b07-45b5-8342-500645bb1348)

### 2b
- Coloca um espaço em branco na fita 2
- É feito a verificação se a = 0 e se tem algum b, se a fita não ter nenhum c, aceite;
- É feito a verificação se a =0 e b =0 e se tiver apenas um c, aceite.
- Caso a fita começa com um a, passamos por todos os “a’s” e marcamos o primeiro
“b”
- Para cada “a” ande a fta 2 para esquerda e a fita 3 para direita, assim passando os
espaços em branco(até o #) da fita 2 para a fita 3
- Quando a fita 1 chegar ao início (>), desmarque o # da fita 2 e volte o cabeçote
para o começo
- Volte o cabeçote da fita 3 para o início, assim movendo a fita 2 para direita e a fita
3 para esquerda, se a fita 3 chegar ao início (>) e ainda ter “b” na fita 1, marque-o, marque a
fita 2 com # na posição atual do cabeçote e volte ao passo 5.
- Caso todos os “b”s já foram marcados, para cada espaço em branco percorrido na
fita 2 marque um “c” como “C”. Caso todos os “c” tenham sido marcados, aceite, caso
contrário, rejeite.

![image](https://github.com/user-attachments/assets/3bd94031-1665-46cf-8d7a-d495d8822975)

### 3a
- A máquina recebe uma sequência de a's e b's (por exemplo: aaabbbbbb) sendo
que o número de "a's" representa no o "n" e os "b's" representam o "m" de Mdc(n,m)
- Gravamos os "a's" na fita 2 e os "b's" na fita 3
- Regredimos por cada fita(apenas a 2 e a 3) ao mesmo tempo para verificar qual
dela é menor, a fita que chegar ao símbolo ">" primeiro é a menor, se as duas
chegarem ao mesmo tempo elas são iguais
- Casos uma das fitas seja menor:
- Voltamos as duas fitas para seu último caractere
- Removemos o número de elementos da fita menor da fita maior
- Caso as duas sejam iguais:
- Voltamos as duas fitas para seu último caractere
- Removemos o número de elementos da fita 2 da fita 3
- Quando a fita 3 não ter mais elementos o resultado estará na fita 2.

  ![image](https://github.com/user-attachments/assets/1fbc75d4-bcda-4888-b95c-32bc8bc989e3)

### 3b
- Passa "a vezes" a fita 2 para a 3, quando ela passar por todos os "a's" ela vai passar
o resultado da fita 3 para fita 2 e então remover um "a" da fita 1, se terminou os "a's"
acaba, se não reinicia o processo.
- Para cada "a" replica os "b's" da segunda fita na terceira.
- Quando já ter passado por todos os "a's":
- Limpa a fita 2;
- Coloca o conteúdo da fita 3 na fita 2;
- Avança por todos os "a's";
- Remove o último "a" da fita 1.
- Caso ainda haja algum "a" fazemos o procedimento novamente.
- Caso o último "a" seja removido e a fita 1 tenha chegado ao início vai para o estado
de aceitação, dando fim ao algoritmo.
- O Resultado é o número de "b's" na segunda fita.

![image](https://github.com/user-attachments/assets/9afbb74e-5a77-42e0-8777-184d6c4479df)
