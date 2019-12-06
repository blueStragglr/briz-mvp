<template>
  <div class="comments">
    <label for="comment">Input comment</label>

    <div class="comment-input">
      <div class="comment-textarea">
        <textarea id ="comment" placeholder="input comment here"></textarea>
      </div>
      <button class="comment-submit" type="button" @click="alertAs('not implemented')">
        submit
      </button>
    </div>
  </div>
</template>

<script>
  export default {
    name: "comments",
    methods: {
      alertAs(message){
        alert(message)
      }
    }
  }
</script>

<style scoped>
  .comments{
    margin-top: 24px;
  }

  .comments>label{
    font-size: 16px;
    font-weight: 500;
  }
  .comment-input{
    display: flex;
    margin-top: 10px;

  }
  .comment-textarea{
    flex: 1;
    padding-right: 16px;
  }
  .comment-textarea > textarea{
    width: 100%;
    resize: none;
    border: 1px solid #bbbbbb;
    border-radius: 6px;
    height: 48px;
    padding: 8px;
  }
  .comment-submit{
    flex: none;
    width: 90px;
    font-size: 14px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    font-weight: 500;
    height: 48px;
    color: #ffffff;
    background-color: #b45162;

    outline: none;
  }

</style>