<template>

    <header class="fixed inset-x-0 top-4 z-50 flex justify-center px-4">
        <div class="flex justify-center rounded-full bg-[#0b0618]/70 p-1.5 shadow-lg shadow-violet-950/40 ring-1 ring-white/10 backdrop-blur-md">
            <GooeyNav
                v-model:active-index="active"
                :items="items"
                theme="dark"
                color="#7c3aed"
                :colors="['#7c3aed', '#a78bfa', '#c4b5fd']"
                :particle-count="15"
                :spread="56"
                class="[&_.gooey-nav\_\_list]:justify-center"
            />
        </div>
    </header>

</template>

<script lang="ts" setup>

    import { ref } from 'vue';
    import GooeyNav from '~/components/ui/gooey-nav/GooeyNav.vue';

    const items = [
        { label: 'Home', href: '#', icon: 'lucide:house' },
        { label: 'Work', href: '#', icon: 'lucide:briefcase' },
        { label: 'About', href: '#', icon: 'lucide:user' },
        { label: 'Contact', href: '#', icon: 'lucide:mail' },
    ];
    const active = ref(0);
</script>