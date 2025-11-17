<template>
  <h3 class="mt-4 mb-3">{{t('setup.automationMode.title')}}</h3>

  <div class="form-check form-switch">
    <input class="form-check-input" type="checkbox" id="fullAutomation"
        :checked="state.setup.fullAutomationMode" @input="toggleFullAutomation">
    <label class="form-check-label" for="fullAutomation">
      {{t('setup.automationMode.fullAutomationLabel')}}
    </label>
  </div>
  <div class="form-text">{{t('setup.automationMode.fullAutomationHelp')}}</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { useI18n } from 'vue-i18n'
import { useStateStore } from '@/store/state'

export default defineComponent({
  name: 'AutomationMode',
  setup() {
    const { t } = useI18n()
    const state = useStateStore()

    return { t, state }
  },
  methods: {
    toggleFullAutomation() : void {
      this.state.setup.fullAutomationMode = !this.state.setup.fullAutomationMode
    }
  }
})
</script>
