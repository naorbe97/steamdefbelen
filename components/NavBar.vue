<template>
  <nav class="navbar">
    <div class="navbar-left">
      <NuxtLink to="/"><img src="/logo.png" alt="Logo" class="logo"></NuxtLink>
    </div>
    <div class="navbar-center">
      <NuxtLink to="/tienda" :class="{ 'nav-link': $route.path !== '/pagina1', 'nav-link-bold': $route.path === '/pagina1' }">Tienda</NuxtLink>
      <NuxtLink to="/soporte" :class="{ 'nav-link': $route.path !== '/pagina1', 'nav-link-bold': $route.path === '/pagina1' }">Soporte</NuxtLink>
    </div>
    <div class="navbar-right">
      <button class="icon-button">
        <!-- Icono -->
      </button>
      <button class="login-button" @click="openModal"><!-- <Icon name="line-md:account" size="2em" color="black"></Icon> -->Iniciar Sesión</button>
      <NuxtLink to="/install" class="install-button">Instalar steam</NuxtLink>
    </div>
    <!-- Aquí añadimos el modal -->
    <LoginModal v-if="showModal" @close="closeModal" @openSignupModal="openSignupModal" />
    <!-- Aquí añadimos el modal de registro -->
    <SignupModal v-if="showSignupModal" @close="closeSignupModal" />
  </nav>
</template>

<script>
import LoginModal from '~/components/LoginModal.vue'; // Importar el componente modal
import SignupModal from '~/components/SignupModal.vue'; // Importar el componente de registro

export default {
  name: 'Navbar',
  components: {
    LoginModal,
    SignupModal
  },
  data() {
    return {
      showModal: false,
      showSignupModal: false
    };
  },
  methods: {
    openModal() {
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
    openSignupModal() {
      this.showSignupModal = true;
    },
    closeSignupModal() {
      this.showSignupModal = false;
    }
  }
}
</script>

<style lang="postcss" scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}

.navbar-left {
  display: flex;
  align-items: center;
}

.navbar-center {
  display: flex;
  gap: 40px;
}

.navbar-right {
  display: flex;
}

.logo {
  width: 50px;
}

.nav-link {
  color: #000;
  text-decoration: none;
  margin-right: 20px;
}

.nav-link-bold {
  font-weight: 300;
}

.icon-button {
  background-color: transparent;
  border: none;
  cursor: pointer;
  padding: 5px;
  color: #000;
}

.install-button {
  background-color: #E6E6E6;
  border-radius: 50px;
  color: #6C6C6C;
  border: none;
  cursor: pointer;
  padding: 10px 20px;
  margin-left: 10px;
}

.install-button:hover {
  background-color: #909090;
}
</style>
