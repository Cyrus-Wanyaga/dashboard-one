<template>
    <div class="flex flex-wrap flex-col md:flex-row items-center">
        <div v-for="(member, index) in members" :key="index"
             class="px-4 py-4 md:py-0 w-full flex-auto md:flex-1 flex flex-row items-center"
             :class="{'border-b md:border-none': listIndex(index)}"
        >
            <div class="relative active-profile">
                <img :src="`https://i.pravatar.cc/150?img=${member.id}`"
                     class="rounded-full h-12 w-12 object-center object-cover" alt="">
                <span v-if="member.active"
                      class="absolute right-0 -mt-3 mr-1 border-2 border-white bg-teal-love rounded-full absolute shadow-teal-love"></span>
            </div>
            <div class="ml-4 flex flex-col">
                <span class="text-gray-700 text-md md:text-xs font-semibold">{{member.name}}</span>
                <span class="text-gray-400 text-xs font-semibold">{{member.points}} points</span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            members: Array
        },
        methods: {
            listIndex(item) {
                return item !== this.members.length - 1;
            }
        }
    }
</script>
