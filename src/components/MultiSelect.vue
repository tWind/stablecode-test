<template>
  <div class="multi-select" :class="{ 'select-filled': filled }">
    <q-select ref="multiSelect" outlined multiple use-chips v-model="model" :options="options" :label="(!filled ? 'Position' : '')" @update:model-value="testMethod3">
      <template v-if="filled" v-slot:append>
        <q-btn round dense flat icon="add" @click.stop.prevent="testMethod2()" />
      </template>
    </q-select>
  </div>
</template>

<script>
import { ref, defineComponent } from 'vue'

export default defineComponent({
  name: 'MultiSelect',
  setup () {
    return {
      model: ref(null),
      options: [
        'Options 1', 'Options 2', 'Options 3', 'Options 3.5', 'Options 4', 'Options 5', 'Options 6'
      ],
      filled: false,
    }
  },
  methods: {
    testMethod2() {
      this.$refs.multiSelect.showPopup();
    },
    testMethod3 (option) {
      this.filled = ([...this.model].length) ? true : false;
    }
  }
});
</script>

<style lang="scss">
.multi-select {
  .q-field__control {
    &:before {
      border-radius: 10px;
    }
  }

  &.select-filled {
    .q-select__dropdown-icon {
      display: none;
    }

    .q-field--auto-height.q-field--labeled .q-field__control-container {
      padding-top: 12px;
    }
  }
}
</style>
