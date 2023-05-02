<template>
  <div class="row row-equal">
    <div class="flex x16 xs12 lg3">
      <va-card>
        <va-card-content>
          <h2 class="va-h2 ma-0" :style="{ color: colors.primary }">53</h2>
          <p class="no-wrap">전체멤버</p>
        </va-card-content>
      </va-card>
    </div>
    <div class="flex x16 xs12 lg3">
      <va-card>
        <va-card-content>
          <h2 class="va-h2 ma-0" :style="{ color: colors.primary }">4</h2>
          <p class="no-wrap">운영진</p>
        </va-card-content>
      </va-card>
    </div>
    <div class="flex x16 xs12 lg3">
      <va-card>
        <va-card-content>
          <h2 class="va-h2 ma-0" :style="{ color: colors.primary }">50,000</h2>
          <p class="no-wrap">남은 회비</p>
        </va-card-content>
      </va-card>
    </div>
    <div class="flex x16 xs12 lg3">
      <va-card>
        <va-card-content>
          <h2 class="va-h2 ma-0" :style="{ color: colors.primary }">291</h2>
          <p class="no-wrap">{{ t('dashboard.info.completedPullRequests') }}</p>
        </va-card-content>
      </va-card>
    </div>
  </div>
</template>

<script setup lang="ts">
  import { ref } from 'vue'
  import { useI18n } from 'vue-i18n'
  import { VaCard, VaCardContent, useColors } from 'vuestic-ui'

  const { t } = useI18n()
  const { colors } = useColors()

  const infoTiles = ref([
    {
      color: 'success',
      value: '803',
      text: 'commits',
      icon: '',
    },
    {
      color: 'danger',
      value: '57',
      text: 'components',
      icon: '',
    },
    {
      color: 'info',
      value: '5',
      text: 'teamMembers',
      icon: '',
    },
    {
      color: 'info',
      value: '5',
      text: 'teamMembers',
      icon: '',
    },
  ])
</script>

<style lang="scss" scoped>
  .row-separated {
    .flex + .flex {
      border-left: 1px solid var(--va-background-primary);
    }
  }

  .rich-theme-card-text {
    line-height: 1.5;
  }

  .gallery-carousel {
    width: 80vw;
    max-width: 100%;

    @media all and (max-width: 576px) {
      width: 100%;
    }
  }
</style>
