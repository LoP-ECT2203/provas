# Prova I - 2017.2 - Turma 01

## Questão 1
(3,0 Pontos) Você foi convidado pela Federação Potiguar de Futebol para desenvolver um novo software para contabilizar as estatísticas do campeonato estadual. Inicialmente, para testar seus conhecimentos, a federação local solicitou o desenvolvimento de um programa para ler uma seqüência CONHECIDA de resultados de um time de futebol qualquer para mostrar aproveitamento do time (em percentual).
Considere que a entrada de dados é formada pelas seguintes informações: um inteiro positivo n (número de partidas disputadas) e uma seqüência de n pares de números inteiros não negativos GP (gols a favor) e GC (gols contra) correspondendo aos resultados das n partidas. Para cada partida, o seu programa deve contabilizar 1 ponto para empate (GP = GC), 3 pontos para vitória (GP > GC) e 0 pontos para derrota (GP < GC). O aproveitamento (a) de um time é a relação entre os pontos ganhos (g) e os pontos totais possíveis, n vezes 3. A fórmula do aproveitamento é dada a seguir:

a = (g / (n*3) ) * 100

```javascript
n = lerInteiro("Entre com a quantidade de partidadas:");
cont = 0;
pontos = 0;
gp = 0;
gc = 0;
while ( cont < n){
    gp = lerInteiro("Entre com os gols a favor: ");
    gc = lerInteiro("Entre com os gols contra: ");
    if (gp > gc)
        pontos = pontos + 3;
    if (gp == gc)
        pontos++;
    cont++;
}
aproveitamento = (pontos/(n*3))*100;
escreva(aproveitamento+"%");

```

Ver: http://lop.ect.ufrn.br/questao/59badc372033dc5ce6bb83bb

## Questão 2

(1,0 Ponto) Escreva um programa para ler as coordenadas de dois pontos em um plano, P1(x1, y1) e P2(x2,y2) nesta ordem. Calcular e mostrar a distância euclidiana entre estes dois pontos.

```javascript
x1 = lerReal("Entre com x1:");
y1 = lerReal("Entre com y1:");
x2 = lerReal("Entre com x2:");
y2 = lerReal("Entre com y2:");

d = Math.sqrt(Math.pow(x2 - x1,2) + Math.pow(y2 - y1,2));

escreva(d);
```

Ver: http://lop.ect.ufrn.br/questao/59bb27828cbf605cecda4f8e

## Questão 3

(2,0 Pontos) Escreva um programa para calcular o valor da conta de água para a empresa TEMOSAGUA. O valor da conta varia de acordo com o tipo de consumidor, se residencial, industrial ou comercial, de acordo com as seguintes regras:

* Residencial: R$ 5.00 de taxa mais R$ 0.05 por metros cúbicos gastos;
* Comercial: R$ 500.00 para consumo até 80 metros cúbicos e mais R$ 0.10 por metros cúbicos gastos acima dos 80 metros cúbicos;
* Industrial: R$ 800.00 para os primeiros 100 metros cúbicos e mais R$ 0.04 por metros cúbicos gastos acima dos 100 metros cúbicos;

Seu programa deve solicitar ao usuário o tipo de conta do usuário, utilize 1 para Residencial, 2 para Comercial e 3 para Industrial, e em seguida o consumo do cliente em metros cúbicos. Como resultado, seu programa deve informar o valor da conta do cliente.

```javascript
tipo = lerInteiro("Entre com o tipo de conta: ");
consumo = lerReal("Entre com o consumo:");
valorConta = 0;
if ( tipo == 1 ) {
    valorConta = 5 + 0.05 * consumo;
}
else if (tipo == 2 ) {
    if (consumo <= 80 )
        valorConta = 500;
    else
        valorConta = 500 + 0.1*(consumo-80);
}
else if (tipo == 3 ){
    if (consumo <= 100 )
        valorConta = 800;
    else
        valorConta = 800 + 0.04*(consumo-100);
}
escreva(valorConta)
```

Ver: http://lop.ect.ufrn.br/questao/59bde0c30da65738ad6b38fb

## Questão 4
(1,0 Ponto) Escreva um programa para receber vários números inteiros positivos e contar quantos são ímpares. O programa deve parar quando o usuário digitar o número 0.

```javascript
n = lerInteiro("Entre com um número.");
contImpares = 0;
while(n != 0) {
    if (n % 2 == 1)
        contImpares++
    n = lerInteiro("Entre com um número.");    
}
escreva(contImpares)
```

Ver: http://lop.ect.ufrn.br/questao/59bdebb0e228af38d3ff3950

## Questão 5

(3,0 Pontos) Faça um programa para calcular o volume (Vc) de vários cones. O programa deve ler o tamanho do raio ( r ) e a altura ( h ) de cada cone, não pode permitir valores negativos e nem valores nulos. Caso a entrada esteja incoerente, o usuário deve digitar novamente até que um valor válido seja fornecido. O programa deve validar r e h individualmente. Depois que o programa realizar o cálculo do volume, o programa deve mostrar o volume e perguntar ao usuário se deseja calcular um novo volume, se o usuário digitar "n" o programa é finalizado.
Observações: Primeiro leia o raio depois a altura; Use pi = 3.14; Use "\n" no final da apresentação de cada volume.


```javascript
resposta = "s";
pi = 3.14
while(resposta != "n") {
    r = lerReal("Entre com o raio");
    while (r <= 0) {
        r = lerReal("Entre com o raio");
    }
    h = lerReal("Enrre com a altura:");
    while(h <= 0){
        h = lerReal("Enrre com a altura:");
    }
    volume = (pi*r*r*h)/3;
    escreva(volume+'\n')
    resposta = lerTexto("Deseja ler calcular um novo volume? ('s' - sim / 'n' - não)")

}
```

Ver: http://lop.ect.ufrn.br/questao/59bdf2df0da65738ad6b3905
