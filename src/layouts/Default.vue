<template>
  <transition name="fade" mode="out-in">
    <router-view />
  </transition>
</template>

<style lang="scss">
/* PAGE TRANSITIONS */
.fade-enter-active,
.fade-leave-active {
  opacity: 1;
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
  max-height: 0;
}
</style>
