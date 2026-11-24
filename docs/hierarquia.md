# Hierarquias previstas

## Hierarquia: Pagamento

Criamos uma classe abstrata `Pagamento` com o que todo pagamento tem em comum: a comanda, o total, a taxa do garçom e o método `pagar()`. Cada forma de pagamento (`PagamentoEspecie`, `PagamentoPix`, `PagamentoCredito` e `PagamentoDebito`) herda dela e implementa o seu próprio `executar(total)`. Em espécie guardamos o valor recebido e o troco, e no crédito guardamos a porcentagem e o valor da taxa.

## Hierarquia: Funcionário

`Funcionario` guarda o que qualquer pessoa da equipe tem, que é `id` e `nome`. O `Garcom` herda dessa classe e fica ligado às comandas que atende: um garçom pode atender várias comandas, mas cada comanda tem um só garçom.

## Hierarquia: Observador

`Observador` é uma interface que só exige o método `atualizar(evento, pedido)`. A `Cozinha` implementa essa interface e guarda a fila de pedidos que precisa preparar. Assim, a `Comanda` mantém uma lista de observadores e avisa todos eles quando algo acontece, sem precisar saber quem são.

## Composição: Comanda, Pedido e Item

Uma `Comanda` é formada por vários `Pedido`, e cada `Pedido` é formado por um ou mais `ItemPedido`. O `Cardapio` é formado pelos `Item` que o restaurante oferece. Cada `ItemPedido` aponta para um `Item` do cardápio e guarda a quantidade e a observação do cliente.
