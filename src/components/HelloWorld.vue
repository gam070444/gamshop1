<template>
  <div>
    <br /><br />
    <div>
      <b-card>
        <b-img :src="img" style="width: 200px; height: 15rem"></b-img>
        <h5>{{ name }}</h5>
        <b-card-text> {{ price }} บาท </b-card-text>

        <div>
          <b-form-spinbutton
            id="sb-inline"
            v-model="value"
            inline
          ></b-form-spinbutton>
          <br /><br/>
        </div>
        <button type="button" class="btn btn-outline-info" @click="Order()">
          <b-icon icon="minecart-loaded"></b-icon> เพิ่มไปยังตระกร้า
        </button>
      </b-card>
    </div>

  </div>
</template>

<script>
export default {
  props: {
    name: String,
    img: String,
    price: Number,
  },
  data() {
    return {
      value: Number,
    };
  },
  methods: {
    Order() {
      alert("เลือกสินค้าใส่ตระกร้าเรียบร้อย"+this.name);
      this.$emit("Order", {
        name: this.name,
        price: this.price,
        value: this.value,
        Total: this.price * this.value
      });
    }
  }
};
</script>
<style></style>
