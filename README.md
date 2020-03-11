# OOP in JavaScript

Uma aplicação é uma coleção de Objetos que se comunicam entre si. Esses Objetos são baseados em coisas do mundo real,
como produtos em um inventório ou históricos de empregados.
Objetos contém informações e executam lógicas baseado nessas informações. 

# Classes

- Classes são usadas em OOP como modelo para criação de objetos. Um objeto é então uma instância de uma classe.
Instanciar é a criação de um objeto baseado na classe. 

# Criando uma classe

class Product { 
    constructor(name, price) {
        this.name = name 
        this.price = price
    }
}

- Uma classe é do tipo Function
- Método especial para criar e iniciar um objeto criado pela classe. Só pode existir um por classe. 
- super() pode ser chamado pelo construtor para chamar o construtor de uma classe pai.

const bread = new Product('bread', 1)
const water = new Product('water', .25

- A keyword new é usada para criar novos objetos.

# Classe em JS
- Uma Classe em JS  parece com uma função mas é usada diferentemente. O nome da função começa com letra maiuscula. 
- O código dentro da função é o constructor. Ele é executado cada vez que um objeto é instanciado. Os parâmetros começam
com underline seguido do nome (ex: _name, _price). Cada novo objeto guarda esses valores dentro.

# Encapsulação 
Confira a seguir outra versão de declarar uma classe: 

function Product(name, price) {  
	this.name = name;  
	this.price = price;
}

- Não requer os métodos getters. Porém agora é dado acesso completo às propriedades de fora, sendo possível que 
qualquer pessoa acesse-as e modifique-as, da seguinte forma:

const bread = new Product('bread', 1);
bread.price = -10;

- Objetos devem ter controle exclusivo sobre suas informações; Objetos 'encapsulam' suas informações para previnir
que outros objetos acessem e modifiquem as informações diretamente. 

# Inheritance
- Herança deixa você criar uma nova classe extendendo outra classe existente, porém com propriedades e funções adicionais.
- A nova classe 'herda' todas as caracteristicas da classe pai, evitando ter que reescrever outro código do zero. 
Além disso, qualquer mudança feita na classe pai automaticamente estará disponível para a classe filha. Isso facilita
a atualização.

# JS e OOP
Há três paradigmas diferentes de programação usados em JS. 

- Prototype-Based Programming
- Object-Oriented Programming
- Functional-Oriented Programming

O ES6 adiciou uma keyword class dedicada para OOP.  

# Criando classes com ES6
Exemplo: 

class Produto { 
    constructor(nome, preço) {
        this.nome = nome 
        this.preço = preço 
    }
}

class Livro extends Produto { 
    constructor(nome, preço, autor) {
        super(nome, preço)
        this.autor = autor 
    }
}

class Cesta { 
    constructor() {
        this.produtos= [] 
    }
    addProduto(qnt, produto) {
        this.produtos.push(...Array(qnt).fill(produto))
    }
    calcTotal() {
        return this.produtos.map(produto=> produto.preço).reduce((a,b) => a + b)
    }
    imprimirNota() {
        console.log("Total: " + this.calcTotal())
    }
}



