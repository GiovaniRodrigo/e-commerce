<template>
  <div class="home-page">
    <!-- Topbar -->
    <header class="topbar flex justify-between items-center p-4 bg-gray-100">
      <div class="logo font-bold text-xl">LOGO</div>
      <input type="text" placeholder="Pesquisar..." class="search border p-2 rounded" />
      <div class="cart">🛒 Carrinho</div>
    </header>

    <!-- Navbar -->
    <nav class="navbar bg-gray-200 p-3">
      <ul class="flex space-x-4">
        <li class="category">Categoria 1</li>
        <li class="category">Categoria 2</li>
        <li class="category">Categoria 3</li>
        <li class="category">Categoria 4</li>
      </ul>
    </nav>

    <!-- Banner Principal -->
    <section
      class="banner bg-blue-300 h-48 flex items-center justify-center text-white text-2xl font-bold my-4"
    >
      Banner Principal / Promoção
    </section>

    <!-- Seção: Produtos em Destaque -->
    <section class="featured-products my-4">
      <h2 class="text-xl font-bold mb-2">Produtos em Destaque</h2>
      <div class="grid grid-cols-2 gap-4">
        <div class="product-card p-4 border rounded text-center">Card Produto 1</div>
        <div class="product-card p-4 border rounded text-center">Card Produto 2</div>
      </div>
    </section>

    <!-- Seção: Novidades / Ofertas -->
    <section class="new-offers my-4">
      <h2 class="text-xl font-bold mb-2">Novidades / Ofertas</h2>
      <div class="grid grid-cols-2 gap-4">
        <div class="product-card p-4 border rounded text-center">Card Produto 3</div>
        <div class="product-card p-4 border rounded text-center">Card Produto 4</div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Home",
};
</script>

<style scoped>
.topbar input {
  width: 200px;
}

.category {
  cursor: pointer;
}
</style>
