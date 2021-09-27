<template>
    <Header />
    <section class="main">
    <Navbar />
    <Contactbar />
    </section>
</template>

<script>
import Header from '@/components/Header'
import Navbar from '@/components/Navbar'
import Contactbar from '@/components/Contactbar'

export default {
  name: 'App',
  components: {
    Header, Navbar, Contactbar
  }
}
</script>

<style lang="scss" scoped>
.main {
  position: relative;
  display: flex;
  justify-content: space-between;
  height: calc(100vh - .56rem);
}
</style>
