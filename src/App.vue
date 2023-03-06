<template>
  <h2>My Course Goal</h2>
  <!-- Task 1: Output your main course goal with help of the composition API -->
  <!-- Don't hardcode it into the template, instead hardcode it into the JS code -->
  <h3 v-if="goalVisibility.goalVisibility">{{ goal }}</h3>
  <!-- Task 2: Toggle (show/ hide) the goal with help of the button  -->
  <button @click="toggleGoal">Toggle Goal</button>
  <!-- Task 3: Manage data in three ways -->
  <!-- => Separate refs -->
  <!-- => Ref Object -->
  <!-- => Reactive Object -->
  <!-- Task 4: Also solve the assignment with the Options API -->
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const goal = ref({
      myGoal: 'I want to study vue and find job to develop myself',
      goalVisibility: true,
    });

    function toggleGoalVisibility() {
      console.log(goal.value.goalVisibility);

      goal.value.goalVisibility = !goal.value.goalVisibility;
    }

    return {
      goal: goal.value.myGoal,
      toggleGoal: toggleGoalVisibility,
      goalVisibility: goal,
    };
  },
};

// task 3 (separate refs)

// import { ref } from 'vue';
// export default {
//   setup() {
//     const goal = ref('I want to study vue and find job to develop myself');
//     const goalVisibility = ref(true);

//     function toggleGoalVisibility() {
//       goalVisibility.value = !goalVisibility.value;
//     }

//     return {
//       goal: goal,
//       goalVisibility: goalVisibility,
//       toggleGoal: toggleGoalVisibility,
//     };
//   },
// };

// task 3 (reactive)

// import { reactive } from 'vue';
// export default {
//   setup() {
//     const goal = reactive({
//       myGoal: 'I want to study vue and find job to develop myself',
//       goalVisibility: true,
//     });

//     function toggleGoalVisibility() {
//       goal.goalVisibility = !goal.goalVisibility;
//     }

//     return { goal: goal, toggleGoal: toggleGoalVisibility };
//   },
// };
</script>

<style>
html {
  font-family: sans-serif;
}
body {
  margin: 3rem;
  text-align: center;
}
</style>
