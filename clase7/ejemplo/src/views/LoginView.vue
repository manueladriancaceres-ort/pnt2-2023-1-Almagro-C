<template>
  <ion-page>
    <ion-content>
      <h2>Login</h2>
      <ion-input v-model="usuario.email" label="email" type="email"></ion-input>
      <ion-input
        v-model="usuario.passw"
        label="password"
        type="password"
      ></ion-input>
      <ion-button @click="logear">Login</ion-button>
    </ion-content>
  </ion-page>
</template>

<script>
import { IonPage, IonButton, IonContent, IonInput } from "@ionic/vue";
import { useLoginStore } from "../stores/login";

export default {
  components: { IonPage, IonButton, IonContent, IonInput },
  setup() {
    const { login } = useLoginStore(); 
    return { login };
  },
  data() {
    return {
      usuario: { email: "", passw: "" },
    };
  },
  methods: {
    logear() {
      // consultar api  (proxima clase)
      // hardcodeo
      if (
        this.usuario.email == "usuario@test.com" &&
        this.usuario.passw == "123456"
      ) {
        this.login({email:this.usuario.email, permissions:[]})
        this.$router.push("/system");
      } else if ( 
        this.usuario.email == "admin@test.com" &&
        this.usuario.passw == "123456"
      ) {
        this.login({email:this.usuario.email, permissions:['config']})
        this.$router.push("/");
      } else {
        alert("Credenciales erroneas");
      }
    },
  },
};
</script>


<style>
</style>
