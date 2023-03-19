<template>
    <div id="content" class="pt-7">
        <div class="grid grid-cols-3 gap-6">
            <div class="col-span-2">
                <div class="relative w-full bg-[url('/images/patern.png')] bg-cover p-12 rounded-xl shadow-xl">
                    <div class="flex flex-row">
                        <div class="basis-1/2">
                            <p class="text-3xl font-bold text-white">Chelsea vs Arsenal</p>
                            <p class="text-sm text-white"><i class="ph ph-calendar"></i> 22 August 2023</p>
                            <p class="text-sm text-white"><i class="ph ph-clock"></i> 01:00 PM</p>
                            <p class="text-sm text-white"><i class="ph ph-map-pin-line"></i> in Wembley, England</p>
                        </div>
                        <div class="basis-1/2 absolute inset-y-1 right-24">
                            <img src="/images/match.png" class="w-72" alt="">
                        </div>
                    </div>
                </div>
            </div>
            <div class="row-span-2">
                <div class="flex flex-row items-center mb-4">
                    <div class="basis-1/2 items-start">
                        <p class="text-xl">Latest Transfer</p>
                    </div>
                    <div class="basis-1/2 flex place-content-end">
                        <a href="#" class="flex flex-row items-center space-x-2 hover:underline"><span>View all</span> <i class="ph ph-caret-right"></i></a>
                    </div>
                </div>
                <span v-if="$fetchState.pending"></span>
                <div class="w-full rounded-xl shadow-xl p-4 border border-gray-200 bg-white mb-4" v-else v-for="(item, i) in transfer" :key="i">
                    <div class="flex flex-row items-center justify-between mb-2">
                        <label class="text-xl">{{ item.player.name }}</label>
                        <label class="text-xs text-gray-400 text-right">
                            <p>{{ Math.floor(Math.random() * 10) }} hours ago</p>
                            <p>On Loan {{ item.transfers[0].date }}</p>
                        </label>
                    </div>
                    <div class="flex flex-row items-center justify-between">
                        <div class="flex flex-row space-x-2"> 
                            <p class="text-xs text-gray-400">Transfer fee</p>
                            <p class="text-xs">€ {{ Math.floor(Math.random() * 1000) }}K</p>
                        </div>
                        <div class="flex flex-row space-x-4">
                            <div class="h-5 w-5 rounded-full">
                                <img :src="item.transfers[0].teams.in.logo">
                            </div>
                            <div class="h-5 w-5 rounded-full bg-lime-500 flex items-center place-content-center">
                                <i class="ph ph-arrow-right font-bold"></i>
                            </div>
                            <div class="h-5 w-5 rounded-full">
                                <img :src="item.transfers[0].teams.out.logo">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-span-2">
                <div class="grid grid-cols-3 gap-4">
                    <div class="col-span-2">
                        <div class="w-full rounded-xl shadow-xl p-4 border border-gray-200 bg-white">
                            <div class="flex flex-row items-center">
                                <div class="basis-1/2 items-start">
                                    <p class="text-xl">Latest Matches</p>
                                </div>
                                <div class="basis-1/2 flex place-content-end">
                                    <a href="#" class="flex flex-row items-center space-x-2 hover:underline"><span>View all</span> <i class="ph ph-caret-right"></i></a>
                                </div>
                            </div>
                            <span v-if="$fetchState.pending"></span>
                            <div class="grid grid-cols-2 gap-4 mt-2" v-else>
                                <div class="w-full p-4 bg-[#e8e8e8] rounded-xl">
                                    <p class="text-xs mb-2">Matchday 10 of 38</p>
                                    <div class="flex flex-row place-content-center space-x-1">
                                        <div id="home" class="w-full grid justify-items-center text-center">
                                            <img :src="latest1.teams.home.logo" class="w-12" alt="">
                                        </div>
                                        <div id="score" class="bg-neutral-600 text-white flex flex-row items-center place-content-center rounded-lg w-full">
                                            <p class="text-lg font-bold">{{ latest1.goals.home }}</p>
                                            <p class="text-lg font-bold">&nbsp;:&nbsp;</p>
                                            <p class="text-lg font-bold">{{ latest1.goals.away }}</p>
                                        </div>
                                        <div id="away" class="w-full grid justify-items-center text-center">
                                            <img :src="latest1.teams.away.logo" class="w-12" alt="">
                                        </div>
                                    </div>
                                </div>
                                <div class="w-full p-4 bg-[#e8e8e8] rounded-xl">
                                    <p class="text-xs mb-2">Matchday 10 of 38</p>
                                    <div class="flex flex-row place-content-center space-x-1">
                                        <div id="home" class="w-full grid justify-items-center text-center">
                                            <img :src="latest2.teams.home.logo" class="w-12" alt="">
                                        </div>
                                        <div id="score" class="bg-neutral-600 text-white flex flex-row items-center place-content-center rounded-lg w-full">
                                            <p class="text-lg font-bold">{{ latest2.goals.home }}</p>
                                            <p class="text-lg font-bold">&nbsp;:&nbsp;</p>
                                            <p class="text-lg font-bold">{{ latest2.goals.away }}</p>
                                        </div>
                                        <div id="away" class="w-full grid justify-items-center text-center">
                                            <img :src="latest2.teams.away.logo" class="w-12" alt="">
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <span v-if="$fetchState.pending"></span>
                    <div class="w-full rounded-xl shadow-xl p-4 border border-gray-200 bg-white" v-else>
                        <div class="flex flex-row items-center space-x-7 mb-3">
                            <div class="items-start">
                                <p class="text-md">PL MATCH</p>
                                <p class="text-xs">Matchday 10 of 38</p>
                            </div>
                            <div class="flex flex-row items-center bg-lime-400 px-2 py-1 rounded space-x-2">
                                <span class="text-white">LIVE</span> <i class="w-2 h-2 rounded-full bg-green-500"></i>
                            </div>
                        </div>
                        <div class="flex flex-row place-content-center space-x-1 py-1">
                            <div id="home" class="w-full grid justify-items-center text-center">
                                <img :src="live.teams.home.logo" class="w-24" alt="">
                            </div>
                            <div id="score" class="flex flex-row items-center place-content-center rounded-lg w-full">
                                <p class="text-2xl font-bold">{{ live.goals.home }}</p>
                                <p class="text-2xl font-bold">&nbsp;:&nbsp;</p>
                                <p class="text-2xl font-bold">{{ live.goals.away }}</p>
                            </div>
                            <div id="away" class="w-full grid justify-items-center text-center">
                                <img :src="live.teams.away.logo" class="w-24" alt="">
                            </div>
                        </div>
                        <div class="flex place-content-center">
                            <a href="#" class="flex flex-row items-center text-xs">Detail<i class="ph ph-caret-right"></i></a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="grid grid-cols-3 gap-6 mt-5">
            <div class="col-span-2">
                <div class="flex flex-row items-center mb-4">
                    <div class="basis-1/2 items-start">
                        <p class="text-xl">{{ this.$route.params.id }} Tables</p>
                    </div>
                    <div class="basis-1/2 flex place-content-end">
                    </div>
                </div>
                <div class="w-full rounded-xl shadow-xl p-4 border border-gray-200 bg-white">
                    <table class="table-auto w-full">
                        <thead>
                            <tr>
                                <th class="text-left">Position</th>
                                <th class="text-left">Club</th>
                                <th class="text-left">Played</th>
                                <th class="text-left">W</th>
                                <th class="text-left">D</th>
                                <th class="text-left">L</th>
                                <th class="text-left">Point</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-if="$fetchState.pending"></tr>
                            <tr v-else v-for="(item,i) in standing" :key="i">
                                <td class="p-2">{{ item.rank }}</td>
                                <td class="p-2">
                                    <div class="flex flex-row items-center space-x-5">
                                        <img :src="item.team.logo" class="w-10 rounded-full" />
                                        <p>{{ item.team.name }}</p>
                                    </div>
                                </td>
                                <td class="p-2">{{ item.all.played }}</td>
                                <td class="p-2">{{ item.all.win }}</td>
                                <td class="p-2">{{ item.all.draw }}</td>
                                <td class="p-2">{{ item.all.lose }}</td>
                                <td class="p-2">{{ item.points }}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            <div class="bg-transparent">
                <div class="flex flex-row items-center mb-4">
                    <div class="basis-1/2 items-start">
                        <p class="text-xl">Top Scorer</p>
                    </div>
                    <div class="basis-1/2 flex place-content-end">
                        <a href="#" class="flex flex-row items-center space-x-2 hover:underline"><span>View all</span> <i class="ph ph-caret-right"></i></a>
                    </div>
                </div>
                <div class="w-full rounded-xl shadow-xl py-4 border border-gray-200 bg-white">
                    <ul>
                        <span v-if="$fetchState.pending"></span>
                        <li class="flex flex-row items-center justify-between p-2 px-4 hover:bg-neutral-100 hover:cursor-pointer" v-else v-for="(item, i) in topscorer" :key="i">
                            <div class="flex flex-row space-x-2 items-center">
                                <div id="image">
                                    <img :src="item.player.photo" class="h-10 rounded-full">
                                </div>
                                <label> {{ item.player.name }}</label>
                            </div>
                            <label class="font-bold">{{ item.statistics[0].goals.total }} GOALS</label>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'MatchPage',
    data() {
        return {
            latest1: {},
            latest2: {},
            live: {},
            fixtures: [],
            transfer: [],
            topscorer: [],
            standing: [],
        }
    },
    async fetch() {
        let response = await this.$axios.get('/json/fixtures.json');
        this.fixtures = response.data.response;
        this.latest1 = this.fixtures[Math.floor(Math.random() * this.fixtures.length)]
        this.latest2 = this.fixtures[Math.floor(Math.random() * this.fixtures.length)]
        this.live = this.fixtures[Math.floor(Math.random() * this.fixtures.length)]

        let resTransfer = await this.$axios.get('/json/transfer.json');
        let tempTransfer = resTransfer.data.response
        this.transfer.push(tempTransfer[Math.floor(Math.random() * tempTransfer.length)])
        this.transfer.push(tempTransfer[Math.floor(Math.random() * tempTransfer.length)])
        this.transfer.push(tempTransfer[Math.floor(Math.random() * tempTransfer.length)])

        let resTopscorer = await this.$axios.get('/json/topscore.json');
        this.topscorer = resTopscorer.data.response

        let resstanding = await this.$axios.get('/json/standing.json');
        this.standing = resstanding.data.response[0].league.standings[0]
        console.log(this.standing)
    },
}
</script>
<style scoped>
tbody tr:nth-of-type(odd) { background-color: #e8e8e8; }
tbody tr:nth-of-type(even) { background-color: #ffffff; }
</style>