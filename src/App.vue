<template>
  <div id="app">
      <HeaderComponent />
      <HeroComponent />
      <StrongPoints :links="strongPoints" />
      <CalculatorComponent :buttons="buttons" @tableActive="tableActive"/>
      <ServiciesComponent :servicies="servicies" />
      <FooterComponent />
  </div>
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue';
import HeroComponent from '@/components/HeroComponent.vue';
import StrongPoints from '@/components/StrongPoints.vue';
import CalculatorComponent from '@/components/CalculatorComponent.vue';
import ServiciesComponent from '@/components/ServiciesComponent.vue';
import FooterComponent from '@/components/FooterComponent.vue';

// Data
import strongPoints from "@/assets/data/strongPoints";
import servicies from "@/assets/data/servicies";
import buttons from "@/assets/data/buttons";


export default {
  name: 'App',
  data() {
    return {
      strongPoints,
      servicies, 
      buttons,
      tableOpen: false,
    };
  },
  components: { 
    HeroComponent, 
    HeaderComponent, 
    StrongPoints, 
    CalculatorComponent, 
    ServiciesComponent,
    FooterComponent
  }, 
  methods: {
    tableActive(bool) {
      this.tableOpen = bool
    },
  }
}
</script>


<style lang="scss">
@import '@/styles/general';
@import '@/styles/vars.scss';


#app {
  width: 100vw;
  overflow-x: none !important;
  margin: 0!important;

  .red_btn,
  .red_button,
  .transp_btn {
    cursor: pointer;
  }

}
</style>
