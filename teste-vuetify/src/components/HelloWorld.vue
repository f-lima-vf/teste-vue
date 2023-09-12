<template>
  <v-container class="fill-height">
    <v-responsive class="align-center text-center fill-height">
      <div>Teste Vue</div>
      <v-data-table
        :headers="headers"
        :items="indicios"
        class="elevation-1"
        select-strategy="page"
        show-select
        multi-sort
        :sort-by="[{key: 'nome', order: 'asc'}]"
        :items-per-page="3"
      >
        <template v-slot:item.id="{ item }">
          <span>{{ item.raw.id }}</span>
        </template>
        <template v-slot:item.nome="{ item }">
          <span>{{ item.raw.nome }}</span>
        </template>
      </v-data-table>
    </v-responsive>
  </v-container>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { VDataTable } from 'vuetify/labs/VDataTable'

type Headers = InstanceType<typeof VDataTable>['headers']


export default defineComponent({
  name: 'HelloWorld',
  components: {
    VDataTable,
  },
  setup() {
    const indicios = ref([{id: 1, nome: 'A'}, {id: 2, nome: 'B'}, {id: 3, nome: 'C'}, {id: 4, nome: 'D'}, {id: 5, nome: 'E'}, {id: 6, nome: 'F'}])
    const selected_indicios= ref([])
    const headers: Headers = [
      { title: 'id', align: 'center', key: 'id' },
      { title: 'nome', align: 'center', key: 'nome' },
    ]
    
    return {
      indicios,
      selected_indicios,
      headers,
    }
  },
})
</script>
