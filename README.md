# App-Teste 

##Frontend
 
O projeto foi desenvolvido com React 17.0.1 , utilizando bibliotecas como o react-bootstrap 1.5.0, styled-components 5.2.1, para icons utilizei o react-icons ,para toasts utilizei react-toastify 7.0.3 e o axios 0.21.1 para comunicação com o backend.

##Backend

o backend foi desenvolvido com Nodejs v12.18.0 com express 4.17.1 e mongoosse 5.11.18.

##Funcionalidades 

A primeira funcionalidade é o navbar utilizado para navegação entre as rotas construídas na aplicação, usando dois ícones seguido de um texto para melhorar a visualização e facilitar a usabilidade.

A tela de cadastro onde foi criado um formulário centralizado onde tem um campo nome(String) , Idade(campo numérico), estado Civil (String), CPF (numérico), estado (campo string do tipo select), cidade(String). Para preencher os estados é consultada uma api do IBGE se comunicando por fetch.

Ao preencher o formulário e clicar no botão de salvar, primeiro será verificado se todos os campos foram preenchidos e segundo verificar se o CPF é válido utilizando regex, logo em sequência será verificado se é uma edição ou se é para salvar um novo usuário.

Após essa seleção será enviada um put (para edição) ou post (para novo usuário) json através do axios para a rota configurada no backend. No backend será acessado o controlador e na função do controlador será verificado se todos os campos foram preenchidos, após a verificação será salvo no banco de dados enviando uma resposta 200 em caso de sucesso ou 404 e 500 em caso de erro e por fim será apresentado um toast com sucesso ou erro.

Na outra rota foi criado uma tabela contendo nome, idade, cidade e ações a se executar, além disso nos dispositivos mobile as colunas cidade e idade foram ocultadas para uma melhor visualização.

Na coluna de ações existem três botões :
o icone de informação
o icone de edição
o icone de remoção,

No de informação será chamado um modal com todas as informações do usuário , no ícone de edição o usuário será redirecionado novamente para a página de formulário com o id na url como parâmetro, que com isso será lido o id e consultado no banco para buscar as informações para a edição, por ultimo o botão remover, remove o usuário da tabela ao realizar uma requisição para o backend por delete e o backend procura o usuário e remove do banco de dados, após a confirmação é selecionado um Toast com sucesso e redirecionado para o formulário.

A tabela sempre é limitada por 5 usuários cadastrados por página e para mudança de usuários na listagem da tabela é necessário clicar nas setas na parte inferior da tabela

##Decisões do projeto

Foi escolhido a stack MERN uma stack robusta que se utiliza do mongo um banco de dados noSQL com isso grava os dados através de documentos, com isso para o desenvolvimento acho muito fácil de editar coleções sendo um ótimo fator para desenvolvimento, o express por ter uma grande comunidade e ser um dos mais populares, facilita muito na implementação e na busca de soluções, facilitando assim as requisições http.

Escolhi para o backend o padrão MVC para controlar o fluxo dos dados por ser muito claro visualização, regras de negócios e ser fácil a manutenção .

Para a estilização do projeto utilizei tanto o react-bootstrap como o styed-components, a vantagem é que o bootstrap me permite facilmente construir um site mais responsivo e o styled-components para maior clareza no código e de compatibilidade com o browser mais facilmente.

Para o deploy, como não usei o Firebase me utilizei do Heroku e do mongoCloud para subir a aplicação.

