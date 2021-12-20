<template>
  <div>
    <div class="border-2 border-red-300 flex">
      <div
        v-for="program in programs"
        :key="program.slug"
        class="border-blue border-2 rounded"
      >{{ program }}</div>
    </div>
    <div class="flex flex-wrap">
      <nuxt-link
        v-for="lesson in lessons"
        :key="lesson.slug"
        class="border-black border-2 rounded py-3 px-4 m-4 font-semibold transition-colors ease-in-out duration-300 bg-blue-200 text-blue-900 hover:bg-black hover:text-blue-100"
        :to="`/training/${lesson.slug}`"
      >
        {{ lesson.title }}
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LessonList',
  data() {
    return {
      lessons: [],
      programs: ['Diving', 'Fishing', 'Volunteer']
    }
  },
  async mounted() {
    this.lessons = await this.$content('lessons')
      .only(['path', 'title', 'slug', 'programs'])
      .fetch()
    // .catch((e) => {
    //   console.log(e)
    //   // error({ statusCode: 404, message: 'Lessons not found!' })
    // })
  },
}
</script>
