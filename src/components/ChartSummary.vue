<template>
  <div class="chart-summary">
    <div class="chart-summary__column chart-summary__column--left">
      <h3 class="chart-summary__column-title">Total this month</h3>
      <p class="chart-summary__this-month-price">${{ thisMonthPrice }}</p>
    </div>
    <div class="chart-summary__column chart-summary__column--right">
      <p class="chart-summary__last-month-perc">+{{ lastMonthPrice }}%</p>
      <h3 class="chart-summary__column-title">from last month</h3>
    </div>
  </div>
</template>
  
  <script setup>
import { ref } from "vue";

const thisMonthPrice = ref(478.33);
const lastMonthPrice = ref(2.4); // In %
</script>
  
  <style lang="scss" scoped>
@import '../style.scss';
.chart-summary {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;

  font-family: $dm-sans;

  &__column {
    color: $dark-brown;

    &--left {
      text-align: left;
    }

    &--right {
      margin-bottom: 5px;

      text-align: right;

      @media screen and (min-width: $lg) {
        margin-bottom: 10px;
      }
    }
  }

  &__column-title {
    color: $medium-brown;
    font-size: 0.938rem;
    font-weight: 400;

    @media screen and (min-width: $lg) {
      font-size: 1.125rem;
    }
  }

  &__this-month-price {
    margin-top: 4px;

    font-weight: 700;
    font-size: 1.875rem;

    @media screen and (min-width: $lg) {
      margin-top: 1px;

      font-size: 3rem;
    }
  }

  &__last-month-perc {
    font-weight: 700;
    font-size: 0.938rem;

    @media screen and (min-width: $lg) {
      margin-bottom: 1px;

      font-size: 1.125rem;
    }
  }
}
</style>