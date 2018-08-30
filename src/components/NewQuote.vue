<template>
  <div class="row pt-3">
    <form class="col-12">
      <div class="form-group col-sm-8 col-xs-12 col-md-6 col-offset-2">
        <label>Цитата</label>
        <textarea
          class="form-control"
          rows="3"
          v-model="quote"
        ></textarea>
      </div>
      <div class="form-group col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button
          class="btn btn-primary"
          @click.prevent="createNew"
        >Добавить цитату</button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    data () {
      return  {
        quote: ''
      }
    },
    methods: {
      createNew () {
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
      }
    }
  }
</script>

<style scoped>

</style>
