# Diagrama UML
## Diagrama UML de casos de uso
<img src="./Apollo - use Case.png"/>

Em nosso diagrama de casos de uso, existirá duas figuras, o do visitante e o do usuário cadastrado, os casos se definem em acesso a páginas e funções, sendo as páginas:
- Minha Conta;
- Login;
- Registro;
- HomePage;
- Histórico de transações;
- Ver cartões;

E funções como:
- Mostrar/Ocultar saldo;
- Recuperar senha;
- Criar/Excluir cartões;
- Criar/Excluir/Sair da conta;
- Filtrar Transações;

O usuário visitante tem acesso a HomePage, a tela de criar conta e a de login.
Já o usuário cadastrado tem acesso a todas as telas.

## Diagrama UML de classes
<img src="Apollo - Diagrama UML.png"/>

Nosso Diagrama de classes representa conceitos e abstrações de funções e atributos que os elementos que irão compor nosso projeto precisarão.
O Diagrama é composto por classes, classes estáticas e enums, junto com suas correlações.

User: Tem informações que dizem respeito somente ao usuário e seu acesso, como nome, telefone, email, senha (criptografada).

Address: O sistema permitirá o preenchimento de mais de um endereço, por isso uma relação 1 para n.

Account: é onde irá conter os dados da conta do usuário como valor em conta, número da conta, e as relações serão feitas através dela como a relação com transações e cartões.

CreditCards: É uma classe responsável por conter os dados gerais de cartão, como nosso sistema terá a função de separar crédito por cartão, essa classe armazenará os totalizadores de créditos e os métodos de criar ou bloquear cartão.

CreditCard: Serão instâncias de cartões, tendo seu número, cvc, data de expiração e seus limites total e usado.

Invoice: É a classe que armazena as contas de cartão de usuário, terá o total a pagar, total pago, e status. Todo mês a aplicação gera um novo invoice para aquele mês.

Transactions: São as transações do sistema, tendo seu valor, data, descrição, tipo (transferência, pix, crédito) e o "to" e "from", "to" seria para o caso de uma transação de saída, uma transferência da sua conta para outra por exemplo, "to"seria então a conta destino, já o "from" é no caso de uma transação de entrada, sendo assim o "from" seria a conta de origem.

Token: é uma classe estática que servirá apenas para gerar e validar o token de um usuário a fim de manter a segurança da aplicação e podermos validar se aquele usuário tem acesso aquela função
