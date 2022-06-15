<!-- Please remove this file from your project -->
<template>
  <div>
    test
    <button @click="test">click</button>

  </div>
</template>

<script>
export default {
  name: 'NuxtTutorial',
  async fetch() {
    // await this.test()
  },
  async mounted() {
    await this.test()
  },
  methods: {
    async test() {
      const response = await this.$axios.$get(
        `/api/2/tweets/search/recent?query=${encodeURI(
          '台灣'
        )}&expansions=author_id`,
        {
          headers: {
            Authorization:
              'Bearer AAAAAAAAAAAAAAAAAAAAAELqdgEAAAAAdJtW9oDy2MsEHQ63AssyuUY6Le4%3DUnmGL9Fo2dYQwInNckFCYLmcZNN2mvDcpABu7RubsywszwVIB6',
          },
        }
      )
      console.log(response);

    }
  }
}
</script>
