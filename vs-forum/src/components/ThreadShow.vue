<template>
  <div>
    <div class="col-large push-top">
      <h1>{{thread.title}}</h1>
      <div class="post-list">
        <div class="post" v-for="postId in thread.posts">
          <div class="user-info">
            <a href="#">{{users[posts[postId].userId].name}}</a>
            <a href="#">
              <img class="avatar-large" :src="users[posts[postId].userId].avatar" alt>
            </a>
            <p class="desktop-only text-small">104 posts</p>
          </div>
          <div class="post-content">
            <p>{{posts[postId].text}}</p>
          </div>
          <div class="post-date text-faded">{{posts[postId].publishedAt}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data'

export default {
  props: {
    id: {
      required: true,
      type: String
    }
  },
  data () {
    return {
      thread: sourceData.threads[this.id],
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>

<style>
</style>
