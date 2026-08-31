<template>
  <div class="lineas-demo">
    <div class="bg-geometry" aria-hidden="true">
      <div class="triangle triangle--top-left"></div>
      <div class="triangle triangle--top-right"></div>
      <div class="triangle triangle--bottom-left"></div>
      <div class="triangle triangle--bottom-right"></div>
      <div class="diamond"></div>
    </div>

    <section class="login-card" aria-label="Login form">
      <h1>Iniciar Sesión</h1>

      <div class="field-group">
        <input type="email" value="admin@iideaa.com" aria-label="Correo electrónico" />
      </div>

      <div class="field-group password-wrap">
        <input type="password" value="********" aria-label="Contraseña" />
        <span class="eye" aria-hidden="true">◉</span>
      </div>

      <div class="row-between">
        <label class="check-label">
          <input type="checkbox" />
          <span>Recordarme</span>
        </label>
      </div>

      <a href="#" class="link">¿Olvidaste tu contraseña?</a>

      <button type="button" class="primary-btn">Iniciar Sesión</button>

      <div class="divider">o continuar con</div>

      <div class="google-wrap">
        <button type="button" class="google-btn">G</button>
      </div>

      <p class="register-text">
        ¿No tienes una cuenta?
        <a href="#">Regístrate aquí</a>
      </p>

      <a href="#" class="back-home">← Volver al inicio</a>
    </section>
  </div>
</template>

<script setup>
// Este componente es solo visual. Puedes conectarlo a tu lógica real luego.
</script>

<style scoped>
:global(html, body, #app) {
  margin: 0;
  width: 100%;
  min-height: 100%;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  background: #dfe7ee;
}

.lineas-demo {
  position: relative;
  width: 100%;
  min-height: 100vh;
  overflow: hidden;
  background: #dfe7ee;
}

.bg-geometry {
  position: absolute;
  inset: 0;
  background: #dfe7ee;
}

.triangle {
  position: absolute;
  width: 50%;
  height: 50%;
  opacity: 0.9;
}

.triangle--top-left {
  top: 0;
  left: 0;
  background: #7c8590;
  clip-path: polygon(0 0, 100% 0, 0 100%);
}

.triangle--top-right {
  top: 0;
  right: 0;
  background: #7e8c9a;
  clip-path: polygon(100% 0, 100% 100%, 0 0);
}

.triangle--bottom-left {
  bottom: 0;
  left: 0;
  background: #7e8c9a;
  clip-path: polygon(0 0, 100% 100%, 0 100%);
}

.triangle--bottom-right {
  right: 0;
  bottom: 0;
  background: #7c8590;
  clip-path: polygon(100% 0, 100% 100%, 0 100%);
}

.diamond {
  position: absolute;
  inset: 8% 18%;
  background: rgba(245, 247, 249, 0.95);
  clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
  box-shadow: inset 0 0 0 1px rgba(0, 0, 0, 0.02);
}

.login-card {
  position: relative;
  z-index: 2;
  width: min(430px, 84vw);
  margin: 12vh auto 0;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 12px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  color: #1f2d3d;
}

.login-card h1 {
  margin: 0 0 1.2rem;
  font-size: clamp(2rem, 2.6vw, 2.8rem);
  font-weight: 400;
  letter-spacing: -0.04em;
  color: #1c2a38;
}

.field-group {
  width: 100%;
  max-width: 270px;
  margin-bottom: 0.8rem;
}

.field-group input {
  width: 100%;
  height: 42px;
  border: 1px solid #c9d5df;
  background: rgba(214, 227, 236, 0.55);
  border-radius: 4px;
  padding: 0.8rem 0.9rem;
  font-size: 1rem;
  color: #2c3d4e;
  box-sizing: border-box;
  outline: none;
}

.password-wrap {
  position: relative;
}

.password-wrap input {
  padding-right: 2.5rem;
}

.eye {
  position: absolute;
  right: 12px;
  top: 50%;
  transform: translateY(-50%);
  color: #4d6273;
  font-size: 1.1rem;
  opacity: 0.85;
}

.row-between {
  width: 100%;
  max-width: 270px;
  margin: 0.2rem 0 0.9rem;
  display: flex;
  justify-content: flex-start;
}

.check-label {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  color: #415464;
  font-size: 0.96rem;
  cursor: pointer;
}

.check-label input {
  width: 16px;
  height: 16px;
  accent-color: #6e8ca1;
}

.link,
.back-home,
.register-text a {
  color: #4d6475;
  text-decoration: none;
  font-size: 0.97rem;
}

.link {
  display: inline-block;
  margin-bottom: 1rem;
}

.primary-btn {
  width: 100%;
  max-width: 270px;
  height: 44px;
  border: 0;
  border-radius: 7px;
  background: linear-gradient(180deg, #7a93a8 0%, #6f869b 100%);
  color: #ffffff;
  font-size: 1.05rem;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(80, 97, 111, 0.2);
}

.divider {
  width: 100%;
  max-width: 270px;
  margin: 1.4rem 0 0.8rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.8rem;
  color: #5b6977;
  font-size: 0.88rem;
}

.divider::before,
.divider::after {
  content: "";
  flex: 1;
  height: 1px;
  background: rgba(96, 112, 125, 0.35);
}

.google-wrap {
  display: flex;
  justify-content: center;
  margin-bottom: 0.9rem;
}

.google-btn {
  width: 52px;
  height: 52px;
  border: 2px solid #e8edf1;
  border-radius: 50%;
  background: white;
  color: #e14d3a;
  font-size: 2rem;
  font-weight: 700;
  cursor: pointer;
  box-shadow: 0 3px 8px rgba(0, 0, 0, 0.08);
}

.register-text {
  margin: 0.3rem 0 0.8rem;
  color: #4f5f6d;
  font-size: 1rem;
  line-height: 1.6;
}

.back-home {
  display: inline-block;
  margin-top: 0.2rem;
  font-size: 1rem;
}

@media (max-width: 768px) {
  .diamond {
    inset: 10% 10%;
  }

  .login-card {
    margin-top: 18vh;
  }
}
</style>
