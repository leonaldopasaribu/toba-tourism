<template>
  <div class="card-item-culinary">
    <card-item
      :image="culinary.culinaryImage[0]"
      :title="culinary.culinaryName"
      :caption1="currency(culinary.culinaryPrice)"
      :caption2="restaurant.restaurantName"
      :caption3="restaurant.restaurantLocation"
      :isAdminMode="isAdminMode"
      @onClickImage="onClickImage"
    >
      <span slot="caption2">
        <i class="fa fa-home"></i>
      </span>
      <span slot="caption3">
        <i class="fa fa-map-marker"></i>
      </span>
    </card-item>
  </div>
</template>

<script>
import CardItem from '@/components/CardItem'
export default {
  name: 'CardItemCulinary',
  props: {
    restaurant: {
      type: Object
    },
    culinary: {
      type: Object
    },
    isAdminMode: {
      type: Boolean,
      default: true
    }
  },
  components: {
    CardItem
  },
  data () {
    return {
    }
  },
  methods: {
    onClickImage () {
      this.$emit('onClickImage', this.culinary.culinaryImage[0])
    },
    onClickCamera () {
      this.$emit('onClickCamera', this.culinary)
    }
  }
}
</script>

<style scoped>
  .caption_icon {
    width: 25px;
    height: 20px;
    margin: 1px;
  }
</style>
