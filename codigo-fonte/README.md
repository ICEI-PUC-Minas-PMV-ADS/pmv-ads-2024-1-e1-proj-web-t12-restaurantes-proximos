loginHTML

        </ul>
    </nav>
</header>

<main>


    <div class="content">    
        
      <!--FORMULÁRIO DE LOGIN-->
      <div id="login">
        
          <h1>Login</h1> 

          <div id="msgError"></div>

          <p class="caixa"> 
            <label id="emailLabel" for="email_login">E-mail</label>
            <input id="email_login" name="email_login" required="required" type="text" placeholder="Insira seu e-mail"/>
          </p>
          
          <p class="caixa"> 
            <label id="senhaLabel" for="senha_login">Senha</label>
            <input id="senha_login" name="senha_login" required="required" type="password" placeholder="Insira sua senha" /> 
           
          
          <p class="caixa"> 
            <input type="checkbox" name="manterlogado" id="manterlogado" value="" /> 
            <label for="manterlogado">Manter-me logado</label>
          </p>
          
          <p class="caixa"> 
            <button onclick="entrar()" class="login-button" id="botao" type=”button”>Entrar</button>
          </p>
       
      </div>
      
     
<footer class="rodape">
    <p>Restaurantes proximos | 2024.</p>
</footer>





LOGIM-CSS

        </ul>
    </nav>
</header>

<main>


    <div class="content">    
        
      <!--FORMULÁRIO DE LOGIN-->
      <div id="login">
        
          <h1>Login</h1> 

          <div id="msgError"></div>

          <p class="caixa"> 
            <label id="emailLabel" for="email_login">E-mail</label>
            <input id="email_login" name="email_login" required="required" type="text" placeholder="Insira seu e-mail"/>
          </p>
          
          <p class="caixa"> 
            <label id="senhaLabel" for="senha_login">Senha</label>
            <input id="senha_login" name="senha_login" required="required" type="password" placeholder="Insira sua senha" /> 
           
          
          <p class="caixa"> 
            <input type="checkbox" name="manterlogado" id="manterlogado" value="" /> 
            <label for="manterlogado">Manter-me logado</label>
          </p>
          
          <p class="caixa"> 
            <button onclick="entrar()" class="login-button" id="botao" type=”button”>Entrar</button>
          </p>
       
      </div>
      
     
<footer class="rodape">
    <p>Restaurantes proximos | 2024.</p>
</footer>




LOGIN JS

function entrar(){


    let email_login = document.querySelector("#email_login")
    let emailLabel = document.querySelector("#emailLabel")
    
    let senha_login = document.querySelector("#senha_login")
    let senhaLabel = document.querySelector("#senhaLabel")
    
    let msgError = document.querySelector("#msgError") // para quando errar senha ou email
    
    let listaUser = [] //listaUser criada no código do cadastro
    
    
  
    let userValid = { //para validar e depois percorrer com Foreach
        
      email: "",
      senha: "",
      nome: ""
     
    }
    //pega a listaUser do LocalStorage criada no cadastro e percorre essa lista para comparar os dados que eu insiro no login com os dados retirados ao fazer o cadastro
    listaUser = JSON.parse(localStorage.getItem("listaUser"))
    listaUser.forEach((item) => { 
      if(email_login.value == item.emailUser && senha_login.value == item.SenhaUser){
  
  
        userValid = {
           email: item.emailUser,
           senha: item.SenhaUser,
           nome: item.nomeUser,
           telefone: item.telefoneUser,
           opcoes: item.opcoesUser,
           endereco: item.enderecoUser,
           instituicao: item.localUser
           
         }
        
      }
    })
     
    //se as informações são validadas então redireciona para a pagina de perfil // também coloquei que o campo tem que estar preenchido
    if(email_login.value == userValid.email && senha_login.value == userValid.senha && email_login.value != "" && senha_login.value != ""){
     
      
      window.location.href = "../paginaPerfil/perfil.html"
      
      
      let mathRandom = Math.random().toString(16).substr(2) 
      let token = mathRandom + mathRandom
      
      localStorage.setItem("token", token)
  
      localStorage.setItem('userLogado', JSON.stringify(userValid))
      localStorage.setItem('nome', JSON.stringify(nomeUser))
      localStorage.setItem('telefone', JSON.stringify(telefoneUser))
      localStorage.setItem('opcoes', JSON.stringify(opcoesUser))
      localStorage.setItem('endereco', JSON.stringify(enderecoUser))
      localStorage.setItem('instituicao', JSON.stringify(localUser))
  
      
  
    } else {
      msgError.setAttribute('style', 'display: block')
      msgError.innerHTML = "Usuário ou senha incorretos"
      emailLabel.setAttribute('style', 'color: red')
      email_login.setAttribute('style', 'border-color: red')
      senhaLabel.setAttribute('style', 'color: red')
      senha.setAttribute('style', 'border-color: red')
  
    }
    
  }


  CADASTRO HTML

  <!DOCTYPE html>
