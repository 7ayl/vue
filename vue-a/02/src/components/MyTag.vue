<template>
    <div class="my-tag">
        <input
          ref="inp"
          v-if="isEdit" 
          v-focus
          class="input"
          type="text"
          placeholder="输入标签"
          @blur="isEdit=false"
        />
        <div 
          v-else 
          @dblclick="handleClick"
          class="text">
            茶具
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            isEdit:false
        }
        
    },
    methods:{
        handleClick(){
            //双击后，切换到显示状态(Vue是异步dom更新)
            this.isEdit=true

            //等dom更新完了，再获取焦点
            // this.$nextTick(()=>{
            //     //立刻获取焦点
            //     this.$refs.inp.focus()
            // })
            
        }
    }
}
</script>

<style lang="less" scoped>
    .my-tag {
    cursor: pointer;
    .input {
      appearance: none;
      outline: none;
      border: 1px solid #ccc;
      width: 100px;
      height: 40px;
      box-sizing: border-box;
      padding: 10px;
      color: #666;
      &::placeholder {
        color: #666;
      }
    }
  }
</style>