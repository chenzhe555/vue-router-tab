<template>
  <router-tab>
    <template v-slot="{ tab: { id, title, icon, closable }, tabs, index}">
      <i v-if="icon" class="tab-icon" :class="icon" />
      <span class="tab-title">{{ $routerTab.i18nText(title) || '未命名页签' }}</span>
      <span class="tab-badge">{{ index }}</span>
      <i
        v-if="closable !== false && tabs.length > 1"
        class="tab-close"
        @click.prevent="$routerTab.closeTab(id)"
      />
    </template>
  </router-tab>
</template>

<style lang="scss" scoped>
.tab-badge {
  $s: 1.2em;
  display: inline-block;
  margin-left: 3px;
  width:  $s;
  height:  $s;
  font-size: 12px;
  line-height: $s;
  vertical-align: super;
  text-align: center;
  color: #fff;
  background-color: #f80;
  border-radius: 100%;
}

.router-tab-item.actived .tab-badge {
  background-color: #f50;
}
</style>
