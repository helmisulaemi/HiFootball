<template>
  <div id="content" class="pt-7">
    <div class="flex justify-center">
      <div class="relative z-0">
          <span class="absolute inset-y-0 left-0 flex items-center p-5">
              <i class="ph ph-magnifying-glass text-slate-500 text-md font-bold"></i>
          </span>
          <input type="search" name="search" class="w-[40rem] p-3 pl-14 text-md text-slate-500 bg-white rounded-md shadow-md" placeholder="Search..." autocomplete="off" v-model="item.search">
      </div>
    </div>
    <div class="flex justify-center mt-5">
      <span class="text-2xl font-bold">Choice League</span>
    </div>
    <div class="flex justify-center mt-1">
      <span class="text-md">please select a league below</span>
    </div>
    <div id="league" class="grid grid-cols-4 gap-4 mt-5">
      <div class="max-w-sm p-4 border border-gray-200 rounded shadow animate-pulse md:p-6" v-if="$fetchState.pending">
          <div class="flex items-center justify-center w-14 mb-4 bg-gray-300 rounded">
              <svg class="w-10 h-10 text-gray-200" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" fill="currentColor" viewBox="0 0 640 512">
                <path d="M480 80C480 35.82 515.8 0 560 0C604.2 0 640 35.82 640 80C640 124.2 604.2 160 560 160C515.8 160 480 124.2 480 80zM0 456.1C0 445.6 2.964 435.3 8.551 426.4L225.3 81.01C231.9 70.42 243.5 64 256 64C268.5 64 280.1 70.42 286.8 81.01L412.7 281.7L460.9 202.7C464.1 196.1 472.2 192 480 192C487.8 192 495 196.1 499.1 202.7L631.1 419.1C636.9 428.6 640 439.7 640 450.9C640 484.6 612.6 512 578.9 512H55.91C25.03 512 .0006 486.1 .0006 456.1L0 456.1z"/>
              </svg>
          </div>
          <div class="h-2.5 bg-gray-200 rounded-full w-48 mb-4"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full"></div>
          <div class="h-2.5 bg-gray-200 rounded-full mt-4 w-32 mb-2"></div>
      </div>
      <div class="max-w-sm p-4 border border-gray-200 rounded shadow animate-pulse md:p-6" v-if="$fetchState.pending">
          <div class="flex items-center justify-center w-14 mb-4 bg-gray-300 rounded">
              <svg class="w-10 h-10 text-gray-200" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" fill="currentColor" viewBox="0 0 640 512">
                <path d="M480 80C480 35.82 515.8 0 560 0C604.2 0 640 35.82 640 80C640 124.2 604.2 160 560 160C515.8 160 480 124.2 480 80zM0 456.1C0 445.6 2.964 435.3 8.551 426.4L225.3 81.01C231.9 70.42 243.5 64 256 64C268.5 64 280.1 70.42 286.8 81.01L412.7 281.7L460.9 202.7C464.1 196.1 472.2 192 480 192C487.8 192 495 196.1 499.1 202.7L631.1 419.1C636.9 428.6 640 439.7 640 450.9C640 484.6 612.6 512 578.9 512H55.91C25.03 512 .0006 486.1 .0006 456.1L0 456.1z"/>
              </svg>
          </div>
          <div class="h-2.5 bg-gray-200 rounded-full w-48 mb-4"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full"></div>
          <div class="h-2.5 bg-gray-200 rounded-full mt-4 w-32 mb-2"></div>
      </div>
      <div class="max-w-sm p-4 border border-gray-200 rounded shadow animate-pulse md:p-6" v-if="$fetchState.pending">
          <div class="flex items-center justify-center w-14 mb-4 bg-gray-300 rounded">
              <svg class="w-10 h-10 text-gray-200" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" fill="currentColor" viewBox="0 0 640 512">
                <path d="M480 80C480 35.82 515.8 0 560 0C604.2 0 640 35.82 640 80C640 124.2 604.2 160 560 160C515.8 160 480 124.2 480 80zM0 456.1C0 445.6 2.964 435.3 8.551 426.4L225.3 81.01C231.9 70.42 243.5 64 256 64C268.5 64 280.1 70.42 286.8 81.01L412.7 281.7L460.9 202.7C464.1 196.1 472.2 192 480 192C487.8 192 495 196.1 499.1 202.7L631.1 419.1C636.9 428.6 640 439.7 640 450.9C640 484.6 612.6 512 578.9 512H55.91C25.03 512 .0006 486.1 .0006 456.1L0 456.1z"/>
              </svg>
          </div>
          <div class="h-2.5 bg-gray-200 rounded-full w-48 mb-4"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full"></div>
          <div class="h-2.5 bg-gray-200 rounded-full mt-4 w-32 mb-2"></div>
      </div>
      <div class="max-w-sm p-4 border border-gray-200 rounded shadow animate-pulse md:p-6" v-if="$fetchState.pending">
          <div class="flex items-center justify-center w-14 mb-4 bg-gray-300 rounded">
              <svg class="w-10 h-10 text-gray-200" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" fill="currentColor" viewBox="0 0 640 512">
                <path d="M480 80C480 35.82 515.8 0 560 0C604.2 0 640 35.82 640 80C640 124.2 604.2 160 560 160C515.8 160 480 124.2 480 80zM0 456.1C0 445.6 2.964 435.3 8.551 426.4L225.3 81.01C231.9 70.42 243.5 64 256 64C268.5 64 280.1 70.42 286.8 81.01L412.7 281.7L460.9 202.7C464.1 196.1 472.2 192 480 192C487.8 192 495 196.1 499.1 202.7L631.1 419.1C636.9 428.6 640 439.7 640 450.9C640 484.6 612.6 512 578.9 512H55.91C25.03 512 .0006 486.1 .0006 456.1L0 456.1z"/>
              </svg>
          </div>
          <div class="h-2.5 bg-gray-200 rounded-full w-48 mb-4"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full mb-2.5"></div>
          <div class="h-2 bg-gray-200 rounded-full"></div>
          <div class="h-2.5 bg-gray-200 rounded-full mt-4 w-32 mb-2"></div>
      </div>
      <div class="card" v-else v-for="(item, key) in filteredList" :key="key">
        <img :src="item.league.logo" class="card-img" :alt="item.league.name">
        <div class="card-tittle">{{ item.league.name }}</div>
        <p class="card-desc">Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        <button type="button" @click="openLeague(item.league.name)" class="card-button">Open league <i class="ph ph-sign-in text-lg ml-4"></i></button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'LeaguePage',
  data() {
      return {
          league: [],
          item: {
            search: ''
          }
      }
  },
  async fetch() {
      let response = await this.$axios.get('/json/league.json');
      this.league = response.data.response;
      var filter = this.league.filter(x => {
        return x.country.name.toLowerCase().includes(this.$route.params.id.toLowerCase());
      })
      this.league = filter
  },
  methods: {
    openLeague(id) {
      this.$router.push({
            name: 'match-id',
            params: {
                id: id
            }
        })
    }
  },
  computed: {
    filteredList() {
      return this.league.filter(post => {
        return post.league.name.toLowerCase().includes(this.item.search.toLowerCase())
      })
    }
  }
}
</script>