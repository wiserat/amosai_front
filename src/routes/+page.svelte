<script>
    import { goto } from "$app/navigation"
    import NiggaSmg from "$lib/assets/nigga_smg.jpg"

    function tryIt() {
        goto('/register')
    }

    function login() {
        goto('/login')
    }

    function app() {
        goto('/app')
    }
</script>

<nav class="bg-white fixed w-full z-20 top-0 left-0">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
        <a href="/" class="flex items-center">
            <img src="https://www.narodnipokladnice.cz/images/stories/sn/numismaticke-novinky/201703/jan-amos-komensky.jpg" class="h-10 mr-3" alt="AmosAI logo">
            <span class="self-center text-2xl font-semibold whitespace-nowrap text-black">AmosAI</span>
        </a>
        <div class="flex md:order-2">
            <button type="submit" on:click={tryIt} class="w-full relative inline-block text-lg group text-center">
                <span class="relative z-10 block px-5 py-3 overflow-hidden font-medium leading-tight text-gray-800 transition-colors duration-300 ease-out border-2 border-gray-900 rounded-lg">
                <span class="absolute inset-0 w-full h-full px-5 py-3 rounded-lg bg-gray-50"></span>
                <span class="absolute left-0 w-96 h-96 -ml-2 transition-all duration-300 origin-top-right -rotate-90 -translate-x-full translate-y-12 bg-sky-200 group-hover:-rotate-180 ease"></span>
                <span class="relative font-bold">Registrovat</span>
                </span>
                <span class="absolute bottom-0 right-0 w-full h-12 -mb-1 -mr-1 transition-all duration-200 ease-linear bg-gray-900 rounded-lg group-hover:mb-0 group-hover:mr-0" data-rounded="rounded-lg"></span>
            </button>
            <button data-collapse-toggle="navbar-sticky" type="button" class="inline-flex items-center p-2 text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-sticky" aria-expanded="false">
            <span class="sr-only">Open main menu</span>
            <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
            </button>
        </div>
        <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1" id="navbar-sticky">
            <ul class="flex flex-col p-4 md:p-0 mt-4 font-medium border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white">
                <li>
                <a href="#" class="block py-2 pl-4 pr-4 font-bold text-lg duration-300 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-sky-300 md:p-0 md:dark:hover:text-blue-300 dark:text-black dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">Kdo Jsme?</a>
                </li>
                <li>
                <a href="#" class="block py-2 pl-4 pr-4 font-bold text-lg duration-300 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-sky-300 md:p-0 md:dark:hover:text-blue-300 dark:text-black dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">Vize</a>
                </li>
                <li>
                <a href="#" class="block py-2 pl-4 pr-4 font-bold text-lg duration-300 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-sky-300 md:p-0 md:dark:hover:text-blue-300 dark:text-black dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">Kontakt</a>
                </li>
            </ul>
        </div>
    </div>
