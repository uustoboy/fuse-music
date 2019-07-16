<template>
    <div>
        <header-bar/>
        <play-bar></play-bar>
    </div>
</template>

<script>
  import HeaderBar from '@/components/header/header'
  import PlayBar from '@/components/play/play'
  export default {
    name: 'index',
    components: {
      HeaderBar,
      PlayBar
    }
  }
</script>

<style scoped>

</style>
