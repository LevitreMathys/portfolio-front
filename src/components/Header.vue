<template>

    <header class="fixed inset-x-0 top-4 z-50 flex justify-center px-4">
        <div class="flex justify-center rounded-full bg-black p-1.5 shadow-lg">
            <GooeyNav
                v-model:active-index="active"
                :items="items"
                theme="dark"
                color="#ff5a1f"
                :colors="['#ff5a1f', '#ff8a3a', '#ffb020']"
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