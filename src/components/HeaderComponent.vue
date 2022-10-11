<template>
    <nav>
        <div>
            <img class="logo_header" src="@/assets/img/logo.svg" alt="ACME">
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
        width: 100%;
        overflow-x: none;
        
        .logo_header {
            width: 5.5vw;
            margin: 0.7rem 0 0 2.5rem;
        }
    }
</style>