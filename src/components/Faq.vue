<template>
  <div 
    :class="open ? 'faq open' : 'faq'"
    @click="$emit('toggle', index)"
  >
    <h3 class="question">{{ faq.question }}</h3>
    <p class="answer">{{ faq.answer }}</p>
  </div>
</template>

<script>
export default {
  props: ["faq", "index", "open"],
};
</script>