<template>
  <div id="app">
      <HeaderComponent />
      <HeroComponent />
      <StrongPoints :links="strongPoints" />
      <CalculatorComponent />
      <ServiciesComponent :servicies="servicies" />
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

// Data
import strongPoints from "@/assets/data/strongPoints";
import servicies from "@/assets/data/servicies";


export default {
  name: 'App',
  data() {
    return {
      strongPoints,
      servicies,
    };
  },
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
@import '@/styles/vars.scss';


#app {

}
</style>
