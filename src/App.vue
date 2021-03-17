<template>
<div>
  <InputText v-model="text" />
  <Button label="Greetings" icon="pi pi-user" @click="greet"></Button>
  <Toast />
  {{text}}
</div>
</template>

<script>
import {defineComponent, ref} from 'vue';
import {useToast} from 'primevue/usetoast';

export default defineComponent({
  setup(){
    const toast = useToast();
    const text = ref('Prime');
    const greet = () => {
      toast.add({severity:'info', summary: 'Hello', detail: text, life: 3000});
    }
    return {
      text,
      greet
    }
  }
})
/* export default {
  data(){
    return {
      text: null
    }
  },
  methods: {
    greet(){
      this.$toast.add({severity:'info', summary: 'Hello', detail:this.text, life: 3000});
    }
  }
} */
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
