<script>
import {IonApp, IonHeader, IonRouterOutlet } from '@ionic/vue'
export default {
  components: { IonApp, IonHeader, IonRouterOutlet }
}
</script>

<template>
  <ion-app>
    <ion-header>
      <nav>
        <RouterLink to="/">Home |</RouterLink>
        <RouterLink to="/about">About |</RouterLink>
        <RouterLink to="/system">System</RouterLink>
      </nav>
    </ion-header>
    <ion-router-outlet />
  </ion-app>
</template>

<style>
</style>
