<template>
  <div class="course">
    <div class="container">
      <div class="title">
        <h1><strong>Course เรียนทั้งหมด<br>ทั้ง Front-End และ Frameworks ต่าง ๆ</strong></h1>
      </div>
      <div class="columns is-multiline">
        <div class="column is-4" v-for = "list in listplay">
          <div class="box">
            <nuxt-link :to="{ name: 'course-lesson', params: { lesson:list.name }}">
              <div style="vertical-align: middle">
                <img class="menu" :src="list.img" width="100px">
                <h4> {{list.name}}  <span class="tag is-Light">{{list.list.length}}</span></h4>
                <p style="color:#999">โดย {{list.teacher}}</p>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import { mapGetters, mapActions } from 'vuex'
  export default {
    name: 'listplay',
    data: function data () {
      return {
      }
    },
    computed: {
      ...mapGetters([
        'listplay'
      ])
    },
    mounted () {
      this.setListplayRef(this.$db.ref('listplay'))
    },
    methods: {
      ...mapActions([
        'setListplayRef'
      ])
    }
  }
</script>

<style scoped>

  .title{
    margin-bottom: 50px;
  }

  a.title{
    color : #47b8f0;
    font-size: 20px;
    font-weight: bold;
    -o-transition:.5s;
    -ms-transition:.5s;
    -moz-transition:.5s;
    -webkit-transition:.5s;
    text-decoration: none;
  }

  a.title:hover{
    color :#0993d8;
    text-decoration: none;
  }

  a{
    color: #555;
    -o-transition:.5s;
    -ms-transition:.5s;
    -moz-transition:.5s;
    -webkit-transition:.5s;
  }

  a:hover{
    color: #222;
    text-decoration: none;
  }

  .course{
    padding: 100px 0 50px 0;
    border-bottom: 1px solid #eee;

  }
</style>
