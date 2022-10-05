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
        overflow-x: none;
        
        .logo_header {
            width: 7vw;
            margin: 0.7rem 0 0.5rem 5.5rem;
        }
    }
</style>