<template>
  <div class="resumify user-image">
    <img :src="src" />
    <input type="file" @change="onFileSelected" accept="image/gif,image/jpeg,image/jpg,image/png" class="user-image-filepicker"/>
  </div>
</template>

<script>
  export default {
    data: () => ({
      src: "data:image/png;base64,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jVwe2RD5IcorakvU42jjaEl0Z4xszJKY+piPsT6x5bH9cQviVsddj1eL58W3JeASYhIOJUws9l28c/HQEvslxUvuLTVamrf06jK1ZRnLzi6XXc5afiIRkxib2JD4lRXGqmVNJDGTapLG2d7sXexXHE/ODs5osltyefJwiltKecoI1427nTua6pFakTrG8+ZV8d6kBaTtS/uYHpZelz6VEZvRnInPTMw8zVfgp/O7srSy8rL6BGaCYkF/tkv2zuxxYZDwkAgSLRW1iRURw3NDYiz5QTKQ455TnfMpNyb3RJ58Hj/vxgrTFZtWDOf75f+8Er2SvbJzlc6qdasGVjNW718DrUla07lWb23R2qEC/4LD64jr0tf9VmhVWF74fn3s+vYizaKCosEf/H9oLJYpFhbf3+C6Yd9G9Ebexp5Ntpt2b/pewim5VmpVWlH6tYxddu1H6x8rf5zanLK5Z4vDlr1bsVv5W+9t89h2uFy+PL98cHvI9pYd9B0lO97vXL7zaoVdxb5dxF2SXf2VwZVtu/V3b939tSq16m61V3VzjUbNppqPezh7bu313Nu0T3Nf6b4vP/F+erDff39LrWFtxQHsgZwDLw7GHOz+2enn+kNqh0oPfavj1/UfjjjcVe9YX9+g0bClEW6UNI4eWXKk96jP0bYmi6b9zbTm0mPgmOTYy18Sf7l3POh45wmnE00nDU7WnKKeKmmBWla0jLemtva3xbf1nQ483dnu2n7qV8tf687onKk+q3R2yzniuaJzU+fzz090CDrGLnAvDHYu73x8Me7ina5FXT2Xgi5duex3+WI3o/v8FbcrZ666XD19zela63WH6y037G+c+s3+t1M9Dj0tNx1vtvU697b3Lew7d8vj1oXbPrcv32HeuX439G7fveh7D+4vud//gPNg5GHGwzePch5NPi54gnlS8lTuacUzjWe1v5v83tzv0H92wGfgxvPI548H2YOv/hD98XWo6AXlRcWw9nD9iM3ImVG/0d6Xi18OvRK8mhwr/lP+z5rXxq9P/uX5143xuPGhN8I3U2/L3qm+q3tv975zInzi2YfMD5MfSz6pfjr82elz95fYL8OTuV9xXyu/mXxr/x70/clU5tSUgCVkzVgBFDLglBQA3tYBQIlHvEMvAESZWZ88E9Cst58h8Hc866VnwgGAOk8AogsACEY8yl5kGCBMRuZp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"
    }),
    methods: {
      onFileSelected: function(evt){
        let file = evt.target.files[0];
        new Promise((resolve) => {
          let reader = new FileReader();
          reader.onloadend = () => {
            this.src = reader.result
          }
          reader.readAsDataURL(file)
        })
      }
    }
  }
</script>

<style lang="scss">
  .resumify.user-image {
    position: relative;

    img {
      display: block;
      height: 200px;
      width:  200px;
      border-radius: 100px;
      border: 1px solid #ddd;
      margin: 15px auto;
    }

    .user-image-filepicker {
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      opacity: 0;
      cursor: pointer;
    }
  }
</style>
