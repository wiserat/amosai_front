<script>
    import { currentUser, pb } from "$lib/pocketbase.js"
    import { goto } from '$app/navigation';
    import { Fileupload, Label, Listgroup, ListgroupItem, Dropzone } from 'flowbite-svelte'
  
    let files
    let url
    let amount
    let alright = 0

    async function sendData() {
        alright = 0
        if (!amount) {
            amount = 10
        }
        if (amount <= 5 || amount >= 25) {
            alright = -1
            throw new Error('Amount of questions must be between 5 and 25')
        } else { 
            try { 
                const data = new FormData()

                data.append('relation', $currentUser.id)

                var amountS = amount.toString()
                data.append('amount', amountS)

                if (!url) {
                    url = ''
                    alright = alright + 1
                }
                data.append('userUrl', url)
                
                try { 
                    for (let file of files) {
                        data.append('userFiles', file)
                    }
                } catch (err) {
                    console.error(err)
                    alright = alright + 1
                }
                
                if (alright == 2) {
                    throw new Error('No files or url inserted')
                } else {
                    const createData = await pb.collection('questions').create(data)
                    await goto('/app/create')
                }
            } catch (err) {
                console.error(err)
            }
        }
    }
</script>

{#if $currentUser}
    <h2 class="font-bold flex w-full justify-center mb-4 items-center text-gray-900 text-xl">Upload your files</h2>
    <div class="items-center justify-center flex w-full">
        <div class="flex flex-col items-center justify-center w-96">
            <Dropzone id='dropzone' multiple bind:files>
                <svg aria-hidden="true" class="mb-3 w-10 h-10 text-gray-900" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 16a4 4 0 01-.88-7.903A5 5 0 1115.9 6L16 6a5 5 0 011 9.9M15 13l-3-3m0 0l-3 3m3-3v12"></path></svg>
                <p class="mb-2 text-sm text-gray-900 dark:text-gray-400"><span class="font-semibold">Click to upload</span> or drag and drop</p>
                <p class="text-xs text-gray-900 dark:text-gray-400">SVG, PNG, JPG or GIF (MAX. 800x400px)</p>
            </Dropzone>
        </div>
        <div class="flex flex-col p-12">
            <Listgroup items={files} let:item class="border-2 border-gray-900 text-gray-900 font-bold">
            {#if item}
                {item.name} 
            {:else}
                <ListgroupItem><b>No files inserted</b></ListgroupItem>
            {/if}
            </Listgroup>
        </div>
    </div> 
    <div>
        <p class="text-gray-900 text-center pb-9 pt-9 font-bold text-4xl">or</p>
    </div>
    <div class="flex w-full justify-center items-center">
        <div>
            <label for="url" class="text-center block mb-3 text-xl font-bold text-gray-900">Give us an  URL</label>
            <input bind:value={url} type="url" name="url" id="url" class="bg-gray-200 border-2 border-gray-900 text-gray-900 sm:text-xm rounded-xl focus:ring-primary-600 focus:border-primary-600 p-2.5 w-96 block" placeholder="https://en.wikipedia.org/wiki/Adolf_Hitler">
        </div>
    </div>
    <hr class="h-px my-8 bg-gray-900 border-2 border-gray-400 mx-6 md:mx-48 rounded">
    <div class="flex w-full justify-center items-center mb-3">
        <div>
            <label for="amount" class="text-center block mb-3 text-xl font-bold text-gray-900">Pocet otazek (5-25)</label>
            <div class="flex flex-col w-full justify-center items-center">
                <input bind:value={amount} type="text" name="amount" id="amount" class="bg-gray-200 border-2 border-gray-900 text-gray-900 sm:text-xm rounded-lg focus:ring-primary-600 focus:border-primary-600 p-2.5 w-11 block text-right" placeholder="10" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');">
            </div>
        </div>
    </div>
    <div class="flex w-full justify-center items-center">
        <button type="submit" on:click={sendData} class="w-80 relative inline-block text-lg group text-center">
            <span class="relative z-10 block px-5 py-3 overflow-hidden font-medium leading-tight text-gray-800 transition-colors duration-300 ease-out border-2 border-gray-900 rounded-lg">
            <span class="absolute inset-0 w-full h-full px-5 py-3 rounded-lg bg-gray-50"></span>
            <span class="absolute left-0 w-96 h-96 -ml-2 transition-all duration-300 origin-top-right -rotate-90 -translate-x-full translate-y-12 bg-sky-200 group-hover:-rotate-180 ease"></span>
            <span class="relative font-bold">Odeslat a načíst otázky</span>
            </span>
            <span class="absolute bottom-0 right-0 w-full h-12 -mb-1 -mr-1 transition-all duration-200 ease-linear bg-gray-900 rounded-lg group-hover:mb-0 group-hover:mr-0" data-rounded="rounded-lg"></span>
        </button>
    </div>
    {#if alright == 2}
        <p class="text-red-700 font-bold text-center">No files or url inserted</p>
    {:else if alright == -1}
        <p class="text-red-700 font-bold text-center">Amount of questions must be between 5 and 25</p>
    {/if}
{:else}
    { goto('/login') }
{/if}