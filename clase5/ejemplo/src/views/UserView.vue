<template>
  <ion-page>
    <h2>User page</h2>
    {{ $route.params.id }}
  </ion-page>
</template>

<script>
  import {IonPage} from '@ionic/vue'
  export default {
    components: { IonPage }
  }
</script>

<style>

</style>