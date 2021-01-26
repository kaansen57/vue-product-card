<template>
    <Card
      :infos="infos"
      :cardColor="cardColor"
      :stripColor="stripColor"
      :buttonColor="buttonColor"
      :textColor="textColor"
    />
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
      infos: [
        {
          src: "headphone.png",
          title: "Headphone",
          price: "89.99₺",
          url: "",
          btnText: "Satın Al",
        },
        {
          src: "macbook.png",
          title: "Macbook Pro",
          price: "9.999₺",
          url: "",
          btnText: "Satın Al",
        },
        {
          src: "klavye.png",
          title: "Gaming Keyboard",
          price: "49.99₺",
          url: "",
          btnText: "Satın Al",
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
