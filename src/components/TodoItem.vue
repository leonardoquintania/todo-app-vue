<template>
  <InputText v-model="description" />
  <div class="div-buttons">
    <Button @click="cancel" class="div-voltar">Voltar</Button>
    <Button @click="saveTodo">Salvar</Button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      description: '',
    };
  },
  props: {
    todo: Object,
  },
  created() {
    this.description = this.todo?.description;
  },
  methods: {
    cancel() {
      this.$emit('cancel');
    },
    saveTodo() {
      this.$emit('saveTodo', { ...this.todo, description: this.description });
    },
  },
};
</script>

<style scoped>
.div-buttons {
  margin-top: 1rem;
}

.div-voltar {
  margin-right: 1rem;
}
</style>
