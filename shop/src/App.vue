<template>
  <div>
    <div class="header">
      <button v-on:click="modalOpen">Корзина</button>
    </div>

    <div class="modal" v-if="isModalOpen">
      <div class="basketRow basketHeader">
        <div>Название товара</div>
        <div>Количество</div>
        <div>Цена за шт.</div>
        <div>Итого</div>
      </div>
      <div class="basketRow" v-bind:key="index" v-for="(item, index) of cart">
        <div>{{ item.name }}</div>
        <div><span class="productCount" data-productid="1">1</span> шт.</div>
        <div>{{ item.price }}</div>
        <div>
          $<span class="productTotalRow" data-productid="1">{{
            item.price
          }}</span>
        </div>
      </div>
      <div class="basketTotal">
        Товаров в корзине на сумму: $<span class="basketTotalValue">1983</span>
      </div>
    </div>
    <div class="featured container">
      <h1>GeekShop</h1>
      <main>
        <div class="showcase">
          <div
            class="goods-item"
            v-bind:key="index"
            v-for="(item, index) of list"
          >
            <img
              src="https://via.placeholder.com/2000"
              alt="Товар с длинным названием"
              class="ProductCard__img"
            />
            <strong>{{ item.name }}</strong>
            <p>{{ item.price }}</p>
            <button class="btn">Add to Cart</button>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "John",
      isModalOpen: false,
      cart: [
        { name: "Hat red", price: 657 },
        { name: "Shirt red", price: 382 },
        { name: "Hat black", price: 944 },
      ],
      list: [
        { name: "Hat red", price: 657 },
        { name: "Shirt red", price: 382 },
        { name: "Hat black", price: 944 },
        { name: "Shirt white", price: 176 },
        { name: "Socks black", price: 554 },
        { name: "Socks orange", price: 285 },
        { name: "Socks black", price: 781 },
        { name: "Shoes black", price: 672 },
        { name: "Socks black", price: 301 },
        { name: "Socks orange", price: 710 },
        { name: "Shirt white", price: 100 },
      ],
    };
  },
  methods: {
    modalOpen() {
      return (this.isModalOpen = this.isModalOpen === true ? false : true);
    },
  },
};
</script>
<style lang="scss">
body {
  font-family: Lato, sans-serif;
}

.header {
  background: #222;
  height: 74px;
  padding: 18px 16px;
  box-sizing: border-box;
  display: flex;
  justify-content: flex-end;
  padding-right: calc(41% - 400px);
}

.basketRow {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin-bottom: 10px;
  border-bottom: 1px solid #ebebeb;
  padding-bottom: 10px;
}

.modal {
  width: 500px;
  font-size: 16px;
  position: absolute;
  right: 160px;
  top: 70px;
  background: white;
  padding: 10px;
  border: 1px solid #ebebeb;
  border-radius: 3px;
}

.basketRow {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin-bottom: 10px;
  border-bottom: 1px solid #ebebeb;
  padding-bottom: 10px;
}

.basketTotal {
  font-weight: bold;
  text-align: right;
}

.container {
  margin: 0 auto;
  width: 1140px;
}

.featured h1 {
  margin-top: 50px;
  margin-bottom: 35px;
  text-align: center;
  color: #222;
}

main {
  display: block;
}

.showcase {
  flex-wrap: wrap;
  display: flex;
  justify-content: space-around;
  text-align: center;
  max-width: 1140px;
  margin: 0 auto;
  padding: 0 2%;
}

.goods-item {
  background: #f8e4e3;
  width: 31.5%;
  display: flex;
  justify-content: space-around;
  flex-direction: column;
  align-items: center;
  margin-bottom: 30px;
  padding-bottom: 20px;
  border-radius: 9px;
  box-shadow: 0 5px 8px rgb(0 0 0 / 16%);
}

.btn {
  padding: 10px;
}

img {
  max-width: 100%;
  margin-bottom: 20px;
  margin-top: -4px;
  border-top-left-radius: 9px;
  border-top-right-radius: 9px;
}

p {
  font-size: 19px;
  line-height: 19px;
  color: #f16d7f;
  text-align: center;
  font-weight: bold;
}
</style>
