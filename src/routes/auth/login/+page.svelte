<!--
  This component uses @tailwindcss/forms

  yarn add @tailwindcss/forms
  npm install @tailwindcss/forms

  plugins: [require('@tailwindcss/forms')]
-->
<script>
  import LogoOutline from "../../../components/svg/LogoOutline.svelte";
  import WhiteOutline from "../../../components/svg/WhiteOutline.svelte";
</script>
<section class="bg-white">
  <div class="lg:grid min-h-screen lg:grid-cols-12">
    <section
      class="relative flex h-32 items-end bg-gray-900 lg:col-span-5 lg:h-full xl:col-span-6"
    >
      <img
        alt="Orange"
        src="https://images.unsplash.com/photo-1548504769-900b70ed122e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1160&q=80"
        class="absolute inset-0 h-full w-full object-cover opacity-80"
      />

      <div class="hidden lg:relative lg:block lg:p-12">
        <a class="block text-white" href="/">
          <span class="sr-only">Home</span>
          <WhiteOutline height="60"/>
        </a>

        <h2 class="mt-6 text-2xl font-bold text-white sm:text-3xl md:text-4xl">
          fishive login 🐫
        </h2>

        <p class="mt-4 leading-relaxed text-white/90">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eligendi nam
          dolorum aliquam, quibusdam aperiam voluptatum.
        </p>
        <p class="mt-4 text-sm text-gray-300">
          Copyright &copy; 2023. All rights reserved.
        </p>
      </div>
    </section>

    <main
      aria-label="Main"
      class="flex items-center justify-center px-8 py-8 sm:px-12 lg:col-span-7 lg:py-12 lg:px-16 xl:col-span-6"
    >
      <div class="max-w-xl lg:max-w-3xl">
        <div class="relative -mt-16 block lg:hidden">
          <a
            class="inline-flex h-16 w-16 items-center justify-center rounded-full bg-white text-orange-600 sm:h-20 sm:w-20"
            href="/"
          >
            <span class="sr-only">Home</span>
            <LogoOutline height="50"/>
          </a>

          <h1
            class="mt-2 text-2xl font-bold text-gray-900 sm:text-3xl md:text-4xl"
          >
          fishive login 🐫
          </h1>

          <p class="mt-4 leading-relaxed text-gray-500">
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eligendi
            nam dolorum aliquam, quibusdam aperiam voluptatum.
          </p>
        </div>

        <form action="#" class="mt-8 grid grid-cols-6 gap-6">


          <div class="col-span-6">
            <label for="Email" class="block text-sm font-medium text-gray-700">
              Email
            </label>

            <input
              type="email"
              id="Email"
              name="email"
              class="mt-1 w-full rounded-md border-gray-700 bg-white p-2 text-sm text-gray-700 shadow-sm"
            />
          </div>

          <div class="col-span-6">
            <label
              for="Password"
              class="block text-sm font-medium text-gray-700"
            >
              Password
            </label>

            <input
              type="password"
              id="Password"
              name="password"
              class="mt-1 w-full rounded-md border-gray-700 bg-white p-2 text-sm text-gray-700 shadow-sm"
            />
          </div>


          <div class="col-span-6">
            <label for="StayLoggedIn" class="flex gap-4">
              <input
                type="checkbox"
                id="StayLoggedIn"
                name="stay_logged_in"
                class="h-5 w-5 rounded-md border-gray-200 bg-white shadow-sm"
              />

              <span class="text-sm text-gray-700">
                Keep me logged in
              </span>
            </label>
          </div>

          <div class="col-span-6">
            <p class="text-sm text-gray-500">
              By logging in, you agree to our
              <a href="#" class="text-gray-700 underline">
                terms and conditions
              </a>
              and
              <a href="#" class="text-gray-700 underline">privacy policy</a>.
            </p>
          </div>

          <div class="col-span-6 sm:flex sm:items-center sm:gap-4">
            <a href="/dashboard">
              <button 
              class="inline-block shrink-0 rounded-md border border-orange-300 bg-orange-600 px-12 py-3 text-sm font-medium text-white transition hover:bg-transparent hover:text-orange-600 focus:outline-none focus:ring active:text-orange-500"
            >
              Log in
            </button>
          </a>

            <p class="mt-4 text-sm text-gray-500 sm:mt-0">
              Don't have an account?
              <a href="register" class="text-gray-700 underline">Register</a>.
            </p>
          </div>
        </form>
      </div>
    </main>
  </div>
</section>
