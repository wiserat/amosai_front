<script>
  import "../app.postcss";
</script>

<div class="flex flex-col min-h-screen justify-between">
  <slot />
  <footer class="bg-sky-100 rounded-lg shadow m-4">
    <div class="w-full mx-auto max-w-screen-xl p-4 md:flex md:items-center md:justify-between">
      <span class="text-sm text-gray-700 sm:text-center">© 2023 <a href="/" class="text-gray-900 font-bold hover:underline">AmosAI™</a>. All Rights Reserved.
      </span>
      <ul class="flex flex-wrap items-center mt-3 text-sm font-bold text-gray-600 sm:mt-0">
          <li>
              <a href="#" class="mr-4 hover:underline md:mr-6 ">About</a>
          </li>
          <li>
              <a href="#" class="mr-4 hover:underline md:mr-6">Privacy Policy</a>
          </li>
          <li>
              <a href="#" class="mr-4 hover:underline md:mr-6">Licensing</a>
          </li>
          <li>
              <a href="#" class="hover:underline">Contact</a>
          </li>
      </ul>
    </div>
  </footer>
</div>