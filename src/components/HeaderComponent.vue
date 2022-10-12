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

    @media screen and (max-width: 670px) {
        nav {
            .logo_header {
                width: 10%;
            }
        }
    }

    @media screen and (max-width: 450px) {
        nav {
            .logo_header {
                width: 15%;
            }
        }
    }
</style>