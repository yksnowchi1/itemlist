<template>
  <div id="Post">
    <h1>{{title}}</h1>
    <div>
      <div v-for="post in posts" class="text item">
        <a href="#">{{post.title}}</a>
      </div>
      <div v-for="item in items">{{item.title}}</div>
    </div>
    <div>
     
    </div>
    
  </div>
</template>
<style>

</style>

<script>
/* eslint-disable no-new */
export default {
  name: 'Post',
  data () {
    return {
      title: 'Lorem ipsum dolor sit amet',
      posts: [ 
        { title: 'Foo' },
        { title: 'Bar' }
      ],
      items: [ 
        { title: 'Foo1' },
        { title: 'Bar2' }
      ],
    }
  },
  mounted: function() {
    this.$http.get('http://x5.dev/api/blog', {}, {
        headers: {

        },
        emulateJSON: true
    }).then(function(response) {
        this.posts = response.data
    
    }, function(response) {
        console.log(response)
    });
  }
}




</script>
