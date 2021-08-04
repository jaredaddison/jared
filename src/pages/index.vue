<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
const name = ref('')
const router = useRouter()

const dog = () => {
  if (name.value)
    router.push(`/dog/${encodeURIComponent(name.value)}`)
}

const cat = () => {
  if (name.value)
    router.push(`/cat/${encodeURIComponent(name.value)}`)
}
</script>

<template>
  <div
    class="dark:bg-gradient-to-tr from-gray-600 via-gray-700 to-gray-900 min-h-screen min-w-screen relative overflow-hidden"
  >
    <div class="hidden sm:block sm:absolute sm:h-full sm:w-full sm:inset-y-0">
      <div class="h-full mx-auto max-w-7xl relative">
        <svg
          class="right-full transform translate-y-1/4 translate-x-1/4 absolute lg:translate-x-1/2"
          width="404"
          height="784"
          fill="none"
          viewBox="0 0 404 784"
        >
          <defs>
            <pattern
              id="f210dbf6-a58d-4871-961e-36d5016a0f49"
              x="0"
              y="0"
              width="20"
              height="20"
              patternUnits="userSpaceOnUse"
              animate="ease-in"
            >
              <rect
                x="0"
                y="0"
                width="4"
                height="4"
                class="text-gray-400"
                fill="currentColor"
              />
            </pattern>
          </defs>
          <rect
            width="404"
            height="784"
            fill="url(#f210dbf6-a58d-4871-961e-36d5016a0f49)"
          />
        </svg>
        <svg
          class="left-full transform -translate-y-3/4 -translate-x-1/4 absolute md:-translate-y-1/2 lg:-translate-x-1/2"
          width="404"
          height="784"
          fill="none"
          viewBox="0 0 404 784"
        >
          <defs>
            <pattern
              id="5d0dd344-b041-4d26-bec4-8d33ea57ec9b"
              x="0"
              y="0"
              width="20"
              height="20"
              patternUnits="userSpaceOnUse"
            >
              <rect
                x="0"
                y="0"
                width="4"
                height="4"
                class="text-gray-400"
                fill="currentColor"
              />
            </pattern>
          </defs>
          <rect
            width="404"
            height="784"
            fill="url(#5d0dd344-b041-4d26-bec4-8d33ea57ec9b)"
          />
        </svg>
      </div>
    </div>
    <div class="pt-3 pb-12 relative sm:pb-20">
      <header class="mx-auto mt-16 max-w-5xl px-4 sm:mt-24">
        <div class="text-center">
          <h1
            class="font-extrabold tracking-tight text-4xl text-gray-900 sm:text-5xl md:text-6xl"
          >
            <span
              class="text-gray-400 text-5xl block xl:inline xl:mx-5 l:mx-6 md:mx-4 sm:mx-1"
            >{{ t('HeroHome.title') }}</span>
            <br />
            {{ " " }}
            <span class="text-4xl text-gray-100/75 block xl:inline">
              {{ t('HeroHome.subtitle') }}
            </span>
          </h1>
          <p
            class="mx-auto max-w-md mt-3 text-base text-gray-500 sm:text-lg md:text-xl md:mt-5 md:max-w-3xl"
          >
            {{ t('HeroHome.about') }}
          </p>
        </div>
      </header>
      <div class="shadow-xl">
        <div class="py-2" />

        <div class="bg-hex-121212 mx-auto ml-10 mr-10 p-10 align-content-center text-center shadow-xl">
          <p class="text-5xl text-gray-100">
            <mdi-dog class="inline-block" />
          </p>
          <p class="text-4xl text-gray-100">
            {{ t('DogFluids.title') }}
          </p>
          <p class="text-2xl">
            <em class="text-sm text-gray-100/50">
              {{ t('DogFluids.subtitle') }}
            </em>
          </p>

          <div class="py-2" />
          <input
            id="input"
            v-model="name"
            :placeholder="t('DogFluids.petname')"
            :aria-label="t('DogFluids.petname')"
            type="text"
            autocomplete="false"
            class="text mx-auto my-auto px-4 py-2 w-250px text-center border-rounded border-gray-100 bg-gray-100 outline-none active:{text-gray-900 border-2 border-green-400}"
            @keydown.enter="dog"
          >
          <label class="hidden" for="input">{{ t('DogFluids.petname') }}</label>
          <div>
            <button
              class="m-3 text-sm btn"
              :disabled="!name"
              @click="dog"
            >
              {{ t('button.go') }}
            </button>
          </div>
        </div>
      </div>
      <div class="shadow-xl">
        <div class="py-2" />

        <div class="bg-hex-121212 mx-auto ml-10 mr-10 p-10 align-content-center text-center shadow-xl">
          <p class="text-5xl text-gray-100">
            <mdi-cat class="inline-block" />
          </p>
          <p class="text-4xl text-gray-100">
            {{ t('CatFluids.title') }}
          </p>
          <p class="text-2xl">
            <em class="text-sm text-gray-100/50">
              {{ t('CatFluids.subtitle') }}
            </em>
          </p>

          <div class="py-2" />

          <input
            id="input"
            v-model="name"
            :placeholder="t('CatFluids.petname')"
            :aria-label="t('CatFluids.petname')"
            type="text"
            autocomplete="false"
            class="text mx-auto my-auto px-4 py-2 w-250px text-center border-rounded border-gray-100 bg-gray-100 outline-none active:{text-gray-900 border-2 border-green-400}"
            @keydown.enter="cat"
          >
          <label class="hidden" for="input">{{ t('CatFluids.petname') }}</label>
          <div>
            <button
              class="m-3 text-sm btn"
              :disabled="!name"
              @click="cat"
            >
              {{ t('button.go') }}
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
