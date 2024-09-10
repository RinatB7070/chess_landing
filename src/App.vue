<template>
  <div>
    <AppHeader :isMobile="this.isMobile"></AppHeader>
    <RunningLine></RunningLine>
    <AppMeta :isMobile="this.isMobile"></AppMeta>
    <AppInfo :isMobile="this.isMobile"></AppInfo>
    <AppMembers :isMobile="this.isMobile"></AppMembers>
    <RunningLine style="margin-bottom: 0px"></RunningLine>
    <AppFooter></AppFooter>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import RunningLine from './components/RunningLine.vue';
import AppMeta from './components/AppMeta.vue';
import AppInfo from './components/AppInfo.vue';
import AppMembers from './components/AppMembers.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  data () {
    const mediaMobile = window.matchMedia('(max-width: 480px)');
    return {
        mediaMobile,
        isMobile: mediaMobile.matches
    }
  },
  mounted() {
    this.mediaMobile.addEventListener('change', () => {
      this.isMobile = this.mediaMobile.matches;
    }) 
  },
  components: {
    AppHeader,
    RunningLine,
    AppMeta,
    AppInfo,
    AppMembers,
    AppFooter
  }
}
</script>
