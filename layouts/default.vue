<template>
  <div class="font-main flex flex-wrap justify-around">
    <header class="w-64 h-64">
      <div class="w-64 mt-24 ml-30 relative md:fixed">
        <div class="flex">
          <div class="bg-center bg-cover w-16 h-16 mr-2 rounded-full shadow photo"></div>
          <div>
            <h1 class="font-bold">Ryo Suzuki</h1>
            <p class="text-xs text-justify">とてもよわい</p>
          </div>
        </div>
        <div class="flex justify-around mt-5 text-xs">
          <nuxt-link to="/">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faCode" />
              </fa-layers>
              Works
            </button>
          </nuxt-link>
          <a href="https://twitter.com/barackobama" target="_blank" rel="noopener noreferrer">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faTwitter" />
              </fa-layers>
              Twitter
            </button>
          </a>
          <a href="https://github.com/snsn1024" target="_blank" rel="noopener noreferrer">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faGithub" />
              </fa-layers>
              Github
            </button>
          </a>
        </div>
        <input type="text" placeholder="Keywords"
          class="bg-gray-300 p-2 text-xs rounded w-full mt-5 focus:outline-none"
          v-model="keyword" @keypress.enter="$router.push('/search/' + keyword)">
      </div>
    </header>
    <main class="w-full mt-10">
      <nuxt />
    </main>
  </div>
</template>

<script>
  import { faTwitter } from '@fortawesome/free-brands-svg-icons'
  import { faGithub } from '@fortawesome/free-brands-svg-icons'
  import { faCode } from '@fortawesome/free-solid-svg-icons'
  export default {
    data() {
      return {
        keyword: ''
      }
    },
    computed: {
      faCode() {
        return faCode
      },
      faTwitter() {
        return faTwitter
      },
      faGithub() {
        return faGithub
      }
    }  
  }
</script>

<style>
  main {
    max-width: 550px;
  }
  .photo {
    min-width: 4rem;
    min-height: 4rem;
    background-image: url('https://pbs.twimg.com/profile_images/1139158874/_____400x400.jpeg');
  }
  button:focus {
    outline: none;
  }
</style>