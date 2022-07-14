<template>
  <q-page class="flex column">
    <div class="row full-width q-gutter-md">
      <div class="col-4">
        <multi-select />
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

import MultiSelect from 'components/MultiSelect.vue'

export default defineComponent({
  name: 'IndexPage',
  components: {
    MultiSelect,
  }
})
</script>
