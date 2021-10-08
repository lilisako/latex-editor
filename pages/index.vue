<template>
  <div class="m-3">
    <!-- header -->
    <div class="flex text-xl md:text-6xl font-bold justify-center py-2">
      <vue-mathjax :formula="logo" />
      <h1 class="ml-2">Playground</h1>
    </div>
    <!-- editor -->
    <div class="flex flex-wrap my-3">
      <div class="w-full md:w-1/2 flex items-center justify-center p-3 font-bold border-2 border-black rounded-xl">
        <textarea v-model="tex" placeholder="type latex" class="w-full h-80 max-h-80 font-bold outline-none resize-none" >
        </textarea>
      </div>
      <div class="w-full md:w-1/2 flex items-center justify-center p-3">
        <vue-mathjax :formula="tex" />
      </div>
    </div>
    <!-- footer -->
    <div class="flex justify-center py-3"> 
      <p class="text-sm font-bold">Created by Risako🐻‍❄️</p>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return { script: [ { src: "https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS-MML_SVG" } ] };
  },
  data() {
    return {
      logo: String.raw`$\LaTeX$`,
      tex: String.raw`$$x(n)y(n) \Leftrightarrow \frac{1}{{2\pi }}\int\limits_{ - \pi }^\pi  {X(e^{j\theta } )Y(e^{j(\omega  - \theta )} )d\theta }$$`
    };
  }
}
</script>
