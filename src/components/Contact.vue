<template>
  <div class="info-section">
    <form id="contact-form">
      <h3 class="info-heading">Contact me</h3>
      <input type="email" placeholder="email" />
      <input type="text" placeholder="subject" />
      <textarea type="text" rows="10" placeholder="message" />
      <button id="submit">Send</button>
    </form>
  </div>
</template>

<script>
export default {};
</script>

<style>
#contact-form {
  display: grid;
  grid-gap: 1rem;
}
#contact-form input,
textarea {
  padding: 0.5rem 1rem;
  border-radius: 1.2rem;
  border-style: none;
  border: 1px solid rgba(97, 97, 97, 0);
  outline: none;
}
#contact-form input:focus,
textarea:focus {
  border: 1px solid rgba(97, 97, 97, 0.5);
}
#contact-form #submit {
  padding: 0.75rem;
  border-radius: 1.2rem;
  border-style: none;
  background-color: rgba(143, 209, 133, 1);
}
</style>