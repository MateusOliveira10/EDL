## Tarefa-02

### Aluno: Mateus de Oliveira da Silva

<h1> Linguagem de Programação Rust </h1>

![Linguagem Rust](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Rust_programming_language_black_logo.svg/240px-Rust_programming_language_black_logo.svg.png)

<h2> Origens e influências </h2>

<p> Rust é uma linguagem de programação, um software livre e de código aberto, desenvolvida para  escrever programas de alto desempenho. A linguagem surgiu de um projeto pessoal iniciado em 2006 pelo funcionário da Mozilla, Graydon Hoare. A organização começou a apoiar o projeto em 2009 e anunciou-o em 2010. Rust é patrocinado pela Mozila, desenvolvida por membros da empresa e por uma comunidade de voluntários  de diferentes lugares do mundo. </p>

<p> Rust é fortemente influenciada por Cyclone (um dialeto seguro de C e uma linguagem imperativa), com alguns aspectos de recursos orientados a objetos de C++. Mas, ela também inclui recursos funcionais de linguagens como Haskell e OCaml. </p>

![Influências](https://user-images.githubusercontent.com/43424073/47382834-96242a80-d6d9-11e8-9eda-59726f4eb9c2.png)

<h2> Classificação </h2>

<p> A linguagem Rust é uma linguagem de programação multiparadigma (imperativa, funcional e orientada a objetos) compilada. É projetada para ser segura, concorrente e prática.Tem tipagem estática, forte, inferência de tipo, nominal e linear. </p>

<p> Rust tem sido desenvolvida e projetada para ser uma “system-language” assim como C/C++. É uma linguagem versátil e ideal para escrever “low-level codes” como drivers e sistemas operacionais. </p>

<h2> Avaliação comparativa Rust vs C\C++ </h2>

* Ênfase em escrever código seguro
* Em Rust não existem ponteiros nulos ou ponteiros soltos, impossibilitando falhas de segmentação.
* Rust gerência memória e recursos automaticamente
* Performance e uma sintaxe bastante semelhante ao C/C++
* Possui Pattern Matching que substitui o switch presente em C\C++,  sendo mais poderoso e útil.

<h2> Exemplos de códigos </h2>

<h3> Linguagem C </h3>

```
#include <stdio.h>

int main(){
    
   printf("Olá, Mundo!\n"); 
    
    
    return 0;       
    
}

```

<h3> Linguagem Rust</h3>

```
fn main() {
    println!("Olá, Mundo!");
}
```

<h3> Linguagem C </h3>

```
#include <stdio.h>

void funcao(int x, int y);

int main(){
    
  int x, y;
  
  x = 5;
  y = 6;
  
  funcao(x,y);
    
    return 0;       
    
}

void funcao(int x, int y){
    
    printf("O valor de x e: %d\n", x);
    printf("O valor de y e: %d\n", y);
     
    }
```

<h3> Linguagem Rust </h3>

```
fn main() {

    funcao(5,6);
}

fn funcao(x:i32, y:i32){
    
    println!("O valor de x e: {}", x);
    println!("O valor de y e: {}", y);
    
}
```

<h3> Acesso a ponteiro nulo </h3>

<p> O erro da falha de segmentação  é comum na linguagem C. O acesso a ponteiro nulo geralmente acontece quando se esquece de verificar a validade de um ponteiro retornado. </p>

<h4> Código em C </h4>

```
uint8_t* pointer = (uint8_t*) malloc(SIZE); // Pode retornar NULL
for(int i = 0 ; i < SIZE ; ++i) {
    pointer[i] = i; // Pode causar uma falha de segmentação
}
```

<p> Rust  lida com esses erros de ponteiro de forma extrema. Simplesmente proíbe o uso de ponteiros brutos em código "seguro". Além disso, elimina o valor nulo do código "seguro". Em vez de ponteiros, o Rust permite o uso de referências à       
 variáveis que são seguras com as regras de vida útil e empréstimo definidas na linguagem. </p>
 
 <h4> Código em Rust </h4>
 
 ```
 let my_var: u32 = 42;
let my_ref: &u32 = &my_var; // <-- Esta é uma referência. Referências SEMPRE 
                           //  <-- apontam para valores válidos
 ```
 
 <h3> Acesso a região de memória fora dos limites </h3>
 
 <p> Frequentemente, isso significa acessar um vetor com um índice fora do seu tamanho. Isso se aplica a operações de leitura e gravação. Acessar a memória fora dos limites pode introduzir vulnerabilidades no programa executável. Essas vulnerabilidades podem permitir que um invasor execute código arbitrário no computador vulnerável. </p>
 
 <h4> Código em C </h4>
 
 ```
 void print_out_of_bounds(void) {
    uint8_t array[4] = {0};
    printf("%u\r\n", array[4]);
}

// Imprime a memória que está fora do 'vetor' (na pilha)

 ```
 
 <p> Nesse caso, a linguagem Rust faz uso de verificações de tempo de execução para atenuar esse comportamento indesejado. </p>
 
 <h4> Código em Rust </h4>
 
 ```
 fn print_panics() {
    let array = [0; 4];
    println!("{}", array[4]);
}

// thread '<main>' panicked at 'índice fora dos limites:
// o tamanho é 4 mais o índice é 4', main.rs:3
 ```
<h2> Bibliografia </h2>

* https://en.wikipedia.org/wiki/Rust_(programming_language)
* https://www.rust-lang.org/en-US/faq.html
* https://www.ibm.com/developerworks/br/library/os-developers-know-rust/index.html
* https://terminaldeinformacao.com/2015/05/28/conhecendo-a-linguagem-de-programacao-rust/
* https://play.rust-lang.org//
* http://cpp.sh/
