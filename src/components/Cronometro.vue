<template>
  <section>
    <strong class="display">
      {{ tempoDecorrido }}
    </strong>
  </section>
</template>


<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CronometroLegal',
  props: {
    tempoEmSegundos: {
      type: Number,
      default: 0,
    }
  },
  computed: {
    tempoDecorrido () : string {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8)  // new Date().toISOString() = '2022-09-29T20:01:32.157Z'  new Date().toISOString().substr(11,8) = '20:01:32'

    }
  },
})
</script>

<style scoped>
  .display {
    color: var(--texto-primario);
  }
</style>