<html lang="pt-br">

<head>
    <title>Restaurantes proximos</title>
    <link rel="stylesheet" href="../cadastroUsuario/cadastro-style.css">
    <link rel="stylesheet" href="../login/login-style.css">
    
    
  
    
</head>

<body>
    <header>
        <nav>
            <a class="logo" href="../encontreRestaurante/encontre.html">Restaurantes proximos</a>
            <div class="mobile-menu">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
            <ul class="nav-list">
                <li><a href="../encontreRestaurante/encontre.html">Encontre Restaurante</a></li>
                <li id="menu-cadastro"><a href="../cadastroUsuario/cadastro.html">Cadastre-se</a></li>
                <li id="menu-entrar"><a href="../login/login.html">Entrar</a></li>
            </ul>
        </nav>
    </header>
    <main>
    
     <form onsubmit="return false"  name="formulario">
        <div class="cadastrar">
            <h1 class="cad-um">Cadastro</h1>
             <div class="caixas">
                 <div class="caixa">
                    <label>Nome Completo *</label><br/>
                    <input type="text" name="nome" id="nome"  minlength="4" required placeholder="Digite seu nome"><br/>
                 </div>               
                 <div class="caixa">
                     <label>Email *</label><br/>
                     <input type="email" name = "email" id="email" required placeholder="Digite seu email"></br>
                 </div>
                 <div class="caixa">
                     <label>Telefone *</label><br/>
                     <input type="tel" minlength="11" name="telefone" id="telefone"  required placeholder="(99)99999-9999"></br>
                 </div>
                 <div class="caixa">
                    <label>Perfil *</label><br/>
                    <select id ="opcoes" name="opcoes">
                        <option value ="null" disabled selected hidden>Selecione</option>
                        <option value ="consumidor" id="consumidor"> Consumidor</option>
                        <option value ="comerciante" id="comerciante">Comerciante</option>
                    </select>
                    
                </div>
                 <div class="caixa">
                     <label>Endereço *</label><br/>
                     <input type="text" name="endereco" id="endereco" minlength="10" required placeholder="Endereço completo"></br>
                 </div>
                 <div class="caixa">
                     <label>Senha *</label><br/>
                     <input type="password" name="Senha" id="Senha" minlength="6"  required placeholder="Crie uma senha"></br>
                   
                 </div>
                 <div class="caixa">
                     <label>Confirmação de senha *</label><br/>
                     <input type="password" name="ConfirmeSenha"  id = "ConfirmeSenha"  minlength="6" required  placeholder="Confirme sua senha"></br>
                 </div>
                 <p>
                     Campos obrigatórios(*)
                 </p>
             </div>
             <div>
                <button onclick=" return cadastrar()" class="cad-button" id="botao" >Cadastrar</button>
             </div>
        </div>
    </form>
    
        <footer class="rodape">
            <p>Restaurantes proximos | 2024.</p>
        </footer>
    </main>
</body>

</html>

CADASTRO CSS

@media (max-width: 999px) {
    .cadastrar{
        width:90%;
      }

     } 

@media(min-width: 1000px){
     .cadastrar{
         width: 700px;
        }
      }
      
    .cadastrar {
        font-size: 16px;
        font-family: Arial, Helvetica, sans-serif;
        color: #ffc400;
        display:flexbox;
        text-align:left;
        line-height: 2;
        box-sizing: border-box;
        border: 2px solid #000000;
        border-radius: 10px;
        margin: 80px auto;
        padding: 10px 50px;
        align-items: center;
        list-style-type: none;
        text-align: center;
      }
      
      .cad-um {
        font-size: 30px;
        line-height: 2.5;
        font-weight: bold;
        text-align:center;
      }
      
      .caixas {
        text-align:left;
        
      }
      
      .caixa {
        margin: 10px 5px;
      }
      
      .caixa input, #opcoes{
        box-sizing: border-box;
        width: 100%;
        height: 30px;
        background-color: white;
        padding: 3px;
        /* margin: 10px; */
        border: 1px solid #000000;
        color: #000000;
        border-radius: 10px;
        
      }
      .cad-button {
        align-items: center;
        font-size: 18px;
        color: whitesmoke;
        background-color: #ffc400;
        margin: 20px;
        border-radius: 10px;
        padding: 5px 20px;
      }


