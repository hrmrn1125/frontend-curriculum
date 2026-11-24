<template>
  <div class="l-mypage">
    <div class="l-main">
      <div v-if="isActive === 'WikiPage'">
        <WikiPage/>
      </div>
    </div>
  </div>
</template>

<script>
import WikiPage from '@/components/WikiPage';

export default {
  name: 'TopPage',
  data() {
    return {
      isActive: 'WikiPage',
      isToggle: false
    }
  },
  components: {
    WikiPage
  },
  methods: {
    handleToggle() {
      this.isToggle = !this.isToggle
    },
    // transition hook
    beforeEnter(el) {
        el.style.height = '0'
    },
    enter(el) {
        el.style.height = el.scrollHeight + 'px'
    },
    beforeLeave(el) {
        el.style.height = el.scrollHeight + 'px'
    },
    leave(el) {
        el.style.height = '0'
    },
    change: function(num) {
      this.isActive = num
    }
  }
}
</script>

<style>
.l-mypage {
  display: flex;
}

.l-sidebar {
  width: 200px;
  height: 100vh;
  background-color: #404950;
  box-shadow: 3px 0px 6px -6px #00000019;
  position: relative;
}

.l-sidebar__inner {
  display: block;
  width: 176px;
  height: 100vh;
  left: 12px;
  position: absolute;
}

.p-sidebarLogo {
  width: 176px;
  margin: 20px auto;
}

.p-sidebarLogo img {
  width: 176px;
}

.p-sidebarMenuList {
  margin: 0 auto;
  max-height: calc(100vh - 166px);
  overflow-y: auto;
}

.p-sidebarMenuList::-webkit-scrollbar {
  width: 6px;
}

.p-sidebarMenuList::-webkit-scrollbar-track {
  background-color: #EDEDED;
  border-radius: 8px;
}

.p-sidebarMenuList::-webkit-scrollbar-thumb {
  background-color: #BCBCBC;
  border-radius: 8px;
}

.p-sidebarMenuItem {
  margin: 0 auto 24px;
}

.c-sidebarLink {
  word-break: break-all;
  font-size: 16px;
  font-weight: 600;
  color: #FFFFFF;
}

.p-toggleButton {
  border: none;
  background-color: #404950;
  font-size: 16px;
  font-weight: 600;
  color: #FFFFFF;
}

.toggle-slide-enter-active,
.toggle-slide-leave-active {
  transition: all 0.2s;
  overflow: hidden;
}
.toggle-slide-enter,
.toggle-slide-leave-to {
  height: 0;
  transition: all 0.2s;
}

.l-main {
  width: calc(100% - 240px);
  margin: 20px;
}
</style>
