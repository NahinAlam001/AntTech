<script>
    let navItems = ['Home', 'About', 'Services', 'Testimonials', 'Contact'];
  </script>
  
  <header class="bg-gradient-to-r from-indigo-600 to-purple-600 text-white shadow-md p-5">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-2xl font-bold">NSU CSE Project Assistance</h1>
      <nav>
        <ul class="flex space-x-6">
          {#each navItems as item}
            <li><a href="#{item.toLowerCase()}" class="hover:text-indigo-200">{item}</a></li>
          {/each}
        </ul>
      </nav>
    </div>
  </header>