</nav>
<section class="pt-16 min-h-screen flex flex-col">
	<div class="container flex flex-col justify-center p-6 mx-auto sm:py-12 lg:py-24 lg:flex-row lg:justify-between">
		<div class="flex flex-col justify-center p-6 text-center rounded-sm lg:max-w-md xl:max-w-4xl lg:text-left">
			<h1 class="text-5xl font-bold leading-none sm:text-6xl">Testové otázky<br>
				<span class="text-7xl">od AI učitelům</span>
			</h1>
			<p class="mt-6 mb-8 text-lg sm:mb-12">Ofoťte učebnicové materiály
				<br class="hidden md:inline lg:hidden">a umělá inteligence vám vygeneruje testové otázky
			</p>
			<div class="flex flex-col space-y-4 sm:items-center sm:justify-center sm:flex-row sm:space-y-0 sm:space-x-4 lg:justify-start">
                <button type="submit" on:click={tryIt} class="relative inline-block text-lg group text-center">
                    <span class="relative z-10 block px-5 py-3 overflow-hidden font-medium leading-tight text-gray-800 transition-colors duration-300 ease-out border-2 border-gray-900 rounded-lg">
                    <span class="absolute inset-0 w-full h-full px-5 py-3 rounded-lg bg-gray-50"></span>
                    <span class="absolute left-0 w-96 h-96 -ml-2 transition-all duration-300 origin-top-right -rotate-90 -translate-x-full translate-y-12 bg-sky-200 group-hover:-rotate-180 ease"></span>
                    <span class="relative font-bold">Zkuste To Sami!</span>
                    </span>
                    <span class="absolute bottom-0 right-0 w-full h-12 -mb-1 -mr-1 transition-all duration-200 ease-linear bg-gray-900 rounded-lg group-hover:mb-0 group-hover:mr-0" data-rounded="rounded-lg"></span>
                </button>
			</div>
		</div>
		<div class="flex items-center justify-center p-6 mt-8 lg:mt-0 h-72 sm:h-80 lg:h-96 xl:h-112 2xl:h-128">
			<img src={NiggaSmg} alt="" class="object-contain h-72 sm:h-80 lg:h-96 xl:h-112 2xl:h-128">
		</div>
	</div>
    <div class="max-w-screen-xl px-4 py-8 mx-auto text-center lg:py-16 lg:px-6 mt-auto">
        <dl class="grid max-w-screen-md gap-24 mx-auto text-gray-900 sm:grid-cols-3">
            <div class="grid mx-auto sm:grid-cols-2">
                <svg aria-hidden="true" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" class="w-16 my-auto mx-auto text-sky-900">
                    <path d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z" stroke-linecap="round" stroke-linejoin="round"></path>
                  </svg>
                <div class="flex flex-col items-center justify-center">
                    <dt class="mb-2 text-3xl md:text-4xl font-extrabold">2043</dt>
                    <dd class="text-gray-700">UČITELŮ</dd>
                </div>
            </div>
            <div class="grid mx-auto sm:grid-cols-2">
                <svg aria-hidden="true" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" class="w-16 my-auto mx-auto text-sky-900">
                    <path d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z" stroke-linecap="round" stroke-linejoin="round"></path>
                </svg>
                <div class="flex flex-col items-center justify-center pl-0 sm:pl-6">
                    <dt class="mb-2 text-3xl md:text-4xl font-extrabold">50000+</dt>
                    <dd class="text-gray-700">VYTVOŘENÝCH OTÁZEK</dd>
                </div>
            </div>
            <div class="grid mx-auto sm:grid-cols-2">
                <svg aria-hidden="true" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" class="w-16 my-auto mx-auto text-sky-900">
                    <path d="M4.26 10.147a60.436 60.436 0 00-.491 6.347A48.627 48.627 0 0112 20.904a48.627 48.627 0 018.232-4.41 60.46 60.46 0 00-.491-6.347m-15.482 0a50.57 50.57 0 00-2.658-.813A59.905 59.905 0 0112 3.493a59.902 59.902 0 0110.399 5.84c-.896.248-1.783.52-2.658.814m-15.482 0A50.697 50.697 0 0112 13.489a50.702 50.702 0 017.74-3.342M6.75 15a.75.75 0 100-1.5.75.75 0 000 1.5zm0 0v-3.675A55.378 55.378 0 0112 8.443m-7.007 11.55A5.981 5.981 0 006.75 15.75v-1.5" stroke-linecap="round" stroke-linejoin="round"></path>
                </svg>
                <div class="flex flex-col items-center justify-center">
                    <dt class="mb-2 text-3xl md:text-4xl font-extrabold">26</dt>
                    <dd class="text-gray-700">ZAPOJENÝCH ŠKOL</dd>
                </div>
            </div>
        </dl>
    </div>
