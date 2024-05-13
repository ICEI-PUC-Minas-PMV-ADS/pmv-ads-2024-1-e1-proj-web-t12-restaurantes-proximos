<!DOCTYPE html>
<html lang="pt-br">

<head>
    <title>Restaurantes proximos</title>
    <link rel="stylesheet" href="login-style.css">
    
    
    
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
  
</body>
  

</html>
