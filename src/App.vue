<template>

<main class="container">
  <div class="flex">
    <div class="grid">

      <article class="illustration">
        <img class="cube" src="images/illustration-box-desktop.svg" alt="@_cube">
        <div class="women-container">
            <img class="women desktop" src="images/illustration-woman-online-desktop.svg" alt="women_illustration">
            <img class="women mobile" src="images/illustration-woman-online-mobile.svg" alt="women_illustration">
        </div>
      </article>

      <article class="faq_container">
        <h1>FAQ</h1>
        <div class="faqs">
          <Faq
            v-for="(faq, i) in faqs" 
            :faq="faq"
            :index="i"
            :key="i"
            :open="faq.open"
            @toggle="toggleOpen"
          />
        </div>
      </article>

    </div>
  </div>
  <footer>
    <div class="attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
        >Frontend Mentor</a
      >. Coded by
      <a href="https://github.com/WalkerAlfaro">Walker Alfaro Trelles</a>.
    </div>
  </footer>
</main>

</template>

<script>
import Faq from "@/components/Faq.vue";

export default {
  name: 'App',
  components: {Faq},
  data () {
    return {
      faqs: [
        {
          question: 'How many team members can I invite?',
          answer: 'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.',
          open: false,
        },
        {
          question: 'What is the maximum file upload size?',
          answer: 'No more than 2GB. All files in your account must fit your allotted storage space.',
          open: false
        },
        {
          question: 'How do I reset my password?',
          answer: 'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.',
          open: false
        },
        {
          question: 'Can I cancel my subscription?',
          answer: 'Yes! Send us a message and we’ll process your request no questions asked.',
          open: false
        },
        {
          question: 'Do you provide additional support?',
          answer: 'Chat and email support is available 24/7. Phone lines are open during normal business hours.',
          open: false
        },
      ],
    }
  },

  methods: {
    toggleOpen(index) {
      this.faqs = this.faqs.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open;
        } else {
          faq.open = false;
        }

        return faq;
      })
    }
  }
}
</script>