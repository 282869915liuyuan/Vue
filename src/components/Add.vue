
<template>
    <div>
      <form>
        <div class="form-group">
          <label for="bookName" class="control-label"></label>
          <input type="text" id="bookName" class="form-control"
                 placeholder="请输入" v-model="book.bookName">
        </div>
        <div class="form-group">
          <label for="bookCover" class="control-label"></label>
          <input type="text" id="bookCover" class="form-control"
                 placeholder="请输入" v-model="book.bookCover">
        </div>
        <div class="form-group">
          <label for="bookPrice" class="control-label"></label>
          <input type="text" id="bookPrice" class="form-control"
                 placeholder="请输入" v-model="book.bookPrice">
        </div>
      <div class="form-group">
        <button type="button" class="btn btn-danger" @click="add">添加</button>
      </div>
      </form>
    </div>
</template>
<script>
    export default {
        data(){
            return {
             book:{
                 bookName:'',
                 bookCover:'',
                 bookPrice:''
             }

            }
        },
        components: {},
        methods: {
            add(){
                this.$http.post('/book',this.book).then(()=>{
                    this.$router.push('/list')
              })
            }
        }
    }
</script>
<style scoped>

</style>
