<template>
  <div class="p-4">
    <CollapseContainer title="在下面输入框输入文本,切换后回来内容会保存">
      <a-input placeholder="请输入" />
    </CollapseContainer>

    <CollapseContainer class="mt-4 px-4" title="标签页操作">
      <a-button class="mr-2" @click="closeAll">关闭所有</a-button>
      <a-button class="mr-2" @click="closeLeft">关闭左侧</a-button>
      <a-button class="mr-2" @click="closeRight">关闭右侧</a-button>
      <a-button class="mr-2" @click="closeOther">关闭其他</a-button>
      <a-button class="mr-2" @click="closeCurrent">关闭当前</a-button>
      <a-button class="mr-2" @click="refreshPage">刷新当前</a-button>
      <a-button class="mr-2" @click="openTab">打开图标界面tab</a-button>
    </CollapseContainer>
  </div>
</template>
<script lang="ts">
  import { defineComponent } from 'vue';
  import { CollapseContainer } from '/@/components/Container/index';
  import { PageEnum } from '/@/enums/pageEnum';
  import { useTabs } from '/@/hooks/web/useTabs';
  export default defineComponent({
    name: 'TabsDemo',
    components: { CollapseContainer },
    setup() {
      const {
        closeAll,
        closeLeft,
        closeRight,
        closeOther,
        closeCurrent,
        refreshPage,
        addTab,
      } = useTabs();

      return {
        closeAll,
        closeLeft,
        closeRight,
        closeOther,
        closeCurrent,
        refreshPage,
        openTab: () => {
          addTab('/feat/icon' as PageEnum, true);
        },
      };
    },
  });
</script>
