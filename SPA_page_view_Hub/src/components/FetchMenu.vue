<script>
   function getBodyContent( text ) {
        const parser = new DOMParser();
        const doc = parser.parseFromString(text, "text/html");  // HTMLをDOMに変換
        return doc.body.innerHTML;  
   }

   async function renderPage( path ) {
    const data = await fetch(path)
    const html_data = await data.text();
    let element = document.getElementById("fetch-area");
    element.innerHTML = element.innerHTML + getBodyContent(html_data);
  };

  let mydata = fetch("/pages/index.json")
             .then( response => response.text() )
             .then( data => JSON.parse(data) )
             .then( data => {
                    data.children.forEach((child, index) => { 
                        console.log(child.type);
                        if (child.type == "file") {
                            console.log("Load page:" + data.path + child.path );
                            renderPage( data.path + child.path );
                        }
                    });
                }
             );
</script>

<template>
  <div id="fetch-area"> </div>
</template>

<style>
#fetch-area  h1 {
     color: red;
  }
</style>