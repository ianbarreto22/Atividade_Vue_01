<template>
    <div className="panel">
        <Tab v-for="(tab, index) in tabs"
            :key="index"
            :index="index"
            v-bind="tab"
            :selected="currentTab"
            @on-selection="select">
        </Tab>

        <div className="box">
            <p>{{tabs[currentTab].content}}</p>
        </div>
    </div>
</template>

<script setup lang="ts">
    import {ref} from 'vue'
    import Tab, {type TabProps} from './Tab.vue'

    const tabs: TabProps[] = [
    {
      title: "Tab 1",
      content: "Conteúdo da primeira tab!"
    },
    {
      title: "Tab 2",
      content: "Conteúdo da segunda tab!"
    },
    {
      title: "Tab 3",
      content: "Conteúdo da terceira tab!"
    },
    {
      title: "Tab 4",
      content: "Conteúdo da quarta tab!"
    },
  ]

  const currentTab = ref(0)

  function select(tabIndex: number){
      currentTab.value = tabIndex
  }
</script>

<style>
    div .panel{
        margin: 100px;
    }

    .box{
        border: 3px solid lightslategray;
        border-radius: 0px 10px 10px 10px;
        padding: 15px;
    }
</style>