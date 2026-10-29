<template>

    <div class="relative h-dvh w-full overflow-hidden bg-black">
    <Grainient
        :colors="['#120f17', '#3f0d1a', '#be123c', '#fb923c', '#fde68a']"
        :angle="150"
        :bands="1"
        :softness="1"
        :silk="0.4"
    />
    </div>


</template>

<script lang="ts" setup>

    import Grainient from '~/components/ui/grainient/Grainient.vue';
    
</script>