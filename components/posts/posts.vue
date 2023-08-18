<template>
  <ul v-if="posts.length > 0" class="grid grid-cols-1 gap-x-8 gap-y-10 lg:grid-cols-3 sm:grid-cols-2">
    <li class="lgcol-span-2" v-for="(post, index) in posts" :key="index">
      <nuxt-link :to="`/${postType}/${post.slug}`">
        <div class="flex items-end justify-center">
          <div class="flex overflow-hidden">
            <img alt="#" v-if="post.cover" class="cover-image" :src="post.cover" />
          </div>
        </div>
        <p class="mt-8">
          <time class="text-xs text-gray-500" datetime="2023-03-16">
            {{ formatDate(post.createdAt) }}
          </time>
        </p>
        <h3 class="mt-5 text-lg font-medium leading-6 text-black">
          {{ post.title }}
        </h3>
        <p class="mt-2 text-base text-gray-500 line-clamp-2">
          {{ post.description }}
        </p>
      </nuxt-link>
    </li>
  </ul>
  <div v-else-if="loading" class="cards">
    <div v-for="placeholder in placeholderClasses" :key="placeholder.id" class="card">
      <content-placeholders :rounded="true" :class="placeholder">
        <content-placeholders-heading />
      </content-placeholders>
    </div>
  </div>
  <p v-else class="max-w-5xl mx-auto">
    {{ amount > 1 ? 'Posts not found' : 'Post not found' }}
  </p>
</template>
<script>
export default {
  name: 'PostsTwo',
  props: {
    postType: {
      type: String,
      default: 'blog',
      validator: (val) => ['blog', 'projects'].includes(val),
    },
    amount: {
      // ? https://content.nuxtjs.org/fetching#limitn
      type: Number,
      default: 10,
      validator: (val) => val >= 0 && val < 100,
    },
    sortBy: {
      // ? https://content.nuxtjs.org/fetching#sortbykey-direction
      type: Object,
      default: () => ({
        key: 'slug',
        direction: 'desc', // you probably want 'asc' here
      }),
      validator: (obj) => typeof obj.key === 'string' && typeof obj.direction === 'string',
    },
  },
  data() {
    return {
      posts: [],
      loading: true,
    }
  },
  computed: {
    placeholderClasses() {
      const classes = ['w-full', 'w-2/3', 'w-5/6']
      return [...Array.from({ length: this.amount }, (v, i) => classes[i % classes.length])] // repeats classes after one another
    },
  },
  async mounted() {
    this.loading = true
    this.posts = await this.fetchPosts()
    this.loading = false
  },
  methods: {
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toLocaleDateString(process.env.lang) || ''
    },
    async fetchPosts(postType = this.postType, amount = this.amount, sortBy = this.sortBy) {
      return this.$content(postType)
        .sortBy(sortBy.key, sortBy.direction)
        .limit(amount)
        .fetch()
        .catch((err) => console.error(err) || [])
    },
  },
}
</script>
