<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
import M from 'materialize-css'

export default {
  created() {
    M.AutoInit()
  }
}
</script>
