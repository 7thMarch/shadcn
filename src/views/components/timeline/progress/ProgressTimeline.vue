<template>
  <div
      class="space-y-8 relative before:absolute before:inset-0 before:ml-5 before:-translate-x-px md:before:mx-auto md:before:translate-x-0 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-transparent before:via-slate-300 before:to-transparent">
    <div v-for="item in items" class="relative flex items-center justify-between md:justify-normal md:odd:flex-row-reverse group is-active">
      <slot v-if="$slots.item" name="item" :item="item"/>
      <template v-else>
        <div
            class="flex items-center justify-center w-10 h-10 rounded-full border border-white bg-slate-300 group-[.is-active]:bg-emerald-500 text-slate-500 group-[.is-active]:text-emerald-50 shadow shrink-0 md:order-1 md:group-odd:-translate-x-1/2 md:group-even:translate-x-1/2">
          <svg class="fill-current" xmlns="http://www.w3.org/2000/svg" width="12" height="10">
            <path fill-rule="nonzero" d="M10.422 1.257 4.655 7.025 2.553 4.923A.916.916 0 0 0 1.257 6.22l2.75 2.75a.916.916 0 0 0 1.296 0l6.415-6.416a.916.916 0 0 0-1.296-1.296Z"/>
          </svg>
        </div>
        <div class="w-[calc(100%-4rem)] md:w-[calc(50%-2.5rem)] bg-white p-4 rounded border border-slate-200 shadow">
          <div class="flex items-center justify-between space-x-2 mb-1">
            <div class="font-bold text-slate-900">{{ item.title }}</div>
            <time class="font-caveat font-medium text-indigo-500">{{ item.time }}</time>
          </div>
          <div class="text-slate-500">{{ item.description }}</div>
        </div>
      </template>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Timeline } from '@/views/components/timeline/Timeline.ts'

export default defineComponent({
  name: 'ProgressTimeline',
  props: {
    items: {
      type: Array<Timeline>,
      required: true
    }
  }
})
</script>
