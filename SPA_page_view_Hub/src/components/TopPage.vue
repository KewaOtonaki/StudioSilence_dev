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
    element.innerHTML = getBodyContent(html_data);
  };

  let mydata = fetch("/pages/index.json")
             .then( response => response.json() )
             .then( data => {
                    data.children.forEach((child, index) => { 
                        console.log(child.path);
                        console.log(child.type);
                        let element = document.getElementById("menu-list");
                        element.innerHTML = element.innerHTML + '<li> <a href="javascript:void(0)" id="' + child.id + '">' + child.title + '</a></li>';
                    });

                    data.children.forEach((child, index) => {
                        document.getElementById(child.id).addEventListener("click", function(event) {
                            event.preventDefault(); // デフォルトの動作を防ぐ
                            console.log(data.path + child.path);
                            renderPage( data.path + child.path);
                        });
                    })
                }
             );
</script>

<template>

  <h1> Studio Silence </h1>

  <ul id="menu-list">
  </ul>

</template>

<style>
</style>