<template>
  <div>
    <h1>{{ judul }}</h1>

    <div>{{ subjudul }}</div>

    <div class="row">
      <div class="col-sm-6">
        <label for="">Angka 1</label>
        <input type="text" v-model="angka1" class="form-control form-control-sm">
      </div>
      <div class="col-sm-6">
        <label for="">Angka 2</label>
        <input type="text" v-model="angka2" class="form-control form-control-sm">
      </div>
      <div class="col-sm-6">
        <button class="btn btn-sm btn-primary" @click="penjumlahan()">Hasil</button>
        <div class="text-success">{{ hasil }}</div>
      </div>
    </div>

    <div class="container mt-5">
      <div class="row">
        <div class="col-sm-3" v-for="(x, index) in dataprodukx" :key="index">
          <div class="card">
            <div class="card-body">
              {{ x.nama_produk }}
            </div>
            <div class="card-footer">
              Rp {{x.harga}}
            </div>
          </div>
        </div>

      </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      judul: "Judul Produk",
      subjudul: "sdfhjsadkjfash asdfhaskj",
      pesan: "tes 123",
      angka1: 0,
      angka2: 0,
      hasil: 0,
      dataprodukx: [
        {
          "id": 1,
          "nama_produk": "Laptop ABC",
          "harga": 15000000,
          "stok": 20,
          "kategori": "Elektronik"
        },
        {
          "id": 2,
          "nama_produk": "Smartphone XYZ",
          "harga": 8000000,
          "stok": 50,
          "kategori": "Elektronik"
        },
        {
          "id": 3,
          "nama_produk": "Headphone DEF",
          "harga": 500000,
          "stok": 100,
          "kategori": "Aksesoris"
        },
        {
          "id": 4,
          "nama_produk": "Kemeja GHI",
          "harga": 250000,
          "stok": 30,
          "kategori": "Pakaian"
        },
        {
          "id": 5,
          "nama_produk": "Sepatu JKL",
          "harga": 700000,
          "stok": 25,
          "kategori": "Pakaian"
        }
      ]
      ,
    }
  },
  mounted() {
  },
  methods: {
    penjumlahan() {
      this.hasil = parseFloat(this.angka1) + parseFloat(this.angka2);
    }
  }

}
</script>

<style></style>