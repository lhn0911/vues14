<template>
  <div class="product-detail">
    <div class="product-main">
      <div class="product-image-carousel">
        <!-- Carousel cho hình ảnh sản phẩm -->
        <img
          class="main-image"
          src="https://cdn.mobilecity.vn/mobilecity-vn/images/2024/03/hinh-nen-hoa.jpg.webp"
          alt="Main Product Image"
        />
        <div class="thumbnail-carousel">
          <!-- Các hình ảnh nhỏ bên dưới -->
          <img
            src="https://i.pinimg.com/236x/f7/be/c8/f7bec8acbe58578f6f7f65423c777a13.jpg"
            alt="Thumbnail 1"
          />
          <img
            src="https://i.pinimg.com/236x/f7/be/c8/f7bec8acbe58578f6f7f65423c777a13.jpg"
            alt="Thumbnail 2"
          />
          <img
            src="https://i.pinimg.com/236x/f7/be/c8/f7bec8acbe58578f6f7f65423c777a13.jpg"
            alt="Thumbnail 3"
          />
        </div>
      </div>
      <div class="product-info">
        <span class="tag tag-green">In Stock</span>
        <span class="tag tag-purple">Kids</span>
        <h1>Cute Soft Teddybear</h1>
        <p class="description">
          Vuhohgi tuilofi ruzhifru zewopaz pi kamin wibrucvil vebbeji pomidwi
          glk zigu of les arsoze.
        </p>
        <div class="price-section">
          <span class="original-price">$175</span>
          <span class="current-price">$200</span>
        </div>
        <div class="reviews">
          <span class="rating-stars">★★★★★</span> (236 reviews)
        </div>
        <div class="color-picker">
          <label>Colors*</label>
          <button class="color-btn" style="background-color: #ff6347"></button>
          <button class="color-btn" style="background-color: #ffd700"></button>
          <button class="color-btn" style="background-color: #adff2f"></button>
        </div>
        <div class="quantity">
          <label>Quantity</label>
          <button @click="decreaseQuantity" class="qty-btn">-</button>
          <input type="number" v-model="quantity" class="quantity-input" />
          <button @click="increaseQuantity" class="qty-btn">+</button>
        </div>
        <div class="action-buttons">
          <button class="btn btn-primary">Buy Now</button>
          <button class="btn btn-secondary">Add To Cart</button>
        </div>
        <p class="dispatch-info">
          Dispatched in 2-3 weeks<br />
          <a href="#" class="delivery-link"
            >Why the longer time for delivery?</a
          >
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quantity: 1,
    };
  },
  methods: {
    increaseQuantity() {
      this.quantity++;
    },
    decreaseQuantity() {
      if (this.quantity > 1) {
        this.quantity--;
      }
    },
  },
};
</script>

<style scoped>
.product-detail {
  display: flex;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}
.product-main {
  display: flex;
  gap: 20px;
}
.product-image-carousel {
  flex: 1;
}
.main-image {
  width: 100%;
  border-radius: 10px;
}
.thumbnail-carousel {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}
.thumbnail-carousel img {
  width: 60px;
  height: 60px;
  border-radius: 5px;
  cursor: pointer;
}
.product-info {
  flex: 1;
  padding-left: 20px;
}
.tag {
  padding: 5px 10px;
  border-radius: 5px;
  color: white;
  margin-right: 10px;
}
.tag-green {
  background-color: #28a745;
}
.tag-purple {
  background-color: #6f42c1;
}
h1 {
  margin: 20px 0;
  font-size: 28px;
}
.description {
  color: #6c757d;
  margin-bottom: 10px;
}
.price-section {
  display: flex;
  gap: 15px;
  align-items: center;
  margin-bottom: 10px;
}
.original-price {
  font-size: 18px;
  text-decoration: line-through;
  color: #999;
}
.current-price {
  font-size: 24px;
  font-weight: bold;
  color: #007bff;
}
.rating-stars {
  color: #f39c12;
}
.color-picker {
  margin-bottom: 20px;
}
.color-picker label {
  display: block;
  margin-bottom: 5px;
}
.color-btn {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: none;
  cursor: pointer;
  margin-right: 5px;
}
.quantity {
  margin-bottom: 20px;
}
.qty-btn {
  padding: 5px 10px;
  background-color: #ddd;
  border: none;
  cursor: pointer;
  border-radius: 5px;
}
.quantity-input {
  width: 50px;
  text-align: center;
}
.action-buttons {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}
.btn {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  border-radius: 5px;
  border: none;
}
.btn-primary {
  background-color: #007bff;
  color: white;
}
.btn-secondary {
  background-color: #6c757d;
  color: white;
}
.dispatch-info {
  font-size: 14px;
  margin-top: 10px;
}
.delivery-link {
  color: #007bff;
  text-decoration: none;
}
</style>
