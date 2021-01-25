<template>
  <div class="">
    <Card
      :images="images"
      :cardColor="cardColor"
      :stripColor="stripColor"
      :buttonColor="buttonColor"
      :textColor="textColor"
    ></Card>
  </div>
</template>

<script>
import Card from "./components/Card";
export default {
  data() {
    return {
      cardColor: "#122936",
      stripColor: "#41b883",
      buttonColor: "#41b881",
      textColor: "#fff",
      images: [
        {
          src: "headphone.png",
          title: "Headphone",
          price: "89.99₺",
          url: "",
          btnText: "Satın Al",
          cardContent: "Content",
        },
        {
          src: "macbook.png",
          title: "Macbook Pro",
          price: "9.999₺",
          url: "",
          btnText: "Satın Al",
          cardContent: "Content",
        },
        {
          src: "klavye.png",
          title: "Gaming Keyboard",
          price: "49.99₺",
          url: "",
          btnText: "Satın Al",
          cardContent: "Content",
        },
        {
          src: "monitor.png",
          title: "Gaming Monitor",
          price: "519.99₺",
          url: "",
          btnText: "Satın Al",
          cardContent: "Content",
        },
      ],
    };
  },
  components: {
    Card,
  },
};
</script>

<style >

</style>
