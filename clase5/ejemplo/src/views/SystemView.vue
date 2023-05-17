<template>
  <!-- Estoy en grupo 6 -->
  <ion-page>
    <ion-content>
      <h2>System Page</h2>
      <ion-list v-for="e in lista" :key="e.cod">
        {{ e.cod }} {{ e.desc }}
      </ion-list>  
      <ion-input label="codigo" v-model="elemento.cod"></ion-input>
      <ion-input label="descripcion" v-model="elemento.desc"></ion-input>
      <ion-button @click="agregar">Agregar</ion-button>
      <ion-button @click="goToAbout" expand="full">Go to About</ion-button>
    </ion-content>  
  </ion-page>
</template>

<script>
import {IonPage, IonButton, IonInput, IonList, IonContent} from '@ionic/vue'

export default {
  components: { IonPage, IonButton, IonInput, IonList, IonContent },
  data() {
    return {
      lista: [{cod:1,desc:'Tuerca 1/2'},{cod:2,desc:'Tuerca 3/4'}],
      elemento: {}
    }
  },
  methods: {
    goToAbout() {
      this.$router.push("/about")
    },
    agregar() {
      this.lista.push({...this.elemento})
    }
  }
}
</script>

<style>

</style>