<template>
  <div class="container mx-auto max-w-4xl px-4">
    <BaseUIPageHeading>Choose a Lesson</BaseUIPageHeading>
    <p>
      The lessons below have been hand crafted by experts to give you the
      need-to-know information about particular topics.
    </p>
    <LessonList></LessonList>
  </div>
</template>

<script>
export default {
  name: 'TrainingIndex',
  head() {
    return [
      {
        title: 'Training',
      },
    ]
  },
}
</script>
