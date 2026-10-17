# Progresso: Cafeteria-Sass

## Dia 1: ambiente e variáveis

### Passo a passo do que fiz

1. Entrei na pasta de trabalho e criei o projeto:
   `mkdir Cafeteria-Sass`, `cd Cafeteria-Sass` e `pwd` (para confirmar onde estou).
2. Abri a pasta no VS Code com `code .`.
3. Conferi o Node e o npm com `node -v` e `npm -v`.
4. Criei o `package.json` (a ficha do projeto) com `npm init -y`.
5. Instalei o SASS só neste projeto com `npm install sass --save-dev`.
   Isso criou a pasta `node_modules` e o `package-lock.json`, que não devo editar.
6. Criei as pastas com `mkdir scss css`.
   A `scss` guarda o que eu escrevo e a `css` guarda o que o SASS gera.
7. No `package.json`, troquei a linha `test` do bloco `scripts` por:
   `"sass": "sass --watch scss/estilos.scss css/estilos.css"`
8. Criei os arquivos com `touch scss/_variaveis.scss scss/estilos.scss`.
9. No `_variaveis.scss` escrevi:
   `|$cor-primaria: #6f4e37;`, `$|cor-fundo: #fdf6ec;` e `|$espacamento-base: 1rem;`
10. No `estilos.scss` escrevi `@use 'variaveis' as *;` e um bloco `body` usando as variáveis, com `padding: $espacamento-base * 2;`.
11. Rodei `npm run sass` e o SASS gerou o `css/estilos.css`.
12. Testei o `--watch`: troquei `$|cor-primaria` para `#c0392b`, salvei, e o CSS mudou sozinho. Depois voltei para `#6f4e37`.
13. Abri um segundo terminal (botão +) e criei este arquivo com `touch PROGRESSO.md`.

### O que aprendi

- Variável: guarda um valor para reutilizar. Começa com `|$`, por exemplo `$|cor-primaria`.
- Partial: arquivo SCSS que começa com `_` (como `_variaveis.scss`). Não vira CSS sozinho, é só um pedaço que outro arquivo importa.
- `@use`: importa um partial. Não precisa do `_` nem da extensão.
- Operador: o SASS calcula valores. `$espacamento-base * 2` virou `2rem` no CSS.
- Compilar: o SASS lê o SCSS e gera o CSS que o navegador entende. As variáveis somem e viram valores reais.
- `--watch`: deixa o SASS vigiando os arquivos. Ao salvar, ele recompila sozinho.
- `npm run sass`: executa o script `sass` que coloquei no `package.json`.
- O `estilos.css` nunca deve ser editado à mão, porque o SASS reescreve o arquivo a cada compilação.

### O que errei e como percebi

- Digitei `nkdir` em vez de `mkdir`. O terminal avisou "Comando não encontrado" e sugeriu o nome certo.
- Digitei `--watch` dentro do terminal que já estava rodando o SASS. Não deu problema, mas o certo é abrir um segundo terminal para outros comandos.
- Achei que o terminal tinha travado, mas ele estava só vigiando os arquivos.
- Para parar o SASS uso Ctrl-C com o foco dentro do terminal.

### Próximo passo (Dia 2)

Criar o `index.html` da cafeteria e o primeiro bloco BEM.


Olá! Estou continuando meu projeto de aprendizagem Cafeteria-Sass (SASS e BEM), em sessões de cerca de 30 minutos por dia. Quero entender os conceitos, com explicação detalhada, passo a passo, e confirmando comigo antes de avançar. Hoje é o Dia 2: criar o index.html da cafeteria e o primeiro bloco BEM. Meu PROGRESSO.md está abaixo:

(cole aqui o conteúdo do PROGRESSO.md)

## Dia 2: HTML e primeiro bloco BEM

### O que fiz

- Criei `index.html` (raiz) e `scss/_cabecalho.scss` com `touch index.html scss/_cabecalho.scss`.
- No HTML, usei o bloco BEM `cabecalho` e os elementos `cabecalho__logo`, `cabecalho__menu` e `cabecalho__link`.
- No `_cabecalho.scss`, usei `@use 'variaveis' as *;` e o `&` para montar os elementos.
- No `estilos.scss`, importei o partial com `@use 'cabecalho';` e troquei o `padding` do body por `margin: 0`.
- Abri a página no navegador (Live Server) e vi a faixa marrom com o logo e os links.
- Li o `css/estilos.css` gerado e comparei com o SCSS.

### O que aprendi

- Cada partial precisa importar as variáveis que usa com seu próprio `@use`.
- O `&` dentro de um bloco: (ESCREVA COM SUAS PALAVRAS)
- No CSS final, o `&__logo` virou `.cabecalho__logo`, uma classe independente.
- As variáveis somem no CSS final e viram valores reais (`#6f4e37`, `2rem`).
- A ordem das regras no CSS segue a ordem dos `@use`.
- O `estilos.css.map` liga o CSS ao SCSS nas ferramentas do navegador.
- O `npm run sass` só funciona na raiz do projeto, onde está o `package.json`.
- O terminal do `npm run sass` fica ocupado vigiando; outros comandos vão no segundo terminal.

### Próximo passo (Dia 3)

- Criar o próximo bloco BEM (seção principal da página).
- Treinar o `&:hover` nos links do cabeçalho.
- Religar o vigia com `npm run sass` na raiz.