</section>
<section class="bg-white">
    <div class="container px-6 py-10 mx-auto">
        <h1 class="text-3xl font-semibold text-gray-800 capitalize text-center pt-32 lg:text-4xl">Proč používat <span class="text-sky-900 font-extrabold">AmosAI</span>?</h1>
        <div class="grid grid-cols-1 gap-8 mt-8 xl:mt-12 xl:gap-12 md:grid-cols-2 lg:grid-cols-3">
            <div class="p-8 space-y-3 border-4 border-sky-600 rounded-3xl hover:rounded-xl scale-100 hover:scale-110 hover:shadow-2xl ease-in-out duration-700">
                <span class="inline-block text-sky-800">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 18.657A8 8 0 016.343 7.343S7 9 9 10c0-2 .5-5 2.986-7C14 5 16.09 5.777 17.656 7.343A7.975 7.975 0 0120 13a7.975 7.975 0 01-2.343 5.657z" />
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.879 16.121A3 3 0 1012.015 11L11 14H9c0 .768.293 1.536.879 2.121z" />
                    </svg>
                </span>
                <h1 class="text-2xl font-semibold text-gray-900 capitalize">Zlepší Otázky</h1>
                <p class="text-lg text-gray-900">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident ab nulla quod dignissimos vel non corrupti doloribus voluptatum eveniet
                </p>
            </div>
            <div class="p-8 space-y-3 border-4 border-sky-600 rounded-3xl hover:rounded-xl scale-100 hover:scale-110 hover:shadow-2xl ease-in-out duration-700">
                <span class="inline-block text-sky-800">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 18.657A8 8 0 016.343 7.343S7 9 9 10c0-2 .5-5 2.986-7C14 5 16.09 5.777 17.656 7.343A7.975 7.975 0 0120 13a7.975 7.975 0 01-2.343 5.657z" />
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.879 16.121A3 3 0 1012.015 11L11 14H9c0 .768.293 1.536.879 2.121z" />
                    </svg>
                </span>
                <h1 class="text-2xl font-semibold text-gray-900 capitalize">Ušetří Čas</h1>
                <p class="text-lg text-gray-900">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident ab nulla quod dignissimos vel non corrupti doloribus voluptatum eveniet
                </p>
            </div>
            <div class="p-8 space-y-3 border-4 border-sky-600 rounded-3xl hover:rounded-xl scale-100 hover:scale-110 hover:shadow-2xl ease-in-out duration-700">
                <span class="inline-block text-sky-800">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 18.657A8 8 0 016.343 7.343S7 9 9 10c0-2 .5-5 2.986-7C14 5 16.09 5.777 17.656 7.343A7.975 7.975 0 0120 13a7.975 7.975 0 01-2.343 5.657z" />
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.879 16.121A3 3 0 1012.015 11L11 14H9c0 .768.293 1.536.879 2.121z" />
                    </svg>
                </span>
                <h1 class="text-2xl font-semibold text-gray-900 capitalize">Zlepší Otázky</h1>
                <p class="text-lg text-gray-900">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident ab nulla quod dignissimos vel non corrupti doloribus voluptatum eveniet
                </p>
            </div>
        </div>
    </div>
</section>
<section>
    <header class="bg-header flex items-center justify-center h-screen pb-12">
        <div class="bg-white font-serif mx-4 p-4 text-center md:p-8">
          <p class="italic text-sm">
            November 1, 2019
          </p>
          <h1 class="text-5xl uppercase">
            Article Title
          </h1>
          <p class="text-lg">
            Author Name
          </p>
        </div>
      </header>
      
      <div class="font-serif leading-normal mx-auto py-12 px-4 max-w-lg">
        <p class="mb-6 text-xl md:text-2xl uppercase">This is a simple parallax effect created by setting the background attachment property to a fixed position. This technique is not meant for non-decorative images, videos, etc. as those require additional HTML and CSS to work properly.</p>
        <p class="mb-4 text-lg">Quae commodi reiciendis dignissimos. Rerum molestiae hic dolores assumenda dolor! Corrupti reiciendis maxime fuga, recusandae obcaecati officia cum temporibus dicta quibusdam praesentium, magni, cumque aperiam iusto sequi illum molestiae non.</p>
        <p class="mb-4 text-lg">In excepturi repellendus eum, qui corrupti rerum perferendis harum adipisci voluptate? Nihil, quidem deleniti libero officia dicta vel asperiores velit molestiae blanditiis, dolore voluptatibus excepturi laudantium at veniam illo. Dolor!</p>
        <p class="mb-4 text-lg">Neque laudantium minus doloremque id quas quod sint velit corporis unde dolore accusantium delectus optio consequuntur voluptatem sapiente odit dolorum minima harum tenetur, dolor provident reprehenderit. Ex eum provident harum?</p>
        <p class="mb-4 text-lg">Mollitia temporibus maxime placeat culpa distinctio possimus, praesentium, assumenda quasi eum voluptate magni aspernatur aperiam. Eius voluptates rem eum, facilis inventore hic provident pariatur nam non! At odit iste cum.</p>
        <p class="mb-4 text-lg">Cumque voluptatibus laboriosam tempore architecto laudantium sint vitae cupiditate voluptate quod tempora saepe odio quasi dolores possimus non totam unde voluptates corrupti, ducimus ipsa enim officiis ipsum maxime eveniet. Aut!</p>
        <p class="mb-4 text-lg">Maxime facere ut natus libero incidunt alias quam consectetur, nisi delectus exercitationem ab qui perferendis dolorem sequi veritatis nobis eius quas dolore ducimus atque vel. Doloribus mollitia non pariatur modi?</p>
        <p class="mb-4 text-lg">Sed in amet a neque, delectus, cupiditate ab assumenda quidem facere molestias vitae itaque soluta reprehenderit dolorem. Deserunt quibusdam, consequatur veniam fugiat ipsam aliquam ea possimus quis officiis enim dolores.</p>
        <p class="mb-4 text-lg">Exercitationem aperiam veniam perspiciatis iure ad nobis necessitatibus cumque cupiditate obcaecati natus. Neque nostrum maxime id veritatis tempore, a voluptate voluptatem et! A ullam id aliquam? Recusandae deleniti odit fugit!</p>
        <p class="mb-4 text-lg">Beatae rerum obcaecati consectetur nostrum eos ipsam, accusamus delectus ex maxime neque sit quod repellendus voluptate sunt dolore hic explicabo ea dolorum vero vel quidem illo! Cupiditate sed voluptatibus ullam?</p>
        <p class="mb-4 text-lg">Modi aliquam facilis adipisci! Soluta eveniet eos omnis, inventore nesciunt, laborum deserunt blanditiis nihil accusamus debitis voluptatibus possimus dolores vero maiores, sed voluptate ut! Facilis possimus vitae consectetur praesentium veritatis.</p>
        <p class="mb-4 text-lg">Tempore, quaerat accusamus ad nostrum maiores numquam, ea nam sed reiciendis, eveniet perspiciatis. Eos nulla vel consectetur quo nesciunt aspernatur sint nemo cumque optio mollitia, veritatis, tenetur quibusdam eum natus.</p>
      </div>
      
      <div class="bg-quote container flex items-center justify-center h-screen mx-auto">
        <blockquote class="bg-black font-serif mx-4 p-4 text-center text-white md:p-8">
          <p class="font-bold italic text-3xl">
            &ldquo;Large, bold pull quote. Hats. Very good.&rdquo;
          </p>
        </blockquote>
      </div>
      
      <div class="font-serif leading-normal mx-auto py-12 px-4 max-w-lg">
        <p class="mb-4 text-lg">Quae commodi reiciendis dignissimos. Rerum molestiae hic dolores assumenda dolor! Corrupti reiciendis maxime fuga, recusandae obcaecati officia cum temporibus dicta quibusdam praesentium, magni, cumque aperiam iusto sequi illum molestiae non.</p>
        <p class="mb-4 text-lg">In excepturi repellendus eum, qui corrupti rerum perferendis harum adipisci voluptate? Nihil, quidem deleniti libero officia dicta vel asperiores velit molestiae blanditiis, dolore voluptatibus excepturi laudantium at veniam illo. Dolor!</p>
        <p class="mb-4 text-lg">Neque laudantium minus doloremque id quas quod sint velit corporis unde dolore accusantium delectus optio consequuntur voluptatem sapiente odit dolorum minima harum tenetur, dolor provident reprehenderit. Ex eum provident harum?</p>
        <p class="mb-4 text-lg">Mollitia temporibus maxime placeat culpa distinctio possimus, praesentium, assumenda quasi eum voluptate magni aspernatur aperiam. Eius voluptates rem eum, facilis inventore hic provident pariatur nam non! At odit iste cum.</p>
      </div>
