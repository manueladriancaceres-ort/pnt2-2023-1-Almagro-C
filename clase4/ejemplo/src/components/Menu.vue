<!-- break hasta 21:20-->

<template>
  <div>
    <h2>Jugadores de Boca</h2>
    <li v-for="jug in jugadores" :key="jug.nro">
      {{ jug.nro }} {{ jug.nombre }}
    </li>
    <Jugador @agregoJugador="agregarJugador"/>
  </div>
</template>

<script>
import Jugador from './Jugador.vue'
export default {
  components: {Jugador},
  data() { 
    return {
      jugadores: [{nro:1,nombre:'Dibu'},{nro:5,nombre:'Varela'},{nro:10,nombre:'Romero'}],
    }
  },
  methods: {
    agregarJugador(jugador) {
      this.jugadores.push(jugador)
    }
  }
}
</script>

<style>

</style>