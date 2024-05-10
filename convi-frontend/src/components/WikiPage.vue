<template>
<div class="l-wiki">
  <div class="l-task">
    <table class="p-taskTab">
      <tbody>
        <tr class="p-taskTab__menu">
          <td @click="change('1')" :class="{'active': isActive === '1'}" href="#">
            <a>ツール導入</a>
          </td>
          <td @click="change('2')" :class="{'active': isActive === '2'}" href="#">
            <a>進め方</a>
          </td>
          <td @click="change('3')" :class="{'active': isActive === '3'}" href="#">
            <a>コーディング規約</a>
          </td>
          <td @click="change('4')" :class="{'active': isActive === '4'}" href="#">
            <a>その他ルール</a>
          </td>
        </tr>
      </tbody>
    </table>
    <div class="p-taskList">
      <div class="p-taskItem" v-if="isActive === '1'">
        <ToolWiki/>
      </div>
      <div class="p-taskItem" v-if="isActive === '2'">
        <FlowWiki/>
      </div>
      <div class="p-taskItem" v-if="isActive === '3'">
        <CodeWiki/>
      </div>
      <div class="p-taskItem" v-if="isActive === '4'">
        <OtherWiki/>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import ToolWiki from '@/components/ToolWiki';
import FlowWiki from '@/components/FlowWiki';
import CodeWiki from '@/components/CodeWiki';
import OtherWiki from '@/components/OtherWiki';

export default {
  name: 'WikiPage',
  data() {
    return {
      isActive: '1',
    }
  },
  components: {
    ToolWiki,
    FlowWiki,
    CodeWiki,
    OtherWiki
  },
  methods: {
    change: function(num) {
      this.isActive = num
    }
  }
}
</script>


<style>
.l-wiki {
  width: 100%;
  height: 100%;
}

.p-taskTab {
  height: 40px;
  width: 100%;
  border-spacing: 0;
}

.p-taskTab__menu {
  height: 40px;
  width: 100%;
}

.p-taskTab__menu td {
  width: 25%;
  background-color: #404950;
  text-align: center;
  vertical-align: middle;
  border: 1px solid #B8C2C9;
  border-bottom: none;
}

.p-taskTab__menu td.active {
  background-color: #EF722F;
  text-align: center;
  vertical-align: middle;
}

.p-taskTab__menu a {
  color: #FFFFFF;
}

.p-taskTab__menu td.active a {
  color: #FFFFFF;
}

.p-taskList {
  height: calc(100vh - 128px);
  background-color: #FFFFFF;
  padding-top: 48px;
}

.p-taskItem {
  height: calc(100vh - 132px);
  margin: -24px 12px;
  padding: 0 18px;
  overflow-y: auto;
}

.p-taskItem::-webkit-scrollbar {
  width: 6px;
}

.p-taskItem::-webkit-scrollbar-track {
  background-color: #EDEDED;
  border-radius: 8px;
}

.p-taskItem::-webkit-scrollbar-thumb {
  background-color: #BCBCBC;
  border-radius: 8px;
}

@media screen and (max-width:773px) {
  .p-taskList {
    height: calc(100vh - 91px);
  }

  .p-taskItem {
    height: calc(100vh - 123px);
    padding: 16px 24px;
  }
}
</style>