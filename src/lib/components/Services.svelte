<script>
    let services = [
      { title: 'Final Year Project Development', description: 'High-quality final year projects customized to your requirements.' },
      { title: 'Programming Assignments', description: 'Get expert help with your coding assignments.' },
      { title: 'Research Papers and Theses', description: 'Professional guidance for your academic writing needs.' },
      { title: 'Web and Mobile App Development', description: 'From concept to launch, we develop apps that stand out.' },
      { title: 'Database Design and Implementation', description: 'Structured and efficient database solutions.' },
      { title: 'AI & Machine Learning Projects', description: 'Cutting-edge AI solutions for your projects.' }
    ];
  </script>
  
  <section id="services" class="py-16 bg-gray-100">
    <div class="container mx-auto text-center">
      <h2 class="text-4xl font-bold mb-12">Our Services</h2>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each services as service}
          <div class="bg-white p-6 rounded-lg shadow-md transform hover:-translate-y-1 transition duration-500">
            <h3 class="text-2xl font-semibold mb-4">{service.title}</h3>
            <p>{service.description}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>