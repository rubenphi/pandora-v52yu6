<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-menu-button color="primary"></ion-menu-button>
        </ion-buttons>
        <ion-title>Pandora</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Pandora</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <div id="container">
        <strong class="capitalize">Bienvenido a Pandora</strong>
        <p>La aplicación fue diseñada para permitir la participación simultanea y por grupos para la asignatura de lengua castellana. 

          {{contador}}
        </p>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonButtons, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { defineComponent } from 'vue';


export default defineComponent({
  components: {
    IonButtons,
    IonContent,
    IonHeader,
    IonMenuButton,
    IonPage,
    IonTitle,
    IonToolbar
  },
    setup() {
   let checked = 'Grupo';
    return { 
      contador: 0,
    }
  },
  methods:{
    ionViewDidEnter() {
    setInterval(()=>{
      this.contador ++;
    }, 1000)
    console.log(this.contador);
  },
  ionViewDidLeave() {
    console.log('Home page did leave');
  },
  ionViewWillEnter() {
   console.log(this.contador);
  },
  ionViewWillLeave() {
    console.log('Home page will leave');
  }
  }
});
</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
