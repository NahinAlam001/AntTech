<script>
  let testimonials = [
    { name: 'John Doe', feedback: 'NSU CSE Project Assistance helped me complete my final year project on time and exceeded my expectations.' },
    { name: 'Jane Smith', feedback: 'The team was professional and supportive throughout the process. Highly recommended!' }
  ];
</script>

<section id="testimonials" class="py-16 bg-indigo-600 text-white">
  <div class="container mx-auto text-center">
    <h2 class="text-4xl font-bold mb-12">What Our Clients Say</h2>
    <div class="grid md:grid-cols-2 gap-8">
      {#each testimonials as testimonial}
        <div class="bg-indigo-700 p-6 rounded-lg shadow-lg transform hover:-translate-y-1 transition duration-500">
          <p class="mb-4">"{testimonial.feedback}"</p>
          <p class="font-bold">{testimonial.name}</p>
        </div>
      {/each}
    </div>
  </div>
</section>
