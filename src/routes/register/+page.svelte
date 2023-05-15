<script>
    import { currentUser, pb } from "$lib/pocketbase.js"
    import { goto } from '$app/navigation';

    let username
    let email
    let organization
    let password
    let passwordConfirm


    async function login() {
        await pb.collection('users').authWithPassword(email, password)
        await goto('/app')
    }

    async function signUp() {
        if (password !== passwordConfirm) {
            alert('passwords do not match')
            return
        }
        try {
            const data = new FormData()
            data.append('username', "hello")
            data.append('name', username)
            data.append('email', email)
            data.append('password', password)
            data.append('passwordConfirm', passwordConfirm)
            data.append('organization', organization)
            const createData = await pb.collection('users').create(data)
            await login
        } catch (err) {
            console.error(err)
        }
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
                        Sign up
                    </h1>
                    <form class="space-y-4 md:space-y-6" action="#">
                        <div>
                            <label for="name" class="block mb-1 text-lg font-bold text-gray-900">Full Name</label>
                            <input type="text" name="name" id="name" class="bg-gray-50 border border-gray-900 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5" placeholder="Hilbert Kuřbřicht">
                        </div>
                        <div>
                            <label for="email" class="block mb-1 text-lg font-bold text-gray-900">Your email</label>
                            <input type="email" name="email" id="email" class="bg-gray-50 border border-gray-900 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5" placeholder="name@client.com">
                        </div>
                        <div>
                            <label for="org" class="block mb-1 text-lg font-bold text-gray-900">Organization</label>
                            <input type="text" name="org" id="org" class="bg-gray-50 border border-gray-900 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5" placeholder="freee biird yeee">
                        </div>
                        <div>
                            <label for="password" class="block mb-1 text-lg font-bold text-gray-900">Password</label>
                            <input type="password" name="password" id="password" placeholder="••••••••" class="bg-gray-50 border border-gray-900 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5">

                        </div>
                        <div>
                            <label for="password" class="block mb-1 text-lg font-bold text-gray-900">Confirm Password</label>
                            <input type="password" name="passwordConfirm" id="passwordConfirm" placeholder="••••••••" class="bg-gray-50 border border-gray-900 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5">
                        </div>
                        <button type="submit" class="w-full relative inline-block text-lg group text-center pt-5">
                            <span class="relative z-10 block px-5 py-3 overflow-hidden font-medium leading-tight text-gray-800 transition-colors duration-300 ease-out border-2 border-gray-900 rounded-lg">
                                <span class="absolute inset-0 w-full h-full px-5 py-3 rounded-lg bg-gray-50"></span>
                                <span class="absolute left-0 w-96 h-96 -ml-2 transition-all duration-300 origin-top-right -rotate-90 -translate-x-full translate-y-12 bg-sky-200 group-hover:-rotate-180 ease"></span>
                                <span class="relative font-bold">Register</span>
                            </span>
                            <span class="absolute bottom-0 right-0 w-full h-12 -mb-1 -mr-1 transition-all duration-200 ease-linear bg-gray-900 rounded-lg group-hover:mb-0 group-hover:mr-0" data-rounded="rounded-lg"></span>
                        </button>
                        <p class="text-sm font-normal text-gray-800 pt-2">
                            Already have an account? <a href="/login" class="font-bold text-primary-600 hover:underline">Login</a>
                        </p>
                    </form>
                </div>
            </div>
        </div>
    </section>
    <form on:submit|preventDefault>
        <input
                placeholder="Full Name"
                type="text"
                bind:value={username}
        />
        <input
                placeholder="Email"
                type="email"
                bind:value={email}
        />
        <input
                placeholder="Organization (leave blank if you are not affiliated with one)"
                type="text"
                bind:value={organization}
        />
        <input
                placeholder="password"
                type="password"
                bind:value={password}
        />
        <input 
                placeholder="confirm password"
                type="password"
                bind:value={passwordConfirm}
        />

        <button on:click={signUp}>sign up</button>
    </form>
{:else}
    { goto('/app') }
{/if}