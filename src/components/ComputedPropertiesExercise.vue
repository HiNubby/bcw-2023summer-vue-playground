<template>
  <div class="computed-properties-exercise container">
    <div class="row">
      <div class="col-12">
        <div class="border p-1">
          <div class="reverse-message">
            <p>Original Message: {{state.message}}</p>
            <p>Computed Reversed Message: {{ state.reversedMessage }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { computed, reactive } from "vue";
export default {
  name: "computed-properties-exercise",
  setup() {
    // NOTE typically state will be abstracted to a global AppState
    const state = reactive({
      // After getting this to work, challenge yourself to add an input field and bind message to it, so as you type the messag gets reversed!
      message: "Quick brown fox",
      reversedMessage: computed(() => {
        let reversedWord = state.message.split("").reverse().join("")
        return reversedWord;
      }),
    });
    return {
      state,
    };
  },
};
</script>


<style scoped>
</style>
