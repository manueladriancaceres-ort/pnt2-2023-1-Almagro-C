<template>
  <ion-page>
    <ion-content>
      <h2>System Page</h2>
      <ion-list v-for="e in lista" :key="e.cod">
        {{ e.id }} {{ e.descripcion }}
        <ion-button @click="eliminar(e.id)">Eliminar</ion-button>
        <ion-button @click="modificar(e.id)">Modificar</ion-button>
      </ion-list>  
      <ion-input label="codigo" v-model="elemento.id"></ion-input>
      <ion-input label="descripcion" v-model="elemento.descripcion"></ion-input>
      <ion-button @click="agregar">Agregar</ion-button>
      <ion-button @click="cargarLista">Cargar Lista </ion-button>
    </ion-content>  
  </ion-page>
</template>

<script>
import {IonPage, IonButton, IonInput, IonList, IonContent} from '@ionic/vue'
import listaService from '../service/listaService'

export default {
  components: { IonPage, IonButton, IonInput, IonList, IonContent },
  data() {
    return {
      lista: [],
      elemento: {}
    }
  },
  mounted() {
    this.cargarLista()
  },
  methods: {
    goToAbout() {
      this.$router.push("/about")
    },
    async cargarLista() {
      try {
        this.lista = await listaService.cargar()
      } catch ( error) {
        alert( error )
      }
    },
    async agregar() {
      const elem = {...this.elemento}
      try {
        await listaService.agregar(elem) 
        this.cargarLista()
      } catch( error ) {
        alert('Se produjo un error de conexion')
      }
    },
    async eliminar(id) {
      try {
        await listaService.eliminar(id) 
        this.cargarLista()
      } catch( error ) {
        alert('Se produjo un error de conexion')
      }
    },
    async modificar(id) {
      const elem = {...this.elemento}
      try {
        await listaService.modificar(id,elem) 
        this.cargarLista()
      } catch( error ) {
        alert('Se produjo un error de conexion')
      }
    }

  }
}
</script>

<style>

</style>