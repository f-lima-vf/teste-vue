<script>
import { ref } from 'vue';
import { VDataTable } from 'vuetify/labs/VDataTable'

export default {
  name: 'HelloWorld',
  components: {
    VDataTable,
  },
  props: {
    indicios: {
      default: ref([{id: 1, nome: 'A'}, {id: 2, nome: 'B'}, {id: 3, nome: 'C'}])
    },
    selected_indicios: {
      default: ref([])
    },
    headers: {
      default: ref(['id', 'nome'])
    }
  }
}
</script>
