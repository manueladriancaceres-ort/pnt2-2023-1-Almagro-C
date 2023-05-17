<script>
import { IonApp, IonHeader, IonRouterOutlet } from '@ionic/vue'
import { useLoginStore} from './stores/login'
import { storeToRefs } from "pinia";

export default {
  components: { IonApp, IonHeader, IonRouterOutlet },
  setup() {
    const store = useLoginStore();
    const { isLogin, user } = storeToRefs(store)
    const { havePermissions } = store
    return { isLogin, user, havePermissions }
  }
}
</script>

<template>
  <ion-app>
    <ion-header>
      <nav>
        <RouterLink to="/">Home |</RouterLink>
        <RouterLink to="/about">About |</RouterLink>
        <RouterLink v-if="isLogin" to="/system">System |</RouterLink>
        <RouterLink v-if="isLogin && havePermissions('config')" to="/config">Config |</RouterLink>
        <RouterLink v-if="!isLogin" to="/login">Login |</RouterLink>
        <RouterLink v-if="isLogin" to="/logout">Logout |</RouterLink>
        Usuario: {{ user.email }}
      </nav>
    </ion-header>
    <ion-router-outlet />
  </ion-app>
</template>

<style>
</style>
