<template>
  <div class="home">
    <v-container>
      <v-row class="text-center">
        <v-col class="mb-4">
          <h1 class="display-2 font-weight-bold mb-3">Welcome to Quiz</h1>
        </v-col>
      </v-row>
      <QuizComponent />
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
import QuizComponent from "@/components/QuizComponent.vue";

export default {
  name: "Quiz",
  components: {
    QuizComponent,
  },
};
</script>
