<template>
  <div>
    <h2>Agregar Jugadores</h2>
    Nro: <input type="number" v-model="jugador.nro">
    Nombre: <input type="text" v-model="jugador.nombre">
    <br/>
    <button @click="agregarJugador">Agregar jugador</button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            jugador: {}
        }
    },
    methods: {
        agregarJugador() {
            this.$emit('agregoJugador',{...this.jugador})
        }
    }
}
</script>

<style>

</style>