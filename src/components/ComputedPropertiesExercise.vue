<template>
  <div class="computed-properties-exercise container">
    <div class="row">
      <div class="col-12">
        <div class="border p-1">
          <div class="reverse-message">
            <p>Original Message: {{ state.message }}</p>
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
      message: "Hello World!",
      reversedMessage: computed(() => {
        state.message.split("").reverse().join('')
        // all computed properties must return a value, what do you want this one to return?
        return "!dlroW olleH";
      }),
    });
    return {
      state,
    };
  },
};
</script>


<style scoped></style>
