<script>
    import { onMount } from "svelte";
    import { writable } from "svelte/store";
    import cryptoJS from "crypto-js";


    const username = writable("");
    const password = writable("");

    async function login() {
        const inputUsername = $username;
        const inputPassword = $password;

        let response = '';
        const url = "http://localhost:3000/login";
        const options = {
            method: "POST",
            headers: {
                "Content-Type": "application/json",
            },
            body: JSON.stringify({ username: inputUsername, password : inputPassword }),
        };
        const res = await fetch(url, options);
        const data = await res.json();
        alert(`Aucun utilisateur trouvé avec le nom "${inputUsername}"`);
        console.log(response);
    }

    async function register() {
        const inputUsername = $username;
        const inputPassword = $password;

        let response = '';
        const url = "http://localhost:"+ process.env.BACK_PORT + "/login";
        const options = {
            method: "POST",
            headers: {
                "Content-Type": "application/json",
            },
            body: JSON.stringify({ name: inputUsername, pass : inputPassword }),
        };
        const res = await fetch(url, options);
        const data = await res.json();
    }

</script>

<section class="bg-gray-50 dark:bg-gray-900">
    <div class="flex flex-col items-center justify-center px-6 py-8 mx-auto md:h-screen lg:py-0">
        <div class="w-full bg-white rounded-lg shadow dark:border md:mt-0 sm:max-w-md xl:p-0 dark:bg-gray-800 dark:border-gray-700">
            <div class="p-6 space-y-4 md:space-y-6 sm:p-8">
                <h1 class="text-xl font-bold leading-tight tracking-tight text-gray-900 md:text-2xl dark:text-white">
                    Se connecter
                </h1>
                <form class="space-y-4 md:space-y-6" action="#">
                    <div>
                        <label for="Username" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Username</label>
                        <input type="Username" name="Username" id="Username" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="BDE Bacchus" required="" bind:value={$username}>
                    </div>
                    <div>
                        <label for="password" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Password</label>
                        <input type="password" name="password" id="password" placeholder="••••••••" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" required="" bind:value={$password}>
                    </div>
                    <div class="flex items-center justify-between">
                        <div class="flex items-start">
                            <div class="flex items-center h-5">
                              <input id="remember" aria-describedby="remember" type="checkbox" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-primary-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-primary-600 dark:ring-offset-gray-800" required="">
                            </div>
                            <div class="ml-3 text-sm">
                              <label for="remember" class="text-gray-500 dark:text-gray-300">Remember me</label>
                            </div>
                        </div>
                    </div>
                    <button on:click={login} type="submit" class="w-full text-white bg-primary-600 hover:bg-primary-700 focus:ring-4 focus:outline-none focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800 bg-sky-600 hover:bg-sky-800">Se connecter</button>
                    <button on:click={register} class="w-full text-white bg-primary-600 hover:bg-primary-700 focus:ring-4 focus:outline-none focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800 bg-sky-600 hover:bg-sky-800">Creer un compte</button>
                </form>
            </div>
        </div>
    </div>
  </section>