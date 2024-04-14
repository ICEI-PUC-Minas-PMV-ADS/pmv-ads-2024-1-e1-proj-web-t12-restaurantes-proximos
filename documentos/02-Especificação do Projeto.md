# Especificação do Projeto

## Perfis de Usuários
<table>
<tbody>
<tr>
<th colspan="2">Perfil 1: Consumidor </th>
</tr>
<tr>
<td width="150px"><b>Descrição</b></td>
<td width="600px">
Pessoa em busca de um restaurante. 
</td>
</tr>
<tr>
<td><b>Necessidades</b></td>
<td>
Filtrar por localidade. 

Ter acesso ao cardápio online. 

Filtrar por Ambiente. 

Filtrar por Avaliações. 

Ver fotos do restaurante. 

Verificar se possui estacionamento. 

Verificar se possui espaço kids. 

Fazer Reserva online. 

Horário de Funcionamento. 
</td>
</tr>
</tbody>
</table>

<table>
<tbody>
<tr>
<th colspan="2">Perfil 2: Comerciante  </th>
</tr>
<tr>
<td width="150px"><b>Descrição</b></td>
<td width="600px">
Restaurantes em busca de clientes 
</td>
</tr>
<tr>
<td><b>Necessidades</b></td>
<td>
Entender as demandas dos clientes. 

Cadastrar pratos  

Inserir imagens  

Disponibilizar informações sobre o estabelecimento  
</td>
</tr>
</tbody>
</table>

<table>
<tbody>
<tr>
<th colspan="3">Perfil 3: Administrador   </th>
</tr>
<tr>
<td width="150px"><b>Descrição</b></td>
<td width="600px">
Administrar é cuidar do website
</td>
</tr>
<tr>
<td><b>Necessidades</b></td>
<td>
Corrigir bugs  
  
Controle de acesso 
</td>
</tr>
</tbody>
</table>



## Histórias de Usuários
|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE`                                             |PARA ... `MOTIVO/VALOR`                 |
|--------------------|--------------------------------------------------------------------------------|----------------------------------------|
|Consumidor  | Encontrar um restaurante em um raio de 2km  | Estou com dificuldade de locomoção   |
|Consumidor  | Buscar restaurantes em Cabo Frio   | Estou em viagem e não conheço a região   |
|Consumidor |Buscar restaurantes 5 estrelas   | Quero ter uma noite especial em casal    |
|Comerciante | Cadastrar pratos típicos da região    | Tem uma alta procura de clientes   |
|Comerciante | Informar que o comércio tem estacionamento  | Facilitar e dar mais conforto aos clientes |
|Administrador   |Controle de dados   | Analisar dados de perfis maliciosos, suporte, manutenção  |


## Requisitos do Projeto

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-01| A aplicação deve permitir ao consumidor cadastrar uma conta  | ALTA | 
|RF-02| A aplicação deve permitir ao consumidor fazer o login da sua conta .   | ALTA | 
|RF-03| Possibilitar aos usuários pesquisarem restaurantes com base em critérios como localização, tipo de cozinha, preço, avaliações dos usuários etc.     | ALTA |
|RF-04| Permitir aos usuários visualizarem detalhes completos de um restaurante, incluindo menu, fotos, comentários e avaliações.    | ALTA |
|RF-05|Enviar notificações aos usuários sobre ofertas especiais, novos restaurantes na área, confirmações de reservas.   | MÉDIA   |
|RF-06|A aplicação deve permitir ao comerciante fazer o cadastro de pratos.    | ALTA  |
|RF-07| A aplicação deve permitir ao comerciante disponibilizar informações sobre o restaurante.    | ALTA |
|RF-08|   A aplicação deve apresentar, para cada prato, uma imagem correspondente.   | BAIXA |
|RF-09| A aplicação deve permitir ao comerciante visualizar as informações sobre o consumidor que foi ao restaurante.   | MÉDIA |
|RF-10| Integrar o sistema com serviços de mapas para fornecer direções para os restaurantes.   | MÉDIA  |
|RF-11| Enviar notificações aos usuários sobre ofertas especiais, novos restaurantes na área, confirmações de reservas.   | BAIXA |
|RF-12| Permitir que os usuários avaliem e comentem sobre os restaurantes que visitaram.   | BAIXA |

**Prioridade: Alta / Média / Baixa.  

### Requisitos Não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-01| O web site deve ser publicado em um ambiente acessível público na Internet.   | ALTA | 
|RNF-02| O web site deverá ser de fácil entendimento permitindo a visualização em dispositivos diversos de forma adequada  | MÉDIA | 
|RNF-03| O web site deve ter bom nível de contraste entre os elementos da tela.    | BAIXO | 
|RNF-04| O web site deve ser compatível com os navegadores de mercado: Google Chrome, Firefox e Microsoft Edge.   | ALTA | 
|RNF-05| Assegurar que as informações dos usuários, como dados pessoais e informações de pagamento, sejam protegidas contra acesso não autorizado   | ALTA | 
|RNF-06| Desenvolver o sistema de forma modular e bem documentada para facilitar futuras atualizações e manutenção | ALTA | 
|RNF-07| Projetar o sistema de forma que possa lidar com um aumento significativo no número de usuários e restaurantes sem comprometer o desempenho   | MÉDIA | 
|RNF-08| Garantir que o sistema esteja disponível 24 horas por dia, 7 dias por semana, para que os usuários possam acessá-lo sempre que desejarem.  | ALTA |


**Prioridade: Alta / Média / Baixa.
