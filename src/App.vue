<template>
  <div>
    <!-- Shopping Cart Form -->
    <div class="bg-white p-6 rounded-lg shadow-md max-w-2xl mx-auto mb-6">
      <div class="flex justify-between mb-6">
        <div
          class="flex items-center bg-blue-50 text-blue-500 px-4 py-2 rounded-md"
        >
          <ShoppingCart class="mr-2" />
          <div>
            <div class="font-semibold">Item Cart</div>
            <div class="text-sm">Product Summary</div>
          </div>
        </div>
        <div class="flex space-x-4">
          <div class="flex items-center">
            <FileText class="mr-2" />
            <div>
              <div class="font-semibold">Billing</div>
              <div class="text-sm">Billing Information</div>
            </div>
          </div>
          <div class="flex items-center">
            <CreditCard class="mr-2" />
            <div>
              <div class="font-semibold">Payment</div>
              <div class="text-sm">Add & Update Card</div>
            </div>
          </div>
        </div>
      </div>

      <table class="w-full mb-6">
        <thead>
          <tr class="text-left">
            <th>Product</th>
            <th>Price</th>
            <th>Quantity</th>
            <th>Total</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="py-4">
              <div class="flex items-center">
                <img
                  src="https://cdn.mobilecity.vn/mobilecity-vn/images/2024/03/hinh-nen-hoa-tinh-mau-tu-toa-sen.jpg.webp"
                  alt="Teddy Bear"
                  class="w-20 h-20 object-cover rounded mr-4"
                />
                <div>
                  <div class="font-semibold">Cute Soft Teddybear</div>
                  <div class="text-sm text-gray-500">
                    size: 8 | Color: Dark Red
                  </div>
                </div>
              </div>
            </td>
            <td>
              <div class="font-semibold">$200</div>
              <div class="text-sm text-gray-500 line-through">$175</div>
            </td>
            <td>
              <div class="flex items-center">
                <button @click="decreaseQuantity" class="p-1 border rounded">
                  <Minus size="16" />
                </button>
                <span class="mx-2">{{ quantity }}</span>
                <button @click="increaseQuantity" class="p-1 border rounded">
                  <Plus size="16" />
                </button>
              </div>
            </td>
            <td>
              <div class="flex items-center justify-between">
                <span class="font-semibold">$200</span>
                <button class="text-red-500"><Trash2 size="16" /></button>
              </div>
            </td>
          </tr>
        </tbody>
      </table>

      <div class="border-t pt-4">
        <h3 class="font-semibold mb-4">Order Summary</h3>
        <div class="space-y-2">
          <div class="flex justify-between">
            <span>Sub Total</span>
            <span class="font-semibold">$200</span>
          </div>
          <div class="flex justify-between text-red-500">
            <span>Discount 5%</span>
            <span>- $10</span>
          </div>
          <div class="flex justify-between">
            <span>Shipping Charges</span>
            <span>-</span>
          </div>
          <div class="flex justify-between font-semibold">
            <span>Total</span>
            <span>$190</span>
          </div>
        </div>
      </div>

      <div class="mt-6 flex justify-between">
        <button class="px-4 py-2 border border-red-300 text-red-500 rounded">
          Continue Shopping
        </button>
        <button class="px-4 py-2 bg-red-500 text-white rounded">
          CheckOut
        </button>
      </div>
    </div>

    <!-- Product Details Form -->
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
            <button
              class="color-btn"
              style="background-color: #ff6347"
            ></button>
            <button
              class="color-btn"
              style="background-color: #ffd700"
            ></button>
            <button
              class="color-btn"
              style="background-color: #adff2f"
            ></button>
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
  </div>
</template>

<script>
import {
  ShoppingCart,
  FileText,
  CreditCard,
  Minus,
  Plus,
  Trash2,
} from "lucide-vue-next";

export default {
  components: {
    ShoppingCart,
    FileText,
    CreditCard,
    Minus,
    Plus,
    Trash2,
  },
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
.product-main {
  display: flex;
  justify-content: space-between;
  gap: 20px;
}

.product-image-carousel {
  flex: 1;
}

.main-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
  margin-bottom: 20px;
}

.thumbnail-carousel img {
  width: 80px;
  height: 80px;
  border-radius: 4px;
  cursor: pointer;
  margin-right: 10px;
}

.product-info {
  flex: 1;
  padding-left: 20px;
}

.price-section {
  display: flex;
  align-items: center;
  gap: 10px;
  margin: 15px 0;
}

.original-price {
  text-decoration: line-through;
  color: gray;
}

.current-price {
  font-size: 1.5em;
  color: #ff6347;
}

.btn-primary {
  background-color: #ff6347;
  color: white;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
}

.btn-secondary {
  background-color: #555;
  color: white;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
}

.quantity-input {
  width: 50px;
  text-align: center;
}

.action-buttons {
  margin-top: 20px;
  display: flex;
  gap: 10px;
}
.flex.justify-between {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.flex.items-center {
  display: flex;
  align-items: center;
}

.max-w-2xl {
  max-width: 768px;
}

.bg-white {
  background-color: white;
}

.rounded-lg {
  border-radius: 12px;
}

.shadow-md {
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.text-sm {
  font-size: 0.875rem;
}

.text-gray-500 {
  color: #6b7280;
}

table {
  width: 100%;
  border-collapse: collapse;
}

th,
td {
  padding: 12px;
  text-align: left;
}

td img {
  max-width: 80px;
  max-height: 80px;
}

.border {
  border: 1px solid #ddd;
}

.p-1 {
  padding: 4px;
}
</style>
