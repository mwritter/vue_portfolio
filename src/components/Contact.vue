<template>
  <div class="info-section">
    <h3 class="info-heading">Contact me</h3>
    <form name="contact" action="POST" data-netlify="true" id="contact-form">
      <input type="email" name="email" placeholder="email" />
      <textarea type="text" name="message" rows="10" placeholder="message" />
      <div data-netlify-recaptcha="true"></div>
      <button type="submit" id="submit">Send</button>
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
  margin-top: 1rem;
}
#contact-form input,
textarea {
  padding: 0.75rem 2rem;
  border-radius: 1.2rem;
  border-style: none;
  border: 1px solid rgba(97, 97, 97, 0);
  outline: none;
  font-family: "Roboto";
  font-size: 1.05rem;
  transition: all 500ms;
  color: rgba(72, 171, 241, 1);
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
  cursor: pointer;
  transition: all 300ms;
}
#contact-form #submit:focus {
  outline: none;
}
#contact-form #submit:hover {
  box-shadow: 1px 1px 5px 0px rgba(10, 10, 10, 0.2);
}
</style>