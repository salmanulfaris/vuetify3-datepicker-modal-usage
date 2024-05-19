# vuetify3-datepicker-modal-usage
Short Demo of How to use Vuetify 3 Datepicker with Modal 
```

<template>
  <v-app>
    <v-container>
      <v-dialog v-model="display">
        <template #activator="{ props }">
          <v-text-field
            v-bind="props"
            prepend-icon="mdi-calendar"
            :model-value="formatted"
            readonly
          />
        </template>

        <template #default>
          <v-date-picker v-model="date" @update:model-value="display = false" />
        </template>
      </v-dialog>
    </v-container>
  </v-app>
</template>

<script setup>
  import { ref, computed } from 'vue'
  // import { padStart } from 'lodash-es'

  const display = ref(false)

  const date = ref(new Date())

  const formatted = computed(() => {
    // const year = date.value.getFullYear()
    // const month = padStart(String(date.value.getMonth() + 1), 2, '0')
    // const day = padStart(String(date.value.getDate()), 2, '0')

    // return `${day}/${month}/${year}`

    return date.value.toLocaleDateString()
  })
</script>


```
