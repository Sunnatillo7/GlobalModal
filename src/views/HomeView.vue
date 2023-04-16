<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6">
        <appModal v-model="dialog">
          <h1>salom</h1>
        </appModal>
        <button @click="dialog = true">open modal</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useStore } from 'vuex'
import { onMounted, ref } from 'vue';
import appModal from '@/components/ui/app-modal.vue';
import { mapGetters } from 'vuex';
import { computed ,watch} from 'vue';
const store = useStore()
const count = computed(() => store.getters.getCounter)
const auth = computed(() => store.getters.getAuth)
const dialog = ref(false)
const myAction = () => {
  store.dispatch('addCounter')
}
onMounted(()=>{
  // store.dispatch('getTodos')
})

</script>
