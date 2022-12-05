<template>
  <article class="top-bunner py_l">
    <div class="container">
      <!--   <img src="../assets/buy-comics-digital-comics.png" alt=""> -->
      <ul class="list-group-flush d-flex justify-content-around">
        <li class="list-group-item"
            v-for="(link, i) in bunnerLinks">
          <a target="_blank" class="d-flex align-items-center" :href="link.href">

            <!--  <img :src="getImgUrl(`../assets/`, link.imgName, `png`)" :alt="link.imgName"> -->

            <!-- <img :src="getImgUrl()" :alt="link.imgName"> -->

            <img :src="gotImgUrl(link.imgName)" :alt="link.imgName"> 

            <h6 class="text-uppercase p-3 small">{{ link.name }}</h6>
          </a>

        </li>
      </ul>
    </div>
  </article>
</template>

<script>
export default {
  data() {
    return {
      bunnerLinks: [
        {
          name: "digital comics",
          imgName: "buy-comics-digital-comics",
          href: "https://www.dcuniverseinfinite.com/",
        },
        {
          name: "dc merchandise",
          imgName: "buy-comics-merchandise",
          href: "https://shop.dc.com/",
        },
        {
          name: "print subscriptions",
          imgName: "buy-comics-shop-locator",
          href: "https://www.dc.com/subscriptions",
        },
        {
          name: "comic shop locator",
          imgName: "buy-comics-subscriptions",
          href: "https://www.dc.com/ComicShopLocator",
        },

      ],
    }
  },
  methods: {

    /* FUNZIONE GENERICA NON FUNZIONANTE */
    //dovrebbe creare un valido URL per l'src delle immagini
    /**
     * 
     * @param {string} relativeURL percorso relativo          es: "../assets/"
     * @param {string} fileName nome del file immagine        es: "pincopallo"
     * @param {.string} format formato del file               es: "png"
     */
    getImgUrl(relativeURL, fileName, format) {

      /*       return new URL(`${relativeURL}${fileName}.${format}`, import.meta.url); */

      //variante semplificata creando una const ma non funge (da aggiungere il punto al format     es:  ".png")
      /*   let imgURL = relativeURL + fileName + format;
        console.log("imgURL", imgURL);
        return new URL(`${imgURL}`, import.meta.url); */
    },



    /* FUNZIONE SEMPLIFICATA DOVE IL PERCORSO E IL FORMATO SONO STATICI DA INSERIRE IN V_FOR*/
    //sembra funzionare da console ma in ciclo non finziona 

    gotImgUrlProva(fileName) {
      let i = 0
      while (i < this.bunnerLinks.length) {

        let imgURL = new URL(`../assets/${fileName}.png`, import.meta.url);
          console.log("go", imgURL); 
        i++
      }
    },
    gotImgUrl(fileName) {
        // return new URL(`../assets/${fileName}.png`, import.meta.url);
    /* ERRORE */
    /* [plugin:vite:import-analysis] Failed to parse source for import analysis because the content contains invalid JS syntax. Install @vitejs/plugin-vue to handle .vue files.
C:/Users/marika/BOOLEAN_projects/vite-comics/src/components/TopBunner.vue:108:101
106|  
107|  
108|  import { createCommentVNode as _createCommentVNode, renderList as _renderList, Fragment as _Fragment, openBlock as _openBlock, createElementBlock as _createElementBlock, createElementVNode as _createElementVNode, toDisplayString as _toDisplayString, pushScopeId as _pushScopeId, popScopeId as _popScopeId } from "vue"
   |                                                                                                      ^
109|  
110|  const _withScopeId = n => (_pushScopeId("data-v-091cea8c"),n=n(),_popScopeId(),n)
    at formatError (file:///C:/Users/marika/BOOLEAN_projects/vite-comics/node_modules/vite/dist/node/chunks/dep-67e7f8ab.js:39975:46)
    at TransformContext.error (file:///C:/Users/marika/BOOLEAN_projects/vite-comics/node_modules/vite/dist/node/chunks/dep-67e7f8ab.js:39971:19)
    at TransformContext.transform (file:///C:/Users/marika/BOOLEAN_projects/vite-comics/node_modules/vite/dist/node/chunks/dep-67e7f8ab.js:36772:22)
    at async Object.transform (file:///C:/Users/marika/BOOLEAN_projects/vite-comics/node_modules/vite/dist/node/chunks/dep-67e7f8ab.js:40228:30)
    at async loadAndTransform (file:///C:/Users/marika/BOOLEAN_projects/vite-comics/node_modules/vite/dist/node/chunks/dep-67e7f8ab.js:36615:29
Click outside or fix the code to dismiss.
You can also disable this overlay by setting server.hmr.overlay to false in vite.config.js. */
      
      }
    },

    /* FUNZIONE TRISTE CHE CICLANDO CREA VRIABILE DA INSERIRE COME PROPRIETA' src di this.bunnerLinks[i]  */
    _getImgUrl() {
      let i = 0
      while (i < this.bunnerLinks.length) {

        let src = new URL(`../assets/${this.bunnerLinks[i].imgName}.png`, import.meta.url)
        console.log("src",src)
        /*   this.bunnerLinks[i].push(src) */
        i++
      }
    },
    /* ___________________________________________________________________________ */


  },
  mounted() {


    // console.log(this.getImgUrl("../assets/",this.bunnerLinks[0].imgName,"png"));
    /* ERRORE:  
    [plugin:vite:import-glob] EPERM: operation not permitted, scandir 'C:\Documents and Settings'
    C:/Users/marika/BOOLEAN_projects/vite-comics/src/components/TopBunner.vue
    Click outside or fix the code to dismiss.
    You can also disable this overlay by setting server.hmr.overlay to false in vite.config.js.*/

    this.gotImgUrlProva(this.bunnerLinks[0].imgName);
 
    console.log("_______________________________________");
    this._getImgUrl();


  }
}

</script>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

* {
  border: 1px solid rgb(253, 249, 19);
}

.top-bunner {
  background-color: $primary;
  color: $light;

  a {
    color: $light;
  }
}
</style>