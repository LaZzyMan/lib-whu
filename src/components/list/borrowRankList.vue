<template>
<div class='borrow-rank-list'>
  <borrow-rank-card
  v-for='(item, index) in result'
  :key=item.index
  :name=item.title
  :author=item.author
  :rate=item.rate
  :rank=item.index+1
  :borrow-times=item.bor_num
  @click-card=onClickCard
  />
</div>
</template>

<script>
import borrowRankCard from '../card/borrowRankCard';

export default {
  name: 'BorrowRankList',
  components: {
    borrowRankCard,
  },
  props: {
    result: {
      type: Array,
      required: true,
      default: () => [],
    },
  },
  methods: {
    onClickCard(key) {
      this.$emit('click-card', key);
    },
  },

};
</script>

<style lang="scss" scoped>
.borrow-rank-list{
  margin: 3vw;
  height: 100%;
}

</style>
