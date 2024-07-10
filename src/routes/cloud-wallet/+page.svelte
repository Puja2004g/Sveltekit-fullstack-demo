<script>
    export let form;
</script>

<div
    class="mt-10 pt-10 w-full max-w-xl p-5 mx-auto rounded-lg shadow-xl dark:bg-white/10 bg-white/30 ring-1 ring-gray-900/5 backdrop-blur-lg"
>
    <h1 class="text-xl mb-4 font-bold font-mono">Login</h1>
    <form method="post" action="?/login">
        <div class="mx-3 mb-2">
            <div class="w-full px-3 mb-6">
                <label
                    class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                    for="grid-city"
                >
                    Email
                </label>
                <input
                    class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                    id="email"
                    type="text"
                    placeholder="Enter email"
                    name="email"
                />
            </div>
            <div class="w-full px-3">
                <label
                    class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                    for="password"
                >
                    Password
                </label>
                <input
                    class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                    id="password"
                    type="password"
                    placeholder="Enter password"
                    name="password"
                />
            </div>
            <button
                type="submit"
                class="bg-yellow-500 hover:bg-blue-700 text-white font-bold mt-5 ml-3 px-5 py-2 rounded"
            >
                Login
            </button>
        </div>
    </form>
    {#if form?.auth}
        <p class="font-semibold text-green-600">
            Logged In. Your balance is {form?.balance}
        </p>
    {/if}
</div>

<!-- payment -->
<div
    class="mt-10 pt-10 mb-28 w-full max-w-xl p-5 mx-auto rounded-lg shadow-xl dark:bg-white/10 bg-white/30 ring-1 ring-gray-900/5 backdrop-blur-lg"
>
    <h1 class="text-xl mb-4 font-bold font-mono">Pay</h1>
    <form method="POST" action="?/pay">
        <div class="mx-3 mb-2">
            <div class="mx-3 mb-2">
                <div class="w-full px-3 mb-6">
                    <label
                        class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                        for="grid-city"
                    >
                        Email
                    </label>
                    <input
                        class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                        id="email"
                        type="text"
                        placeholder="Enter email"
                        name="email"
                    />
                </div>
                <div class="w-full px-3">
                    <label
                        class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                        for="password"
                    >
                        Password
                    </label>
                    <input
                        class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                        id="password"
                        type="password"
                        placeholder="Enter password"
                        name="password"
                    />
                </div>

                <div class="w-full px-3 mb-6">
                    <label
                        class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2 mt-6"
                        for="paymail"
                    >
                        Paymail
                    </label>
                    <input
                        class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                        id="paymail"
                        type="text"
                        placeholder="Enter paymail"
                        name="paymail"
                    />
                </div>
                <div class="w-full px-3">
                    <label
                        class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                        for="amount"
                    >
                        Amount
                    </label>
                    <input
                        class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                        id="amount"
                        type="number"
                        placeholder="Enter amount"
                        name="amount"
                    />
                </div>
                <button
                    type="submit"
                    class="bg-yellow-500 hover:bg-blue-700 text-white font-bold mt-5 ml-2 px-2 p-3 rounded"
                >
                    Pay amount
                </button>
            </div>
        </div>
    </form>
    {#if form?.success}
        <p class="pt-2 text-green-600 font-mono font-bold ml-10">
            The payment was successful. Here is your <a
                class=" text-blue-500 font-bold font-mono"
                href="https://whatsonchain.com/tx/{form?.payResponse}"
                >transaction</a
            >!
        </p>
    {:else if form?.success === false}
        <p class="font-semibold text-red-600 mt-10">
            {form?.payResponse}
        </p>
    {/if}
</div>
