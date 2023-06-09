# Hackathon IDP

## Equipe: Os Conquistadores da Disrupção

### Desafio Escolhido

Foi escolhido o desafio do restaurante localizado no IDP por este ser um problema crescente, pois o número de alunos do IDP irá aumentar bastante nos próximos anos e semestre.


### Inovações

Após o desafio delimitado, algumas soluções foram pensadas, entre elas:
 1. O aluno (cliente) poder fazer o pedido durante a aula, e assim que o intervalo começar, seu pedido já tenha sido esquentado e esteja em uma estufa para manter seu calor, apenas aguardando sua busca.

 2. Criação de duas filas na frente da lanchonete, uma para que as pessoas que compraram pela web apenas retirem seus pedidos, e outra para pessoas que estjam realizando seu pedido na hora.

 3. Disponibilização de um funcionário que ficará por conta apenas das entregas dos pedido, a fim de otimizar o andamento da fila.

 4. Uma aba em que o cliente possa acompanhar o preparo do pedido através de uma "linha do tempo", onde o pedido passará por 3 estágios: Pedido aceito, em preparo e pronto para ser retirado.

 5. Uma aba na visão do lojista, onde ele possa facilmente trocar o estágio do pedido.

### Escolha de ferramentas

Foram cogitadas diferentes ferramentas para a construção da proposta final.

No entanto, optou-se por construir o front end utilizando Flask, uma biblíoteca de Python, para que a requisição da API e construção da aplicação fosse feita em uma única ferramenta, em conjunto com o HTML e CSS.

O request da API foi feito da seguinte forma:

`url = 'https://hackarestaurante-os-conquistadores-da-disrupcao.azurewebsites.net'`
`caminho = 'end_point'`
`r = requests.get(url + caminho)`
`resposta_api = r.json() `

O Flask teve um papel muito relevante, pois atua como servidor quando o usuário pede a página, e como client quando o flask faz requsições à API.

Os caminhos para as páginas HTML foram definidos como:

`@app.route("/html_escolhido")`
`def index():`
`return render_template('html_escolhido.html')`

Após isso, foram montadas as páginas:


 1. Inicial
        
        possui um header que redireciona para as outras páginas.
 
 2. Cardápio

    Recebe uma lista de .json, que pode ser interpretada pelo Python como dicionário, e então mostra esta lista em forma de "cardápio", apresentado a classe da comida/bebida, a imagem e o custo unitário.

    Também possui um botão embaixo de cada item, escrito "Adicionar ao Carrinho". Uma vez que o botão do item é pressionado, é possível ir até o carrinho para acompanhar os itens.

 3. Carrinho

    Os itens serão apresentados por suas imagens e o preço total dos produtos adicionados é apresentado no final, dando opção ao usuário de finalizar suas compras.

 4. Login

    A tela de login é conectada à API e possui duas caixas de input, para receber os dados do usuário e fazer seu reconhecimento no banco de dados dado pela API.

 5. Cadastro

    Caso o usuário não possua cadastro, ele poderá apertar no botão registrar, presente na tela de login ou no header, e então poderá criar seu próprio usuário.

  6. Checkout

   Apresenta o total do pedido e um input para selecionar a forma de pagamento. 
 
 7. Acompanhe seu pedido

   Esta página apresenta o item do pedido, o valor do pedido, a forma de pagamento, o status do pedido e tempo de espera.

Após a criação destas telas, decidiu-se utilizar o framework bootstrap para tornar alguns objetos presentes na aplicação um pouco mais bonitos e organizados.

