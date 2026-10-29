<template>

    <ProfileCard
        :avatar-url="me"
        name="Mathys Levitre"
        title="Développeur fullstack"
        handle="LevitreMathys"
        status="Online"
        theme="dark"
        backdrop-color="#a78bfa"
        @contact-click="onContactClick"
    />

</template>

<script setup lang="ts">
    import ProfileCard from '~/components/ui/profile-card/ProfileCard.vue';
    import me from '@/assets/me.png'

    function onContactClick() {
        console.log('contact');
    }
</script>