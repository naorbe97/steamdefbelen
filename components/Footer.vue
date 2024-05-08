<template>
    <footer class="footer">
        <div class="footer-content">
            <p>© 2024 Mi Sitio Web</p>
            <nav class="footer-nav">
                <NuxtLink to="/">Inicio</NuxtLink>
                <NuxtLink to="/acerca">Acerca de</NuxtLink>
                <NuxtLink to="/contacto">Contacto</NuxtLink>
            </nav>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style scoped>
.footer {
    background-color: #333;
    color: #fff;
    padding: 20px 0;
}

.footer-content {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.footer-content p {
    margin: 0;
}

.footer-nav {
    display: flex;
}

.footer-nav NuxtLink {
    color: #fff;
    text-decoration: none;
    margin-right: 20px;
}

.footer-nav NuxtLink:last-child {
    margin-right: 0;
}
</style>