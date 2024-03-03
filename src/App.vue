<script>
export default {
  data() {
    return {
      item: '',
      list: [],
    }
  },
  methods: {
    simpan() {
      // validasi                               // ← TODO 3: tambah validasi input user, ketika user tidak menambahkan input dan langsung menekan tombol tambah, munncul peringatan untuk mengisi input

      // fungsi simpan ke array
      this.list.push(this.item)
    }
  },
  computed: {
    isMoreThanFour: function () {
      return this.list.length >= 4;
    }
  },
}

</script>

<template>
  <!-- list -->
  <ul>
    <li v-for="(todo, index) in list" :key="index">{{ todo }}</li>      <!-- TODO 1: ubah ke urutan angka -->
  </ul>

  <!-- input -->
  <input type="text" v-model="item">
  <button @click="simpan">Simpan</button>
  <p>{{ list.length >= 4 ? 'Hebat' : '' }}</p>    <!-- TODO 2: ubah menggunakan computed -->
</template>

<style scoped>

</style>
