<template>
    <div class="container">
        <div id="page">
            <transition name="fade">
                <router-view></router-view>
            </transition>
        </div>
        <div>
            <h1>Hello</h1>
        </div>
    </div>
</template>

<style>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-active {
    opacity: 0;
}
</style>

<script>

export default {
    data() {
        return {

        }
    }
}
</script>
