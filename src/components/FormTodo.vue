<template>
  <div class="form-todo form-group">
    <p>
        <input v-model="name" type="text" class="form-control" name="author" placeholder="Nome">
    </p>
    <p>
        <textarea v-model="message" name="message" class="form-control" placeholder="Comentário"></textarea>
    </p>
    <p>
    <button v-on:click="addComment" type="submit" class="btn btn-primary">Comentar</button>      
    </p>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        name: '',
        message: ''
      }
    },
    methods: {
      addComment() {
        if(this.message.trim() === ''){
          return;
        }       

        this.$emit('add-todo',{
          name: this.name,
          message: this.message
        });

        this.name = '';
        this.message = '';
      },  
    }
  }
</script>
