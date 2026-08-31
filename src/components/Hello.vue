<script setup lang="ts">
// Componente de error 404 animado
</script>

<template>
  <div class="hello-wrapper">
    <div title="404" class="glitch-text">404</div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Fira+Mono:400');

/* Contenedor principal (reemplaza al body del ejemplo original) */
.hello-wrapper {
  display: flex;
  width: 100vw;
  height: 100vh;
  align-items: center;
  justify-content: center;
  margin: 0;
  background: #131313;
  color: #fff;
  font-size: 96px;
  font-family: 'Fira Mono', monospace;
  letter-spacing: -7px;
  
  /* Para que ocupe toda la pantalla independientemente de dónde se coloque */
  position: absolute;
  top: 0;
  left: 0;
  z-index: 9999;
}

/* Efecto principal */
.glitch-text {
  animation: glitch 1s linear infinite;
  position: relative;
}

@keyframes glitch {
  2%, 64% {
    transform: translate(2px, 0) skew(0deg);
  }
  4%, 60% {
    transform: translate(-2px, 0) skew(0deg);
  }
  62% {
    transform: translate(0, 0) skew(5deg); 
  }
}

.glitch-text:before,
.glitch-text:after {
  content: attr(title);
  position: absolute;
  left: 0;
}

/* Parte superior del glitch */
.glitch-text:before {
  animation: glitchTop 1s linear infinite;
  clip-path: polygon(0 0, 100% 0, 100% 33%, 0 33%);
  -webkit-clip-path: polygon(0 0, 100% 0, 100% 33%, 0 33%);
}

@keyframes glitchTop {
  2%, 64% {
    transform: translate(2px, -2px);
  }
  4%, 60% {
    transform: translate(-2px, 2px);
  }
  62% {
    transform: translate(13px, -1px) skew(-13deg); 
  }
}

/* Parte inferior del glitch */
.glitch-text:after {
  animation: glitchBotom 1.5s linear infinite;
  clip-path: polygon(0 67%, 100% 67%, 100% 100%, 0 100%);
  -webkit-clip-path: polygon(0 67%, 100% 67%, 100% 100%, 0 100%);
}

@keyframes glitchBotom {
  2%, 64% {
    transform: translate(-2px, 0);
  }
  4%, 60% {
    transform: translate(-2px, 0);
  }
  62% {
    transform: translate(-22px, 5px) skew(21deg); 
  }
}
</style>
