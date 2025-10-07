<template>
  <div class="login-container">
    <div class="logo">LOGO</div>

    <form @submit.prevent="handleLogin" class="login-form">
      <input
        type="email"
        v-model="email"
        placeholder="Email"
        required
      />
      <input
        type="password"
        v-model="senha"
        placeholder="Senha"
        required
      />
      <button type="submit">Login</button>
    </form>

    <div class="links">
      <p>Não tem conta? <a href="#" @click.prevent="cadastreSe">Cadastre-se</a></p>
      <p>Esqueceu a senha? <a href="#" @click.prevent="recuperarSenha">Recuperar</a></p>
    </div>

    <div class="social-login">
      <button @click="loginGoogle">G</button>
      <button @click="loginFacebook">f</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "LoginPage",
  data() {
    return {
      email: "",
      senha: "",
    };
  },
  methods: {
    handleLogin() {
      console.log("Email:", this.email);
      console.log("Senha:", this.senha);
      // Aqui você adicionaria a lógica de login
    },
    cadastreSe() {
      console.log("Redirecionar para cadastro");
    },
    recuperarSenha() {
      console.log("Redirecionar para recuperação de senha");
    },
    loginGoogle() {
      console.log("Login com Google");
    },
    loginFacebook() {
      console.log("Login com Facebook");
    },
  },
};
</script>

<style scoped>
.login-container {
  max-width: 400px;
  margin: 50px auto;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  background-color: #fff;
  text-align: center;
}

.logo {
  font-size: 32px;
  font-weight: bold;
  margin-bottom: 30px;
}

.login-form input {
  width: 100%;
  padding: 12px;
  margin: 10px 0;
  border-radius: 6px;
  border: 1px solid #ccc;
  font-size: 16px;
}

.login-form button {
  width: 100%;
  padding: 12px;
  margin-top: 15px;
  border: none;
  border-radius: 6px;
  background-color: #ccc;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}

.login-form button:hover {
  background-color: #bbb;
}

.links p {
  margin: 10px 0;
  font-size: 14px;
}

.links a {
  color: #007bff;
  text-decoration: underline;
  cursor: pointer;
}

.social-login {
  margin-top: 20px;
}

.social-login button {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin: 0 10px;
  border: none;
  font-size: 24px;
  cursor: pointer;
  background-color: #eee;
}

.social-login button:hover {
  background-color: #ddd;
}
</style>
