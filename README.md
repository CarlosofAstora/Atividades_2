# Problema 2335 do LeetCode
- O Aluno: Carlos Henrique Carvalho.

- O Problema: Preencher 3 tipos de copos diferentes distribuidos em quantidades diferentes no menor tempo possível. As opções de preenchimento **por segundo** são um único copo de qualquer tipo ou dois copos de tipos **diferentes**. Retornar o número de segundos passados.

- A Solução:
```
   int fillCups(int* amount, int amountSize) {
    int seg = 0;

    while (amount[0] > 0 || amount[1] > 0 || amount[2] > 0) {
        if (amount[0] >= amount[2] && amount[1] >= amount[2]) {
            amount[0]--;
            amount[1]--;
            seg++;
            
        } else if (amount[1] >= amount[0] && amount[2] >= amount[0]) {
            amount[1]--;
            amount[2]--;
            seg++;
            
        } else if (amount[2] >= amount[1] && amount[0] >= amount[1]) {
            amount[2]--;
            amount[0]--;
            seg++;
            
        } 
    }
    return seg;
}
```

- Os Testes: Foram feitos testes utilizando os três vetores fornecidos no problema original: {1,4,2}, {5,4,4} e {5,0,0}. Eu não fui capaz de detectar uma situação em que o código não funcione e o Leetcode não apresentou nenhum erro também.
