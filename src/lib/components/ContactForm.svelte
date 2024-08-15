<script>
  let name = '';
  let email = '';
  let message = '';
  
  function submitForm() {
    // Here you can add logic to send form data to a backend service
    alert(`Thank you, ${name}! We will get in touch with you soon.`);
    // Reset the form if needed
    name = '';
    email = '';
    message = '';
  }
</script>

<section id="contact" class="py-16 bg-gray-100">
  <div class="container mx-auto">
    <h2 class="text-4xl font-bold text-center mb-8">Get in Touch</h2>
    <form class="max-w-lg mx-auto bg-white p-8 rounded-lg shadow-md" on:submit|preventDefault={submitForm}>
      <div class="mb-4">
        <label for="name" class="block text-gray-700 font-bold mb-2">Name</label>
        <input type="text" id="name" bind:value={name} class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-600" required>
      </div>
      <div class="mb-4">
        <label for="email" class="block text-gray-700 font-bold mb-2">Email</label>
        <input type="email" id="email" bind:value={email} class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-600" required>
      </div>
      <div class="mb-4">
        <label for="message" class="block text-gray-700 font-bold mb-2">Message</label>
        <textarea id="message" bind:value={message} rows="4" class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-600" required></textarea>
      </div>
      <button type="submit" class="w-full bg-indigo-600 text-white font-bold py-2 rounded-lg hover:bg-indigo-700 transition">Submit</button>
    </form>
  </div>
</section>
