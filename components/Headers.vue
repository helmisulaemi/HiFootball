<template>
    <header class="fixed w-screen left-0 top-0 right-0 shadow-sm bg-[#F6F6F4] z-50">
        <nav class="container mx-auto flex flex-row p-2 items-center">
            <div class="basis-1/2 flex flex-row items-center space-x-4">
                <div class="py-1">
                    <Nuxt-link :to="{ name: 'index' }">
                        <img src="/images/logo.png" alt="" class="w-28">
                    </Nuxt-link>
                </div>
            </div>
            <div class="basis-1/2 flex justify-center">
                <ul class="flex flex-row space-x-8">
                    <li class="flex flex-row items-center"><Nuxt-link :to="{ name: 'index' }">Home</Nuxt-link></li>
                    <li class="flex flex-row items-center"><Nuxt-link :to="{ name: 'event' }">Event</Nuxt-link></li>
                    <li class="flex flex-row items-center"><a href="javascript:void(0)">About</a></li>
                </ul>
            </div>
        </nav>
    </header>
</template>