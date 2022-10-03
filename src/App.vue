<template>
  <div id="app">
      <HeaderComponent />
      <HeroComponent />
      <StrongPoints />
      <CalculatorComponent />
      <ServiciesComponent />
      <FooterComponent />
  </div>
</template>

<script>
import HeroComponent from '@/components/HeroComponent.vue';
import HeaderComponent from '@/components/HeaderComponent.vue';
import StrongPoints from '@/components/StrongPoints.vue';
import CalculatorComponent from '@/components/CalculatorComponent.vue';
import ServiciesComponent from '@/components/ServiciesComponent.vue';
import FooterComponent from '@/components/FooterComponent.vue';


export default {
  name: 'App',
  components: { 
    HeroComponent, 
    HeaderComponent, 
    StrongPoints, 
    CalculatorComponent, 
    ServiciesComponent,
    FooterComponent
  }
}
</script>


<style lang="scss">
@import '@/styles/general';

#app {

}
</style>
