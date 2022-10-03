<template>
    <nav>
        <div>
            <img class="logo_header" src="@/assets/logo.svg" alt="ACME">
        </div>
    </nav>
</template>

<script>
export default {
    name: 'HeaderComponent'
}
</script>

<style lang="scss" scoped>
nav {
    width: 100vw;
    .logo_header {
        width: 5vw;
        margin-left: 1.1rem;
    }
}
</style>