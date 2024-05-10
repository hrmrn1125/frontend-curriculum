<template>
  <div class="l-mypage">
    <div class="l-sidebar">
      <div class="l-sidebar__inner">
        <div class="p-sidebarLogo" v-on:click="goToTop">
          <img src="../assets/images/front-logo.png" alt="Convi.comロゴ">
        </div>
        <div class="p-sidebarMenuList">
          <div @click="change('WikiPage')" :class="{'active': isActive === 'WikiPage'}">
            <a class="c-sidebarLink">Wiki</a>
          </div>
          <div>
            <button class="p-toggleButton" @click="handleToggle">DivPuzzle</button>
            <transition
              name="toggle-slide"
              @before-enter="beforeEnter"
              @enter="enter"
              @before-leave="beforeLeave"
              @leave="leave">
              <ul v-show="isToggle">
                <li @click="change('DivPuzzleLesson1')" :class="{'active': isActive === 'DivPuzzleLesson1'}">
                  <a class="c-sidebarLink">DivPuzzle – Lesson1</a>
                </li>
                <li @click="change('DivPuzzleLesson2')" :class="{'active': isActive === 'DivPuzzleLesson2'}">
                  <a class="c-sidebarLink">DivPuzzle–Lesson2</a>
                </li>
                <li @click="change('DivPuzzleLesson3')" :class="{'active': isActive === 'DivPuzzleLesson3'}">
                  <a class="c-sidebarLink">DivPuzzle–Lesson3</a>
                </li>
              </ul>
            </transition>
          </div>
        </div>
      </div>
    </div>
    <div class="l-main">
      <div v-if="isActive === 'WikiPage'">
        <WikiPage/>
      </div>
      <div v-if="isActive === 'DivPuzzleLesson1'">
        <DivPuzzleLesson1/>
      </div>
      <div v-if="isActive === 'DivPuzzleLesson2'">
        <DivPuzzleLesson2/>
      </div>
      <div v-if="isActive === 'DivPuzzleLesson3'">
        <DivPuzzleLesson3/>
      </div>
    </div>
  </div>
</template>

<script>
import WikiPage from '@/components/WikiPage';
import DivPuzzleLesson1 from '@/components/DivPuzzleLesson1';
import DivPuzzleLesson2 from '@/components/DivPuzzleLesson2';
import DivPuzzleLesson3 from '@/components/DivPuzzleLesson3';

export default {
  name: 'TopPage',
  data() {
    return {
      isActive: 'WikiPage',
      isToggle: false
    }
  },
  components: {
    WikiPage,
    DivPuzzleLesson1,
    DivPuzzleLesson2,
    DivPuzzleLesson3
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
