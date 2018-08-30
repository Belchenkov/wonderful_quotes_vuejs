<template>
    <div v-if="quoteCount" class="mt-4">
      <div class="progress">
        <div
          :style="{width: (quoteCount/maxQuotes) * 100 + '%' }"
          class="progress-bar"
          role="progressbar"
          aria-valuenow="0"
          aria-valuemin="0"
          aria-valuemax="100"
        >
          {{ quoteCount }} / {{ maxQuotes }}
        </div>
      </div>
    </div>
</template>

<script>
    export default {
      props: [
        'quoteCount',
        'maxQuotes'
      ]
    }
</script>

<style scoped>

</style>
