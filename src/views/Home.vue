<template>
  <div class="home">
    <div>
  <b-carousel
    id="carousel-no-animation"
    style="text-shadow: 0px 0px 2px #000"
    no-animation
    indicators
    img-width="1024"
    img-height="480"
  >
    <b-carousel-slide
      img-src="http://bowbakery.co.th/wp-content/uploads/2015/07/modified-2.jpg"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="http://bowbakery.co.th/wp-content/uploads/2015/07/modified-1.jpg"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="https://www.unileverfoodsolutions.co.th/th/chef-inspiration/best-foods-bakers-partner/new-sensations-to-impress-customers/jcr:content/parsys/header/articleheader/previewImage.transform/jpeg-optimized/image.1540999177218.jpg"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="http://fb1-cv.lnwfile.com/5nqnj7.jpg"
    ></b-carousel-slide>
  </b-carousel>
</div>
    <div class="row">
      <HelloWorld
        class="col-3"
        v-for="(item, index) in nun"
        :key="index"
        :img="item.img"
        :name="item.name"
        :price="item.price"
        @Order="menuorder"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  data() {
    return {
      select: [],
      nun: [
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/%E0%B9%80%E0%B8%84%E0%B8%A3%E0%B8%9B%E0%B9%80%E0%B8%84%E0%B9%89%E0%B8%81%E0%B8%AA%E0%B8%A3%E0%B8%AD%E0%B9%80%E0%B8%9A%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%A3%E0%B8%B5%E0%B9%881-405x405.jpg",
          name: "เครปเค้กสตรอเบอร์รี่",
          price: 45,
        },
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/%E0%B8%9A%E0%B8%A5%E0%B8%B9%E0%B9%80%E0%B8%9A%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%A3%E0%B8%B5%E0%B9%88%E0%B8%8A%E0%B8%B5%E0%B8%AA%E0%B9%80%E0%B8%84%E0%B9%89%E0%B8%81-405x405.jpg",
          name: "บลูชีสเค้ก ",
          price: 35,
        },
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/%E0%B8%AA%E0%B8%95%E0%B8%A3%E0%B8%AD%E0%B9%80%E0%B8%9A%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%A3%E0%B8%B5%E0%B9%88%E0%B8%8A%E0%B8%B5%E0%B8%AA%E0%B9%80%E0%B8%84%E0%B9%89%E0%B8%81-405x405.jpg",
          name: "สตรอชีสเค้ก",
          price: 35,
        },
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Croissant-1024x1024-405x405.jpg",
          name: "ครัวซองท์",
          price: 30,
        },
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Whole-wheat-sandwich-%E0%B8%9E%E0%B8%A3%E0%B8%B5%E0%B9%80%E0%B8%A1%E0%B8%B5%E0%B9%88%E0%B8%A2%E0%B8%A1%E0%B9%81%E0%B8%8B%E0%B8%99%E0%B8%94%E0%B9%8C%E0%B8%A7%E0%B8%B4%E0%B8%8A-%E0%B8%AD%E0%B8%B2%E0%B8%A2%E0%B8%B8%E0%B8%AA%E0%B8%B4%E0%B8%99%E0%B8%84%E0%B9%89%E0%B8%B2-3-%E0%B8%A7%E0%B8%B1%E0%B8%99%E0%B9%81%E0%B8%8A%E0%B9%88%E0%B9%80%E0%B8%A2%E0%B9%87%E0%B8%99-1024x1024-405x405.jpg",
          name: "พรีเมี่ยมแซนด์วิช",
          price: 35,
        },
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Strawberry-puff-1024x1024-405x405.jpg",
          name: "พัฟแยมสตรอ",
          price: 30,
        },
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/3.Crispy-bread-butter-%E0%B8%82%E0%B8%99%E0%B8%A1%E0%B8%9B%E0%B8%B1%E0%B8%87%E0%B8%81%E0%B8%A3%E0%B8%AD%E0%B8%9A%E0%B9%80%E0%B8%99%E0%B8%A2-%E0%B8%AD%E0%B8%B2%E0%B8%A2%E0%B8%B8%E0%B8%AA%E0%B8%B4%E0%B8%99%E0%B8%84%E0%B9%89%E0%B8%B2-30-%E0%B8%A7%E0%B8%B1%E0%B8%99-1024x1024-405x405.jpg",
          name: "ขนมปังกรอบเนย",
          price: 30,
        },
        {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Almond-chocolate-cracker-1024x1024-405x405.jpg",
          name: "แครกเกอร์อัลมอนด์",
          price: 59,
        },
         {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Tuna-Roll-1024x1024-405x405.jpg",
          name: "โรลทูน่า",
          price: 29,
        },
         {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Cheese-sausage-bun-%E0%B8%82%E0%B8%99%E0%B8%A1%E0%B8%9B%E0%B8%B1%E0%B8%87%E0%B9%84%E0%B8%AA%E0%B9%89%E0%B8%81%E0%B8%A3%E0%B8%AD%E0%B8%81%E0%B8%8A%E0%B8%B5%E0%B8%AA-%E0%B8%AD%E0%B8%B2%E0%B8%A2%E0%B8%B8%E0%B8%AA%E0%B8%B4%E0%B8%99%E0%B8%84%E0%B9%89%E0%B8%B2-2-%E0%B8%A7%E0%B8%B1%E0%B8%99-1024x1024-405x405.jpg",
          name: "ขนมปังไส้กรอกชีส",
          price: 29,
        },
         {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Nut-meringue-bucket-1024x1024-405x405.jpg",
          name: "นัทเมอแรงค์ถัง",
          price: 59,
        },
         {
          img:
            "http://bowbakery.co.th/wp-content/uploads/2015/08/Choc-rice-meringue-1024x1024-405x405.jpg",
          name: "เมอแรงค์ 60 กรัม ช็อคไรท์",
          price: 59,
        },
      ],
    };
  },
  methods: {
    menuorder(value) {
      this.$emit("Order", value);
    },
  },
};
</script>
