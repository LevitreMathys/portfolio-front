<template>

    <div class="relative h-dvh w-full overflow-hidden bg-black">
    <Grainient
        :colors="['#0b0618', '#2e1065', '#7c3aed', '#c4b5fd', '#f5f3ff']"
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