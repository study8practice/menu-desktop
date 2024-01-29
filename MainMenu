<template>
  <header class="menu">
    <button class="btn-menu" @click="openMenu">
      Botão
    </button>

    <!-- <h4>Categorias</h4> -->

    <nav class="nav">
      <ul class="n1-lista">
        <li class="n1-itens" v-for="(n1, idN1) in n1menu" :key="idN1" @mouseenter="getIndice(idN1)">
          <span >{{n1.label}}</span>
          
          <div class="n2-wrapper">
            <ul class="n2-lista n2-listaSub n2-lista-1" v-if="n1.sub">

              <li>
                <ul class=" n2NoChildren-lista n2-listaSub n2-lista-1" v-show="n2NoChildren.length > 0">
                  <li class="n2-itens" v-for="(n2No, i) in n2NoChildren" :key="i">
                    {{n2No.label}}
                  </li>
                </ul>
              </li>
              
              <li  class="n2-itens" :class="{notChildren: n2.sub, empty: !n2.sub}" v-for="(n2, i) in n1.sub" :key="i" >
                <template v-if="n2.sub">
                  {{n2.label}}
                </template>
                <div class="n3-wrapper" v-if="n2.sub">
                  <ul class="n3-lista n3-listaSub n3-lista-1" >
                    <li  class="n3-itens" v-for="(n3, i) in n2.sub" :n3="n3" :key="i" >
                      {{n3.label}}
                    </li>
                  </ul>
                </div>
              </li>
            </ul>
          </div>
        </li>
      </ul>
    </nav>
  </header>
</template>
<script>
export default {
  name: 'MainMenu',
  props: ['n1menu'],
  data() {
    return {
      n2NoChildren: []
    }
  },
  methods: {
    getIndice(key){
      this.n2NoChildren = []

      this.n1menu[key].sub.forEach(m => {
        if(!m.sub){
          this.n2NoChildren.push(m)
        }
      });
    },
  },
  mounted() {
    const n2 = document.querySelectorAll(".empty")
    const n2Array = Array.from(n2)
    n2Array.forEach(t => {
      t.parentElement.removeChild(t)
    })

    // https://devarthur.com/blog/como-remover-um-elemento-html-pelo-javascript
    // https://horadecodar.com.br/como-converter-uma-nodelist-em-array-com-javascript/

    const itens = document.querySelectorAll('.n3-itens');
    const itensArray = Array.from(itens)
    itensArray.forEach((item) => {

      if(item.innerText.toLowerCase() === "ver tudo"){
        item.classList.add('underlined')
      } 
    })
  }
}
</script>

<style scoped>
ul {
  list-style: none;
}
.menu{
  height: 75px;
  background: #fdd900;
  display: flex;
  align-items: center;
}
@media(max-width: 1023px){
  .btn-menu{
    display: block;
  }
}
@media(min-width: 1024px){
  .btn-menu{
    display: none;
  }
  .nav{
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
  }
  .n1-lista{
    display: flex;
    align-items: center;
    position: relative;
  }
  .n1-itens{
    cursor: pointer;
    height: 75px;
    width: 172px;
    display: flex;
    align-items: center;
    color: #000;
  }
  .n1-itens:hover .n2-wrapper{
    display: block;
  }
  .n2-wrapper{
    display: none;
    background: #fff;

    max-width: 1200px;
    width: 100%;

    position: absolute;
    top: 75px;
    left: 0;
    height: 300px;
    overflow: auto;
  }
  .n2NoChildren-lista{
    max-width: 200px;
  }
  .n2-lista{
    display: grid;
    grid-template-columns: repeat(5, 200px);
    grid-gap: 36px;
    margin: 16px 24px;
  }
  .n2-itens{
    color: #000;
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 8px;
  }
  .n3-wrapper{
    margin-top: 8px;
  }
  .n3-itens{
    font-weight: 400;
    margin-bottom: 8px;
  }
  .n3-itens.underlined{
    text-decoration: underline;
  }
}
</style>
