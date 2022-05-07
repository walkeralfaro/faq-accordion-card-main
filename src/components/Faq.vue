<template>
  <div 
    :class="open ? 'faq open' : 'faq'"
    @click="$emit('toggle', index)"
  >
    <div class="question_container">
      <h2 class="question">{{ faq.question }}</h2>
      <img src="images/icon-arrow-down.svg" alt="arrow">
    </div>
    <p class="answer">{{ faq.answer }}</p>
  </div>
  <hr>
</template>

<script>
export default {
  props: ["faq", "index", "open"],
};
</script>