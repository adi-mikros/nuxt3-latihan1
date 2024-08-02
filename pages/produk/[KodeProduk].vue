<template>
  <div>
    <h3>Idproduk : {{ $route.params.KodeProduk }}</h3>
    <h1>{{ nama }}</h1>
    <h5>Rp {{ harga }}</h5>
    <p>{{ deskripsi }}</p>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      nama: "",
      harga: "",
      deskripsi: "",
    }
  },
  mounted(){
    this.getData();
  },
  methods:{
    async getData(){
      let res = await axios.get("https://api-smnmart.biznizo.my.id/android/produk/detail/"+this.$route.params.KodeProduk );
      this.nama=res.data[0].Nama;
      this.harga=res.data[0].Harga;
      this.deskripsi=res.data[0].Deskripsi;
    }
  }

}
</script>

<style></style>