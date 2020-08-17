<template>
    <div class="is-primary">
        <a href="*" class="button" style="width:64px;" ref="name">{{ item.name }}</a><br />
        <a href="*" class="wb-phone">{{ item.interPhone }}</a><label style="margin-left:4px;" ref="status" class="wb-status"></label>
    </div>
</template>

<script>
export default {
  name: 'Desk',
  props: ['item'],
  mounted: function () {
    //this.$refs.name.className = 'button is-primary'
    switch (this.item.status){
      case "1":
        this.$refs.name.classList.add('is-primary');
        this.$refs.status.innerHTML = "在";
        break;
      case "2":
        this.$refs.name.classList.add('is-black');
        this.$refs.status.innerHTML = "退";
        break;
      case "3":
        this.$refs.name.classList.add('is-success');
        this.$refs.status.innerHTML = "会";
        break;
      case "4":
        this.$refs.name.classList.add('is-info');
        this.$refs.status.innerHTML = "内";
        break;
      case "5":
        this.$refs.name.classList.add('is-waring');
        this.$refs.status.innerHTML = "外";
        break;
      case "6":
        this.$refs.name.classList.add('is-danger');
        this.$refs.status.innerHTML = "休";
        break;
      case "7":
        this.$refs.name.classList.add('is-waring');
        this.$refs.status.innerHTML = "出";
        break;
      case "8":
        this.$refs.name.classList.add('is-white');
        this.$refs.status.innerHTML = "他";
        break;
      case "0":
        this.$refs.namei.classList.add('is-warning');
        this.$refs.status.innerHTML = "宅";
        break;
    }
  }
}
</script>