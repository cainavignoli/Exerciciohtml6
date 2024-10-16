.

1. Função contarOcorrencias

Função que recebe um array de números e retorna um objeto com a quantidade de vezes que cada número aparece no array.

function contarOcorrencias(arr) {
    let ocorrencias = {};
    for (let num of arr) {
        ocorrencias[num] = (ocorrencias[num] || 0) + 1;
    }
    return ocorrencias;
}

// Exemplo de uso:
let numeros = [1, 2, 2, 3, 3, 3, 4];
console.log(contarOcorrencias(numeros)); // { '1': 1, '2': 2, '3': 3, '4': 1 }

--------------------------------------------------------------------------

2. Função ordenarPorIdade

Função que recebe um array de objetos com nome e idade e retorna o array ordenado pela idade (crescente).

function ordenarPorIdade(pessoas) {
    return pessoas.sort((a, b) => a.idade - b.idade);
}

// Exemplo de uso:
let pessoas = [
    { nome: "João", idade: 25 },
    { nome: "Ana", idade: 20 },
    { nome: "Carlos", idade: 30 }
];
console.log(ordenarPorIdade(pessoas)); // [ { nome: 'Ana', idade: 20 }, { nome: 'João', idade: 25 }, { nome: 'Carlos', idade: 30 } ]

-----------------------------------------------------------------------------------------------

3. Função separarParesImpares

Função que recebe um array de números e retorna dois arrays: um de pares e outro de ímpares.

function separarParesImpares(arr) {
    let pares = [], impares = [];
    for (let num of arr) {
        if (num % 2 === 0) pares.push(num);
        else impares.push(num);
    }
    return { pares, impares };
}

// Exemplo de uso:
let numeros = [1, 2, 3, 4, 5, 6];
console.log(separarParesImpares(numeros)); // { pares: [2, 4, 6], impares: [1, 3, 5] }


------------------------------------------------------------------------------------

4. Função ehPalindromo

Função que verifica se uma string é um palíndromo (lida igual de trás para frente).

function ehPalindromo(str) {
    let normalizada = str.toLowerCase().replace(/\s+/g, '');
    return normalizada === normalizada.split('').reverse().join('');
}

// Exemplo de uso:
console.log(ehPalindromo("arara")); // true
console.log(ehPalindromo("A man a plan a canal Panama")); // true

------------------------------------------------------------------

5. Função somaMatriz

Função que recebe uma matriz (array 2D) e retorna a soma de todos os elementos.

function somaMatriz(matriz) {
    let soma = 0;
    for (let linha of matriz) {
        for (let valor of linha) {
            soma += valor;
        }
    }
    return soma;
}

// Exemplo de uso:
let matriz = [
    [1, 2],
    [3, 4],
    [5, 6]
];
console.log(somaMatriz(matriz)); // 21

--------------------------------------------------------------------------------

6. Função substituirElemento

Função que substitui todas as ocorrências de um valor antigo por um novo valor em um array.

function substituirElemento(arr, valorAntigo, valorNovo) {
    return arr.map(item => item === valorAntigo ? valorNovo : item);
}

// Exemplo de uso:
let array = [1, 2, 2, 3, 2];
console.log(substituirElemento(array, 2, 99)); // [1, 99, 99, 3, 99]

7. Função multiplicarMatrizes

Função que recebe duas matrizes e retorna o resultado da multiplicação delas.

function multiplicarMatrizes(A, B) {
    let resultado = [];
    for (let i = 0; i < A.length; i++) {
        resultado[i] = [];
        for (let j = 0; j < B[0].length; j++) {
            let soma = 0;
            for (let k = 0; k < A[0].length; k++) {
                soma += A[i][k] * B[k][j];
            }
            resultado[i][j] = soma;
        }
    }
    return resultado;
}

// Exemplo de uso:
let matrizA = [
    [1, 2],
    [3, 4]
];
let matrizB = [
    [5, 6],
    [7, 8]
];
console.log(multiplicarMatrizes(matrizA, matrizB)); // [[19, 22], [43, 50]]
