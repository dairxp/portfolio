<template>
  <div class="auth-animated-wrapper">
    <!-- Fondo animado -->
    <div class="auth-animated-bg">
      <div class="top"></div>
      <div class="bottom"></div>
    </div>
    
    <!-- Contenedor del contenido (login, register, etc.) -->
    <div class="auth-animated-content">
      <slot></slot> <!-- Espacio para renderizar el contenido que envuelva este componente -->
    </div>
  </div>
</template>

<script setup lang="ts">
/**
 * Componente Init.vue - Efecto animado de fondo interactivo con el mouse.
 * Extraído de la lógica original (auth-animated) de React a un componente Vue reutilizable.
 */
</script>

<style scoped>
/* Variables de color originales pasadas a CSS variables */
.auth-animated-wrapper {
  --color-bg-main: var(--bg);
  --color-accent: var(--accent);
  --color-primary-accent: var(--accent-2);
  --color-secondary: var(--text-h);
  --color-navbar-dark: var(--text);

  position: relative;
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--color-bg-main);
  overflow-x: hidden;
}

.auth-animated-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  z-index: 0;
  pointer-events: none;
}

.auth-animated-bg .top::before,
.auth-animated-bg .top::after,
.auth-animated-bg .bottom::before,
.auth-animated-bg .bottom::after {
  content: '';
  display: block;
  position: absolute;
  width: 200vmax;
  height: 200vmax;
  top: 50%;
  left: 50%;
  margin-top: -100vmax;
  margin-left: 0;
  transform-origin: 0 50%;
  transition: all 0.8s cubic-bezier(0.445, 0.05, 0, 1);
  z-index: 1;
  opacity: 0.65;
}

.auth-animated-bg .top::before { transform: rotate(45deg); background: var(--color-accent); }
.auth-animated-bg .top::after { transform: rotate(135deg); background: var(--color-primary-accent); }
.auth-animated-bg .bottom::before { transform: rotate(-45deg); background: var(--color-secondary); }
.auth-animated-bg .bottom::after { transform: rotate(-135deg); background: var(--color-navbar-dark); }

.auth-animated-content {
  position: relative;
  z-index: 10;
  width: 100%;
  max-width: 600px;
  padding: 30px;
  opacity: 0;
  transform: scale(0.95);
  transition: all 0.5s cubic-bezier(0.445, 0.05, 0, 1);
  transition-delay: 0s;
}

/* ESTADO ACTIVO (Hover en PC) */
@media (hover: hover) and (pointer: fine) {
  .auth-animated-bg .top::before,
  .auth-animated-bg .top::after,
  .auth-animated-bg .bottom::before,
  .auth-animated-bg .bottom::after {
    transition: all 0.5s cubic-bezier(0.445, 0.05, 0, 1) 0.5s; /* Retraso al cerrar */
  }
  
  .auth-animated-content {
    transition: all 0.5s cubic-bezier(0.445, 0.05, 0, 1) 0.3s;
  }

  .auth-animated-wrapper:hover .auth-animated-bg .top::before,
  .auth-animated-wrapper:hover .auth-animated-bg .top::after,
  .auth-animated-wrapper:hover .auth-animated-bg .bottom::before,
  .auth-animated-wrapper:hover .auth-animated-bg .bottom::after,
  .auth-animated-wrapper:active .auth-animated-bg .top::before,
  .auth-animated-wrapper:active .auth-animated-bg .top::after,
  .auth-animated-wrapper:active .auth-animated-bg .bottom::before,
  .auth-animated-wrapper:active .auth-animated-bg .bottom::after {
    margin-left: 900px; /* Mayor espacio central */
    transform-origin: -900px 50%;
    transition-delay: 0s;
  }
  
  .auth-animated-wrapper:hover .auth-animated-content,
  .auth-animated-wrapper:active .auth-animated-content {
    opacity: 1;
    transform: scale(1);
    transition-delay: 0.2s;
  }
}

/* Animaciones de entrada para móviles */
@keyframes mobileOpenShapes {
  0% {
    margin-left: 0;
    transform-origin: 0 50%;
  }
  100% {
    margin-left: 900px; /* Mayor espacio central */
    transform-origin: -900px 50%;
  }
}

@keyframes mobileShowContent {
  0% {
    opacity: 0;
    transform: scale(0.95);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* En Móviles (Sin hover), mostramos todo por defecto con una animación de entrada */
@media (hover: none) or (max-width: 768px) {
  .auth-animated-bg .top::before,
  .auth-animated-bg .top::after,
  .auth-animated-bg .bottom::before,
  .auth-animated-bg .bottom::after {
    animation: mobileOpenShapes 0.8s cubic-bezier(0.445, 0.05, 0, 1) forwards;
  }

  .auth-animated-content {
    opacity: 0;
    transform: scale(0.95);
    animation: mobileShowContent 0.8s cubic-bezier(0.445, 0.05, 0, 1) 0.2s forwards;
  }
}
</style>