</section>



<div class="fixed inset-x-0 lg:inset-x-auto bottom-6 lg:right-8 xl:right-10 xl:bottom-8">
    <div class="md:w-64 xl:w-52 px-6 lg:px-0">
        <div class="p-2 bg-sky-200 shadow-2xl rounded-lg sm:p-3 hover:bg-sky-300 ease-in-out duration-300">
            <div class="flex flex-wrap items-center justify-between">
                <a target="_blank" href="mailto:jonas.tenora@gmail.com" class="flex items-center flex-1 w-0">
                    <span class="flex p-2 bg-sky-800 rounded-lg">
                        <svg class="h-6 w-6 text-white" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M8.625 12a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H8.25m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H12m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0h-.375M21 12c0 4.556-4.03 8.25-9 8.25a9.764 9.764 0 01-2.555-.337A5.972 5.972 0 015.41 20.97a5.969 5.969 0 01-.474-.065 4.48 4.48 0 00.978-2.025c.09-.457-.133-.901-.467-1.226C3.93 16.178 3 14.189 3 12c0-4.556 4.03-8.25 9-8.25s9 3.694 9 8.25z" fill="currentColor"></path>
                        </svg>
                    </span>
                    <p class="ml-3 font-bold tracking-wide text-black truncate">
                        Zeptejte se nás
                    </p>
                </a>
            </div>
        </div>
    </div>
</div>
<nav>
    <div class=""
</nav>

<br><br><br><br><br><br><br><br><br><br><br><br>
<button on:click={login}>he</button>
<br><br>
<button on:click={app}>app</button>

<style>
    .bg-header {
        background: url(https://picsum.photos/1920/1920/?random) center center no-repeat;
        background-attachment: fixed;
    }

    .bg-quote {
        background: url(https://picsum.photos/1600/1600/?random) center center no-repeat;
        background-attachment: fixed;
    }
</style>