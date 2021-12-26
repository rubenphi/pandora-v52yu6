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
    

        <strong class="capitalize">Bienvenido a Pandora</strong>
        <p>La aplicación fue diseñada para permitir la participación simultanea y por grupos para la asignatura de lengua castellana. 

          <ion-button (click)="increment">añadir</ion-button>

          
    {{ count }}
        </p>
     
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonButton, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { defineComponent } from 'vue';


export default defineComponent({
  components: {
    IonButton,
    IonContent,
    IonHeader,
    IonMenuButton,
    IonPage,
    IonTitle,
    IonToolbar
  },
  
    setup() {
      
    return { 
      count: 0
    }
  },
  methods:{
   increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    },
   ionViewWillEnter() {
      setInterval( () => console.log(this.count), 1000 );
  },
    
    ionViewDidEnter() {
   // setInterval( () => console.log(this.contador ++) , 1000 );
  },
  ionViewDidLeave() {
    console.log('Home page did leave');
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
