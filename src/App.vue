<template>
<ion-app>
    <ion-split-pane >
      <ion-menu type="overlay">
        <ion-content>
          <ion-list id="inbox-list">
            <ion-list-header>Hola</ion-list-header>
            <ion-note>Espero que la clase de hoy sea estupenda {{ dato }} </ion-note>

            <ion-menu-toggle auto-hide="false" >
             <ion-item @click="checked()"  lines="none" detail="false" class="hydrated" >
                <ion-icon slot="start" :icon="homeOutline"></ion-icon>
                <ion-label>Home</ion-label>
              </ion-item>
              <ion-item  lines="none" class="hydrated" >
                <ion-icon slot="start" :icon="peopleOutline"></ion-icon>
                <ion-label>Grupo</ion-label>
              </ion-item>
              <ion-item  lines="none"  class="hydrated" >
                <ion-icon slot="start" :icon="helpCircleOutline"></ion-icon>
                <ion-label>Cuestionarios</ion-label>
              </ion-item>
            </ion-menu-toggle>
          </ion-list>

        </ion-content>
      </ion-menu>
      <ion-router-outlet id="main-content"></ion-router-outlet>
    </ion-split-pane>
  </ion-app>
  <ion-page>

  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonPage, IonIcon, IonItem, IonLabel, IonList, IonListHeader, IonMenu, IonMenuToggle, IonNote, IonRouterOutlet, IonSplitPane } from '@ionic/vue';
import { defineComponent, ref } from 'vue';
import { peopleOutline, homeOutline, helpCircleOutline } from 'ionicons/icons';
export default defineComponent({
  name: 'App',
  components: {
    IonPage,
    IonContent, 
    IonIcon, 
    IonItem, 
    IonLabel, 
    IonList, 
    IonListHeader, 
    IonMenu, 
    IonMenuToggle, 
    IonNote, 
    IonRouterOutlet, 
    IonSplitPane,
  },
    
  setup() {
   const data = ref('holi')
   const checked = async () => {
        data.value = 'nada'
        };
    return { 
      dato: data,
      checked,
      peopleOutline, 
      homeOutline,
      helpCircleOutline
    }
  }
});
</script>

<style scoped>
ion-menu ion-content {
  --background: var(--ion-item-background, var(--ion-background-color, #fff));
}
ion-menu.md ion-content {
  --padding-start: 8px;
  --padding-end: 8px;
  --padding-top: 20px;
  --padding-bottom: 20px;
}
ion-menu.md ion-list {
  padding: 20px 0;
}
ion-menu.md ion-note {
  margin-bottom: 30px;
}
ion-menu.md ion-list-header,
ion-menu.md ion-note {
  padding-left: 10px;
}
ion-menu.md ion-list#inbox-list {
  border-bottom: 1px solid var(--ion-color-step-150, #d7d8da);
}
ion-menu.md ion-list#inbox-list ion-list-header {
  font-size: 22px;
  font-weight: 600;
  min-height: 20px;
}
ion-menu.md ion-list#labels-list ion-list-header {
  font-size: 16px;
  margin-bottom: 18px;
  color: #757575;
  min-height: 26px;
}
ion-menu.md ion-item {
  --padding-start: 10px;
  --padding-end: 10px;
  border-radius: 4px;
}
ion-menu.md ion-item.selected {
  --background: rgba(var(--ion-color-primary-rgb), 0.14);
}
ion-menu.md ion-item.selected ion-icon {
  color: var(--ion-color-primary);
}
ion-menu.md ion-item ion-icon {
  color: #616e7e;
}
ion-menu.md ion-item ion-label {
  font-weight: 500;
}
ion-menu.ios ion-content {
  --padding-bottom: 20px;
}
ion-menu.ios ion-list {
  padding: 20px 0 0 0;
}
ion-menu.ios ion-note {
  line-height: 24px;
  margin-bottom: 20px;
}
ion-menu.ios ion-item {
  --padding-start: 16px;
  --padding-end: 16px;
  --min-height: 50px;
}
ion-menu.ios ion-item.selected ion-icon {
  color: var(--ion-color-primary);
}
ion-menu.ios ion-item ion-icon {
  font-size: 24px;
  color: #73849a;
}
ion-menu.ios ion-list#labels-list ion-list-header {
  margin-bottom: 8px;
}
ion-menu.ios ion-list-header,
ion-menu.ios ion-note {
  padding-left: 16px;
  padding-right: 16px;
}
ion-menu.ios ion-note {
  margin-bottom: 8px;
}
ion-note {
  display: inline-block;
  font-size: 16px;
  color: var(--ion-color-medium-shade);
}
ion-item.selected {
  --color: var(--ion-color-primary);
}
</style>