CADASTRO JS

function cadastrar() {

    if (nome.value == "" || nome.value.length < 4) {
        alert("Preencha o formulário corretamente!");
        nome.focus();
        return;
    }
    if (email.value == "") {
        alert("Preencha o formulário corretamente!");
        email.focus();
        return;
    }
    if (telefone.value == "" || telefone.value.length < 11) {
        alert("Preencha o formulário corretamente!");
        telefone.focus();
        return;
    }
    if (local.value == "" || local.value.length < 3) {
        alert("Preencha o formulário corretamente!");
        local.focus();
        return;
    }
    if (opcoes.value == "null") {
        alert("Preencha o formulário corretamente!");
        opcoes.focus();
        return;
    }
    if (endereco.value == "" || endereco.value.length < 10) {
        alert("Preencha o formulário corretamente!");
        endereco.focus();
        return;
    }
    if (Senha.value == "" || Senha.value.length < 6) {
        alert("Preencha o formulário corretamente!");
        Senha.focus();
        return;
    }
    if (ConfirmeSenha.value == "") {
        alert("Preencha o formulário corretamente!");
        ConfirmeSenha.focus();
        return;
    }

    if (Senha.value != ConfirmeSenha.value) {
        alert("As senhas não correspondem!");
        ConfirmeSenha.focus();
        return;
    }

    let listaUser = JSON.parse(localStorage.getItem('listaUser') || '[]');

    listaUser.push(
        {
            nomeUser: nome.value,
            emailUser: formulario.email.value,
            telefoneUser: formulario.telefone.value,
            localUser: formulario.local.value,
            opcoesUser: formulario.opcoes.value,
            enderecoUser: formulario.endereco.value,
            SenhaUser: formulario.Senha.value,
            ConfirmeSenhaUser: formulario.ConfirmeSenha.value
        });

    localStorage.setItem("listaUser", JSON.stringify(listaUser));

    alert("Usuário cadastrado com sucesso!");
    window.location.href = "../login.html";
}



ENCONTRE HTML

<!DOCTYPE html>
<html lang="pt-br">

<head>
    <title>Restaurantes proximos</title>
    <link rel="stylesheet" href="encontre-style.css">
</head>

<body>
    <header>
        <nav>
            <a class="logo" href="../encontreRestaurante/encontre.html">Restaurantes proximos</a>
            <div class="mobile-menu">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
            <ul class="nav-list">
                <li><a href="../encontreRestaurante/encontre.html">Encontre Restaurante</a></li>
                <li id="menu-cadastro"><a href="../cadastroUsuario/cadastro.html">Cadastre-se</a></li>
                <li id="menu-entrar"><a href="../login/login.html">Entrar</a></li>
            </ul>
        </nav>
    </header>
    <main class="main">
        <div class="corpo">
            <h1>O restaurante certo no momento ideal!</h1>
        </div>
    </main>
    <section class="servicos-home corpo">
        <h1 class="titulo">Serviços</h1>
        <ul class="servicos-home-lista">
            <li>
                <h2>Churrascaria</h2>
                    <img src="../encontreRestaurante/churrascaria.jpg" alt="churrascarias">
                    <a href="../paginaLivros/paginaLivros.html">Confira algumas churrascarias disponíveis!</a>
            </li>
            <li>
                <h2>Pizzaria</h2>
                    <img src="../encontreRestaurante/pizzaria.jpg" alt="pizzaria">
                    <a href="../paginaTutorias/paginaTutorias.html">Confira algumas pizzaria disponíveis!</a>
            </li>
            <li>
                <h2>Hamburgueria</h2>

                    <img src="../encontreRestaurante/hamburgueria.jpg" alt="hamburgueria">
                    <a href="../paginaCadastro/cadastre-se.html">Confira algumas hamburgueria disponíveis!</a>
        </ul>
    </section>
    <section class="depoimentos-home">
        <div class="corpo">
            <h1 class="titulo">Depoimentos dos consumidores</h1>
            <ul class="depoimentos-lista">
                <li>
                    <div>
                        <h2>João Santos</h2>
                        <q>"O restaurante Sabor Caseiro é uma ótima escolha para quem procura uma refeição reconfortante e saborosa. Os pratos são bem servidos e têm aquele gostinho de comida feita em casa. Destaque para o atendimento simpático e prestativo. Recomendo o estrogonofe de carne, simplesmente delicioso!"</q>
                    </div>
                </li>
                <li>
                    <div>
                        <h2>Ana Rodrigues</h2>
                        <q>"Minha experiência no Bistrô Le Charme foi decepcionante. Apesar do ambiente bonito, a comida deixou muito a desejar. Os pratos estavam mal temperados e a apresentação não correspondia ao esperado. Além disso, o serviço foi lento e desorganizado. Não pretendo voltar."</q>
                    </div>
                </li>
                <li>
                    <div>
                        <h2>Pedro Oliveira</h2>
                        <q>"O restaurante Sabores do Oriente me surpreendeu positivamente. A comida estava fresca e cheia de sabor, especialmente o sushi que estava muito bem preparado. O atendimento foi atencioso e o ambiente era agradável. Uma excelente opção para os amantes da culinária oriental!"</q>
                    </div>
                </li>
                <li>
                    <div>
                        <h2>Maria Silva</h2>
                        <q>"Fui ao restaurante La Gourmetia e tive uma experiência incrível! A comida estava deliciosa, o ambiente era aconchegante e o serviço foi impecável. Recomendo o prato de salmão grelhado, estava divino! Com certeza voltarei em breve."</q>
                    </div>
                </li>
            </ul>
        </div>
    </section>
    <section class="sobre-home">
        <div class="corpo">
            <h1 class="titulo">Sobre o projeto Restaurantes proximos</h1>
            <div id="sobre-conteudo">
                <img class="sobre-logo" src="../encontreRestaurante/logo.PNG" alt="Logotipo marca-texto amarelo">
                <p class="sobre-texto">Este projeto é justificado pela crescente demanda por soluções que simplifiquem o processo de escolha de restaurantes e melhorem a experiência do usuário. Além disso, a criação de uma plataforma que promova a descoberta e apoie os negócios locais é fundamental para fortalecer a comunidade e estimular o desenvolvimento econômico.</p>
    </section>
    <footer class="rodape">
        <p>Restaurantes proximos | 2024.</p>
    </footer>
