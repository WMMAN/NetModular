<template>
  <section class="nm-main">
    <nm-header/>
    <nm-tabnav/>
    <section class="nm-content">
      <transition name="fade-transverse">
        <keep-alive :include="keepAlive">
          <router-view :key="$route.path"/>
        </keep-alive>
      </transition>
    </section>
  </section>
</template>
<script>
import NmHeader from '../header'
import { mapState } from 'vuex'
export default {
  components: { NmHeader },
  computed: {
    ...mapState('app/page', ['keepAlive'])
  }
}
</script>
