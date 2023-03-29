<template>
  <div class="container mx-auto py-8">
    <form>
      <h2 class="text-gray-400">What are you looking to do?</h2>
      <RadioAccordion
        :modelValue="modelValue"
        :name="name"
        :options="options"
        @update:modelValue="updateModelValue"
      >
    </RadioAccordion>

    </form>
  </div>
</template>

<script lang="ts">
import type Option from 'types/Option';
import { defineComponent, ref } from 'vue';
import RadioAccordion from './components/RadioAccordion.vue';

export default defineComponent({
  name: 'App',
  components: {
    RadioAccordion,
  },
  setup() {
    const modelValue = ref<number>(0);
    const name = 'options';

    const options: Option[] = [
      {
        id: 'option1',
        title: 'Option 1',
        subtitle: 'Subtitle of option 1',
        value: 1,
        details: [{text: 'test link', target: 'https://example.com'}]
      },
      {
        id: 'option2',
        title: 'Option 2',
        subtitle: 'Subtitle of option 2',
        value: 2,
      },
      {
        id: 'option3',
        title: 'Option 3',
        subtitle: 'Subtitle of option 3',
        value: 3,
      },
    ];

    const updateModelValue = (value: Number) => {
      modelValue.value = value;
    };

    return {
      modelValue,
      name,
      options,
      updateModelValue,
    };
  },
});
</script>

<style lang="postcss">
/* Import Tailwind CSS */
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
</style>

