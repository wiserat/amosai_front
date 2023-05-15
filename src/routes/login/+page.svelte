<script>
    import { currentUser, pb } from "$lib/pocketbase.js"
    import { goto } from '$app/navigation';

    let username
    let password

    async function login() {
        await pb.collection('users').authWithPassword(username, password)
        await goto('/app')
    }

    async function signUp() {
        try {
            const data = {
                username,
                password,
                passwordConfirm: password,
                name: 'hellothere',
            }
            const createUser = await pb.collection('users').create(data)
            await login
        } catch (err) {
            console.error(err)
        }
    }

    function signOut() {
        pb.authStore.clear()
    }
</script>

{#if $currentUser}
<section>
    <div class="flex flex-col items-center justify-center px-6 py-8 mx-auto md:h-screen lg:py-0">
        <a href="/" class="flex items-center mb-6 text-3xl font-semibold text-gray-900">
            <img class="w-10 h-10 mr-2 rounded-full" src="https://www.narodnipokladnice.cz/images/stories/sn/numismaticke-novinky/201703/jan-amos-komensky.jpg" alt="logo">
            AmosAI
        </a>
        <div class="w-full bg-gray-100 border-4 border-black rounded-xl shadow md:mt-0 sm:max-w-md xl:p-0">
            <div class="p-6 space-y-4 md:space-y-6 sm:p-8">
                <h1 class="text-xl font-bold leading-tight tracking-tight text-gray-900 md:text-2xl">
                    Login to your account
                </h1>
                <form class="space-y-4 md:space-y-6" action="#">
                    <div>
                        <label for="email" class="block mb-1 text-lg font-bold text-gray-900">Your email</label>
                        <input type="email" name="email" id="email" class="bg-gray-50 border border-gray-900 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5" placeholder="name@client.com">
                    </div>
                    <div>
                        <label for="password" class="block mb-1 text-lg font-bold text-gray-900">Password</label>
                        <input type="password" name="password" id="password" placeholder="••••••••" class="bg-gray-50 border border-gray-900 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5">
                        <a href="#" class="text-sm font-bold text-primary-600 hover:underline">Forgot password?</a>
                    </div>
                    <button type="submit" class="w-full relative inline-block text-lg group text-center pt-5">
                        <span class="relative z-10 block px-5 py-3 overflow-hidden font-medium leading-tight text-gray-800 transition-colors duration-300 ease-out border-2 border-gray-900 rounded-lg">
                        <span class="absolute inset-0 w-full h-full px-5 py-3 rounded-lg bg-gray-50"></span>
                        <span class="absolute left-0 w-96 h-96 -ml-2 transition-all duration-300 origin-top-right -rotate-90 -translate-x-full translate-y-12 bg-sky-200 group-hover:-rotate-180 ease"></span>
                        <span class="relative font-bold">Login</span>
                        </span>
                        <span class="absolute bottom-0 right-0 w-full h-12 -mb-1 -mr-1 transition-all duration-200 ease-linear bg-gray-900 rounded-lg group-hover:mb-0 group-hover:mr-0" data-rounded="rounded-lg"></span>
                    </button>
                    <p class="text-sm font-normal text-gray-800 pt-2">
                        Don’t have an account yet? <a href="/register" class="font-bold text-primary-600 hover:underline">Register</a>
                    </p>
                </form>
            </div>
        </div>
    </div>
</section>
{:else}
    { goto('/app') }
{/if}