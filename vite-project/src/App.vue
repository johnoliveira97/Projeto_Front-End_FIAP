<script setup>
import Input from '../src/Input.vue'

</script>

<template id="app">
  <div>
    <div>
      <a class="header-logo" href="https://github.com/" aria-label="Homepage" data-ga-click="(Logged out) Header, go to homepage, icon:logo-wordmark">
        <svg height="40" viewBox="0 0 16 16" width="40" data-view-component="true" class="octicon octicon-mark-github">
          <path d="M8 0c4.42 0 8 3.58 8 8a8.013 8.013 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38 0-.27.01-1.13.01-2.2 0-.75-.25-1.23-.54-1.48 1.78-.2 3.65-.88 3.65-3.95 0-.88-.31-1.59-.82-2.15.08-.2.36-1.02-.08-2.12 0 0-.67-.22-2.2.82-.64-.18-1.32-.27-2-.27-.68 0-1.36.09-2 .27-1.53-1.03-2.2-.82-2.2-.82-.44 1.1-.16 1.92-.08 2.12-.51.56-.82 1.28-.82 2.15 0 3.06 1.86 3.75 3.64 3.95-.23.2-.44.55-.51 1.07-.46.21-1.61.55-2.33-.66-.15-.24-.6-.83-1.23-.82-.67.01-.27.38.01.53.34.19.73.9.82 1.13.16.45.68 1.31 2.69.94 0 .67.01 1.3.01 1.49 0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8Z"></path>
        </svg>
      </a>
    </div>
    <div>
      <h1 class="titulo">Sign in to GitHub</h1>
    </div>
    <div class="boxes">
      <form name="login-form" action="/login" method="POST">
        <label class="username">e-mail address
          <Input type="email" 
          name="email"
          v-model="email"
          placeholder="E-mail"/> {{ email }}
        </label>
        <div class="pwd-wrapper">
          <label for="pwd">Password</label>
          <Input 
          v-model="password"
          name="password"
          type="password"
          icon="lock"
          :errors="errors.password"
          placeholder="Senha"
          class="password" />
          <a href="#" class="forget-pwd">Forgort password?</a>
        </div>
        <button class="botao">Sign in</button>
      </form>
    </div>
  </div>
</template>

<style scoped>

.titulo {
 color: black;
 font-size:20px;
 background:#cde;
}

#app {
  display:flex;
}

.boxes {
  background:#eee;
  border-radius: 4px;
  padding: 20px;
  width:240px;
  text-align: left;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.username {
  margin-top: 24px;
}
.pwd-wrapper{
  margin-bottom: 24px;
  position: relative;
}
.forget-pwd{
  position: absolute;
  right:0;
  top:0;
  font-size:12px;
}
.input{
  padding: 4px;
  width: 100%;
}
.botao{
  padding: 8px 12px;
  text-align:center;
  align:center;
  margin-left:80px;
  background:green;
}
</style>
