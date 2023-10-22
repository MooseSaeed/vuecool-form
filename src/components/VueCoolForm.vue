<template>
  <div
    class="relative flex flex-col items-center rounded-xl bg-transparent bg-clip-border text-gray-300 shadow-none;"
  >
    <input
      class="mb-3 w-full rounded-md border bg-transparent px-3 py-3 font-sans text-sm font-normal text-blue-gray-700 outline outline-0 transition-all"
      type="text"
      placeholder="Give me a name"
      v-model="formInfo.name"
    />
    <input
      class="mb-3 w-full rounded-md border bg-transparent px-3 py-3 font-sans text-sm font-normal text-blue-gray-700 outline outline-0 transition-all"
      type="text"
      placeholder="Give me a title"
      v-model="formInfo.title"
    />
    <h2
      class="block font-sans text-2xl font-semibold leading-snug tracking-normal text-blue-gray-900 antialiased text-center"
    >
      {{
        !formInfo.title || !formInfo.name
          ? `${defaultName} - ${defaultTitle}`
          : `${formInfo.name}
      - ${formInfo.title}`
      }}
    </h2>

    <form class="mt-8 mb-2 w-80 max-w-screen-lg sm:w-96">
      <div class="mb-4 flex flex-col gap-6">
        <div class="relative h-11 w-full min-w-[200px]">
          <input
            v-model="name"
            class="peer h-full w-full rounded-md border bg-transparent px-3 py-3 font-sans text-sm font-normal text-blue-gray-700 outline outline-0 transition-all placeholder-shown:border placeholder-shown:border-t-blue-gray-200 focus:border-2 focus:border-green-500 focus:border-t-transparent focus:outline-0 disabled:border-0 disabled:bg-blue-gray-50"
            placeHolder=" "
          />
          <label
            class="pointer-events-none absolute left-0 -top-1.5 flex h-full w-full select-none text-[11px] font-normal leading-tight text-blue-gray-400 transition-all before:pointer-events-none before:mt-[6.5px] before:mr-1 before:box-border before:block before:h-1.5 before:w-2.5 before:rounded-tl-md before:border-t before:border-l before: before:transition-all after:pointer-events-none after:mt-[6.5px] after:ml-1 after:box-border after:block after:h-1.5 after:w-2.5 after:flex-grow after:rounded-tr-md after:border-t after:border-r after: after:transition-all peer-placeholder-shown:text-sm peer-placeholder-shown:leading-[4.1] peer-placeholder-shown:text-blue-gray-500 peer-placeholder-shown:before:border-transparent peer-placeholder-shown:after:border-transparent peer-focus:text-[11px] peer-focus:leading-tight peer-focus:text-green-300 peer-focus:before:border-t-2 peer-focus:before:border-l-2 peer-focus:before:!border-green-500 peer-focus:after:border-t-2 peer-focus:after:border-r-2 peer-focus:after:!border-green-500 peer-disabled:text-transparent peer-disabled:before:border-transparent peer-disabled:after:border-transparent peer-disabled:peer-placeholder-shown:text-blue-gray-500"
          >
            Name
          </label>
        </div>
      </div>
      <div class="mb-4 flex flex-col gap-6">
        <div class="relative h-11 w-full min-w-[200px]">
          <input
            class="peer h-full w-full rounded-md border bg-transparent px-3 py-3 font-sans text-sm font-normal text-blue-gray-700 outline outline-0 transition-all placeholder-shown:border placeholder-shown:border-t-blue-gray-200 focus:border-2 focus:border-green-500 focus:border-t-transparent focus:outline-0 disabled:border-0 disabled:bg-blue-gray-50"
            placeHolder=" "
            type="email"
            v-model="email"
          />
          <label
            class="pointer-events-none absolute left-0 -top-1.5 flex h-full w-full select-none text-[11px] font-normal leading-tight text-blue-gray-400 transition-all before:pointer-events-none before:mt-[6.5px] before:mr-1 before:box-border before:block before:h-1.5 before:w-2.5 before:rounded-tl-md before:border-t before:border-l before: before:transition-all after:pointer-events-none after:mt-[6.5px] after:ml-1 after:box-border after:block after:h-1.5 after:w-2.5 after:flex-grow after:rounded-tr-md after:border-t after:border-r after: after:transition-all peer-placeholder-shown:text-sm peer-placeholder-shown:leading-[4.1] peer-placeholder-shown:text-blue-gray-500 peer-placeholder-shown:before:border-transparent peer-placeholder-shown:after:border-transparent peer-focus:text-[11px] peer-focus:leading-tight peer-focus:text-green-300 peer-focus:before:border-t-2 peer-focus:before:border-l-2 peer-focus:before:!border-green-500 peer-focus:after:border-t-2 peer-focus:after:border-r-2 peer-focus:after:!border-green-500 peer-disabled:text-transparent peer-disabled:before:border-transparent peer-disabled:after:border-transparent peer-disabled:peer-placeholder-shown:text-blue-gray-500"
          >
            Email
          </label>
        </div>
      </div>
      <div class="mb-4 flex flex-col gap-6">
        <div class="relative h-11 w-full min-w-[200px]">
          <input
            class="peer h-full w-full rounded-md border bg-transparent px-3 py-3 font-sans text-sm font-normal text-blue-gray-700 outline outline-0 transition-all placeholder-shown:border placeholder-shown:border-t-blue-gray-200 focus:border-2 focus:border-green-500 focus:border-t-transparent focus:outline-0 disabled:border-0 disabled:bg-blue-gray-50"
            placeHolder=" "
            type="email"
            v-model="confirmEmail"
          />
          <label
            class="pointer-events-none absolute left-0 -top-1.5 flex h-full w-full select-none text-[11px] font-normal leading-tight text-blue-gray-400 transition-all before:pointer-events-none before:mt-[6.5px] before:mr-1 before:box-border before:block before:h-1.5 before:w-2.5 before:rounded-tl-md before:border-t before:border-l before: before:transition-all after:pointer-events-none after:mt-[6.5px] after:ml-1 after:box-border after:block after:h-1.5 after:w-2.5 after:flex-grow after:rounded-tr-md after:border-t after:border-r after: after:transition-all peer-placeholder-shown:text-sm peer-placeholder-shown:leading-[4.1] peer-placeholder-shown:text-blue-gray-500 peer-placeholder-shown:before:border-transparent peer-placeholder-shown:after:border-transparent peer-focus:text-[11px] peer-focus:leading-tight peer-focus:text-green-300 peer-focus:before:border-t-2 peer-focus:before:border-l-2 peer-focus:before:!border-green-500 peer-focus:after:border-t-2 peer-focus:after:border-r-2 peer-focus:after:!border-green-500 peer-disabled:text-transparent peer-disabled:before:border-transparent peer-disabled:after:border-transparent peer-disabled:peer-placeholder-shown:text-blue-gray-500"
          >
            Confirm Email
          </label>
        </div>
      </div>
      <div class="inline-flex items-center">
        <label
          class="relative -ml-2.5 flex cursor-pointer items-center rounded-full p-3"
          for="checkbox"
        >
          <input
            type="checkbox"
            class="peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-green-500 checked:bg-green-500 checked:before:bg-green-500"
            id="checkbox"
            :checked="consent"
            @change="checkBoxHandler"
          />
        </label>
        <label class="mt-px cursor-pointer select-none font-light text-gray-700" for="checkbox">
          <p
            class="flex items-center font-sans text-md font-normal leading-normal text-gray-400 antialiased"
          >
            I agree that
            <a
              href="https://vueschool.io/"
              target="_blank"
              class="text-green-600 mx-1 hover:text-green-500 transition-colors font-semibold"
              >VueSchool</a
            >
            is awesome.
          </p>
        </label>
      </div>
      <button
        class="mt-6 flex justify-center items-center w-full select-none rounded-lg bg-green-600 hover:bg-green-500 py-3 px-6 text-center align-middle font-sans text-md font-bold uppercase text-white shadow-md shadow-pink-500/20 transition-all focus:opacity-[0.85] focus:shadow-none active:opacity-[0.85] active:shadow-none disabled:pointer-events-none disabled:opacity-50 disabled:shadow-none"
        type="button"
      >
        Confirm
      </button>
    </form>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'

const defaultName = 'VueCool Form'
const defaultTitle = 'Tell Us About Yourself'

const formInfo = reactive({
  name: '',
  title: ''
})

const name = ref('')
const email = ref('')
const confirmEmail = ref('')

const consent = ref(false)

const checkBoxHandler = () => {
  consent.value = !consent.value
}
</script>

<style></style>
