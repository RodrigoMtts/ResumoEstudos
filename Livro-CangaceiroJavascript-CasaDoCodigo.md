# Javascript - Cangaceiro

## Métodos Javascript

**Object.freeze(objeto ou this):**

Propriedades de objetos congeladas não podem receber novas atribuições

Não congela a propriedades dos objetos que são suas propriedades

**Object.isFrozen(objeto):**

Verifica se um objeto está congelado 

 - retorna: true ou false

**InstaciaDeDate.setDate(diaDoMes):**

Permite alterar a data de um date

**InstaciaDeDate.getTime():**

retornará um número long comuma representação da data

**Object.assign():**

O método Object.assign() é usado para copiar os valores de todas as propriedades próprias  enumeráveis de um ou mais objetos de origem para um objeto destino. Ele retornará o objeto destino.

O primeiro parâmetro de Object.assign() é o objeto destino que receberá a cópia das propriedades dos objetos de origem

Podemos passar quantos objetos de origem desejarmos a partir do segundo parâmetro

**typeof():**

Verifica o tipo de dado de algo

**[].concat(array):**

Copia os valores de um array para outro

**[].join(separador):**

Uni todos os elementos de um array em uma string

 - Caso o separador seja '' não haverá separação

## Métodos API do DOM

**ElementoDOM.addEventListener('evento',funçãoDeCallBack):**

Fica monitorando uma tag até ocorrer o evento especificado, então executa a função informada.
 - O evento submit retorna um objeto que controla o evento.

**document.querySelector():** 

Uma API do DOM que nos permite buscar elementos através de seletores CSS

**document.createElement('div'):** 

Cria um novo elemento, mas para ele aparecer deve ser adcionado em algum lugar na arvore do DOM
 
**elementoDOM.appendChild(elemento):** 

Adciona elemento no final de um outro elemento(tag)

**elementoDOM.innerHTML = elemento:** 

Adciona elemento dentro de outro elemento(tag). Para conteúdo muito extenso a renderização do innerHTML pode ser lenta, melhor usar paginação

## Palavras Chaves	

**new:** 

é  bastante importante por ser o responsável pela inicialização da  variável implícita _this_ de cada instância criada, ou seja, de cada objeto criado. 

**var:**

Cria uma variável com escopo global ou de função

**let:** 

Cria uma variável com escopo de bloco

## Conceitos

**Hoisting:** 

Variáveis declaradas com *var* são içadas para o início do bloco da função na qual foram declaradas

**Temporal Dead Zone:** 

É entre a declaração da variável(usando **let**) e sua atribuição  que temos o _Temporal Dead Zone_.

Qualquer acesso feito à variável nesse espaçode tempo resultará em _ReferenceError_.

## Caracteristicas

### Formulários

 - O retorno da propriedade value dos elementos dos DOM do tipo input retorna seus valores como string. Os valores que devem ser números ou datas tem de ser convertidos.
 
### Contexto

 - Funções atribuídas a variáveis e passadas como parametros perdem seu contexto. Se o contexto original for nescessário deve-se usar o método **bind**, passando como parametro o objeto a qual o contexto é desejado.
 
### DOM

 - Uma vez buscado um elemento na página, estaremos com sua referência. Caso seu valor seja alterado não será nescessário busca-lo novamente.

## Boas Práticas

 - **Fail-Fast:** Validamos os parâmetros recebidos pelo método e já falhamos antecipadamente antes que eles sejam usados  pela lógica do programa. Mas  claro, fornecendo uma mensagem de erro clara para  o desenvolvedor sobre o problema ocorrido.
 - **Programação Defensiva:** Deve-se retornar sempre uma cópia dos objetos(array é um objeto) para que está não venham com referência do objeto original. Assim as prpriedades do objeto original não será alteradas
 - Adcionar a busca de elementos da página no construtor da classe para evitar percorrer o DOM a todo momento
 - Criar uma pasta com classes que farão as conversões nescessários. Ex: Data -> Texto e Texto -> Data. Separando assim a responsabilidade de conversão
 - As classes que só tem métodos estaticos não devem ser instanciadas. Para garantir isso devemos criar um contrutor que lança uma exceção.
 
parou no 7.3