<template>
  <v-container>
    <h2>Container</h2>

    <v-row class="text-center">
      <v-col class="mb-4">
        <div
          class="box"
          v-for="(question, index) in questions.slice(a, b)"
          :key="index"
          v-show="quiz"
        >
          <div class="box-question">
            <h2 class="display-1 font-weight-bold mb-3 text-left">
              Question {{ b }}/{{ questions.length }}
            </h2>
            <h3 class="font-weight-bold mb-3">
              {{ question.question }}
            </h3>
          </div>
          <div class="box-propositions">
            <v-list-item-group v-model="selectedItem" color="primary">
              <v-list-item
                v-for="(proposition, index) in question.propositions"
                :key="index"
              >
                <v-list-item-content>
                  <v-list-item-title
                    v-text="proposition.props"
                  ></v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "QuizContainer",

  data: () => ({
    items: [
      { text: "Real-Time", icon: "mdi-clock" },
      { text: "Audience", icon: "mdi-account" },
      { text: "Conversions", icon: "mdi-flag" },
    ],
    questions: [
      {
        question: "Inside which HTML element do we put the JavaScript ?",
        propositions: [
          { props: "<script>", correct: true },
          { props: "<js>" },
          { props: "<scripting>" },
          { props: "<javascript>" },
        ],
      },
      {
        question:
          "What is the correct syntax for referring to an external script called 'xxx.js' ?",
        propositions: [
          { props: '<script href="xxx.js">' },
          { props: '<script name="xxx.js">' },
          { props: '<script src="xxx.js">', correct: true },
          { props: '<script id="xxx.js">' },
        ],
      },
      {
        question: "How do you write 'Hello World' in an alert box ?",
        propositions: [
          { props: 'msg("Hello World")' },
          { props: 'alertBox("Hello World")' },
          { props: 'alert("Hello World")', correct: true },
          { props: 'msgBox("Hello World")' },
        ],
      },
      {
        question: "How to write an IF statement in JavaScript ?",
        propositions: [
          { props: "if i = 5 then" },
          { props: "if (i == 5)", correct: true },
          { props: "if i == 5 then" },
          { props: "if i = 5" },
        ],
      },
      {
        question: "How does a FOR loop start ?",
        propositions: [
          { props: "for i = 1 to 5" },
          { props: "for (i <= 5; i++)" },
          { props: "for (i = 0; i <= 5)" },
          { props: "for (i = 0; i <= 5; i++)", correct: true },
        ],
      },
      {
        question: "How can you add a comment in a JavaScript ?",
        propositions: [
          { props: "'This is a comment" },
          { props: "//This is a comment", correct: true },
          { props: "<!--This is a comment-->" },
          { props: "*This is a comment" },
        ],
      },
    ],
    a: 0,
    b: 1,
    next: true,
    score_show: false,
    quiz: true,
    score: 0,
    correct: false,
    progress: 0,
  }),
  methods: {
    selectResponse(e) {
      this.correct = true;
      this.next = false;
      if (e.correct) {
        this.score++;
      }
    },
  },
};
</script>