</body>

</html>

ENCONTRE CSS

/* LIMPAR CONFIGURAÇÃO PADRÃO DO BROWSER*/

* {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font: inherit;
    vertical-align: baseline;
  }
  
  /* MENU DE NAVEGAÇÃO */
  
  a {
    color: rgb(0, 0, 0);
    text-decoration: none;
    transition: 0.3s;
  }
  
  a:hover {
    opacity: 0.7;
  }
  
  .logo {
    font-size: 28px;
    font-family: cursive;
  }
  
  nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    font-family: Arial, Helvetica, sans-serif;
    background: #ffc400;
    height: 8vh;
  }
  
  main {
    height: 92vh;
  }
  
  .nav-list {
    list-style: none;
    display: flex;
  }
  
  .nav-list li {
    letter-spacing: 3px;
    margin-left: 32px;
  }
  
  .mobile-menu {
    display: none;
    cursor: pointer;
  }
  
  .mobile-menu div {
    width: 32px;
    height: 2px;
    background: rgb(0, 0, 0);
    margin: 8px;
    transition: 0.3s;
  }
  
  @media (max-width: 999px) {
    body {
      overflow-x: hidden;
    }
  
    .nav-list {
      position: absolute;
      top: 8vh;
      right: 0;
      width: 50vw;
      height: 92vh;
      background: #ffffff;
      flex-direction: column;
      align-items: center;
      justify-content: space-around;
      transform: translateX(100%);
      transition: transform 0.3s ease-in;
    }
  
    .nav-list li {
      margin-left: 0;
      opacity: 0;
    }
  
    .mobile-menu {
      display: block;
    }
  }
  
  .nav-list.active {
    transform: translateX(0);
  }
  
  @keyframes navLinkFade {
    from {
      opacity: 0;
      transform: translateX(50px);
    }
  
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
  
  .mobile-menu.active .line1 {
    transform: rotate(-45deg) translate(-8px, 8px);
  }
  
  .mobile-menu.active .line2 {
    opacity: 0;
  }
  
  .mobile-menu.active .line3 {
    transform: rotate(45deg) translate(-5px, -7px);
  }
  
  /* ESTILO PADRÀO */
  
  body {
    font-family: Arial, Helvetica, sans-serif;
    background: #ffc400(255, 255, 255);
    color: #000000;
  }
  
  section {
    padding: 4rem 0;
  }
  
  img {
    display: block;
    max-width: 100%;
  }
  
  h1, h2 {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.2;
    font-weight: 700;
  }
  
  p {
    font-size: 0.875rem;
    line-height: 1.5;
  }
  
  .corpo {
    max-width: 1200px;
    margin-left: auto;
    margin-right: auto;
    padding-left: 1rem;
    padding-right: 1rem;
  }
  
  .titulo {
    font-size: 1.5rem;
    color: #ffc400;
    text-align: center;
    margin-bottom: 2rem;
  }
  
  /* MAIN */
  
  .main {
    margin-top: 0;
    width: 100%;
    height: 500px;
    background: url("capa.jpg") no-repeat center center;
    background-size: cover;
    color: rgb(255, 255, 255);
    text-align: center;
    display: flex;
    align-items: center;
  }
  
  .main h1 {
    font-size: 2.25rem;
    text-transform: none;
  }
  
  .main p {
    font-size: 1.125rem;
    font-style: italic;
    margin-top: 1rem;
  }
  
  /* SERVIÇOS */
  
  .servicos-home {
    text-align: center;
  }
  
  .servicos-home-lista {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
    list-style-type: none;
  }
  
  .servicos-home-lista li {
    background: #ffffff(255, 255, 255);
    border: 1px solid #ffc400(0, 0, 0);
    border-radius: 10px;
    text-align: center;
  }
  
  .servicos-home-lista li h2 {
    font-size: 1.125rem;
    color: #ffc400;
    text-transform: uppercase;
    height: 200px;
    border-radius: 5px 5px 0 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .servicos-home-lista a {
    display: block;
    margin-top: 1rem;
    font-family: Arial, Helvetica, sans-serif;
    color: #000000;
  }
  
  .servicos-home-lista a:hover {
    text-decoration: none;
    color: #000000;
  }
  
  /* DEPOIMENTOS */
  
  .depoimentos-home {
    width: 100%;
    background: rgb(255, 255, 255);
    text-align: center;
  }
  
  .depoimentos-lista {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    text-align: left;
    padding: 2rem 0;
  }
  
  .depoimentos-lista li {
    display: grid;
    grid-template-columns: auto minmax(200px, 1fr);
    gap: 1rem;
    align-items: center;
  }
  
  .depoimentos-lista img {
    border-radius: 50%;
    box-shadow: 2px 2px 2px #ffc400(0, 0, 0, 0.08);
  }
  
  .depoimentos-lista h2 {
    font-size: 1.125rem;
    margin-bottom: 1rem;
  }
  
  .depoimentos-lista q {
    font-size: 1rem;
    line-height: 1.5;
    font-style: italic;
  }
  
  /* SOBRE */
  
  .sobre-home {
    width: 100%;
  }
  
  #sobre-conteudo {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    align-items: center;
  }
  
  .sobre-logo {
  width: 45%;
  margin: auto;
  }
  
  .sobre-texto {
    font-size: 1.050rem;
  }
  
  html {
    scroll-behavior: smooth;
  }
  
  /* FOOTER - RODAPÉ */
  
  .rodape {
    background-color: #000000;
    font-family: Arial, Helvetica, sans-serif;
    color: rgb(255, 255, 255);
    font-size: 15px;
    text-align: center;
    padding: 20px 0px 20px 0px;
    position: static;
    left: 0;
    bottom: 0;
    width: 100%;
  }
  
  /* RESPONSIVIDADE */
  
  @media only screen and (max-width: 750px) {
    .servicos-home-lista,
    .depoimentos-lista,
    .sobre-corpo,
    .servicos-corpo {
      grid-template-columns: 1fr;
      justify-items: center;
    }
  
    .main,
    .sobre,
    .servicos {
      height: 400px;
    }
    
    .servicos-home-lista li {
      max-width: 388px;
    }
  
    .depoimentos-lista {
      padding: 0px;
    }
  
    body {
      overflow-x: hidden;
    }
  }
  
  @media only screen and (max-width: 400px) {
    .main h1 {
      font-size: 1.5rem;
    }
  
    .titulo {
      font-size: 1.125rem;
    }
  
    .depoimentos-lista li {
      grid-template-columns: 1fr;
      justify-items: center;
      text-align: center;
    }
  
    body {
      overflow-x: hidden;
    }
  }
  
D:\Workspaces\Restaurantes Proximos\encontreRestaurante\pizzaria.jpg
D:\Workspaces\Restaurantes Proximos\encontreRestaurante\logo.PNG
D:\Workspaces\Restaurantes Proximos\encontreRestaurante\hamburgueria.jpg
D:\Workspaces\Restaurantes Proximos\encontreRestaurante\churrascaria.jpg
D:\Workspaces\Restaurantes Proximos\encontreRestaurante\capa.jpg      

file:///D:/Workspaces/Restaurantes%20Proximos/encontreRestaurante/encontre.html

