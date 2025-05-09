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
    RenderMathJax();
  };

  function listMenu(parent) {
    let index = parent + "/index.json";
    console.log(index);
    fetch(index)
    .then(data => data.json())
    .then(data => {
        console.log(data.id);
        data.children.forEach((child, index) => {
            let element = document.getElementById(data.id);

            if (child.type == "file") element.innerHTML = element.innerHTML + '<li> <a href="javascript:void(0)" id="' + child.id + '">' + child.title + '</a></li>';
            if (child.type == "directory") element.innerHTML = element.innerHTML + '<li>' + child.title + '</li>';


            if(child.type == "directory"){
                console.log(child.type);
                let child_path = data.path + child.path;
                let child_menu_id = data.id + "-" + child.path;
                console.log(child_path);
                console.log(child_menu_id);
                console.log('<ul id="' + child_menu_id + '"> </ul>');
                element.innerHTML = element.innerHTML + '<ul id="' + child_menu_id + '"> </ul>';
                listMenu(child_path);
            }
        });

        data.children.forEach((child, index) => {
            if (child.type == "file") {

                document.getElementById(child.id).addEventListener("click", function(event) {
                event.preventDefault(); // デフォルトの動作を防ぐ
                console.log(data.path + child.path);
                renderPage( data.path + child.path);                
            });
        }
    });
    }); 
}

listMenu("/pages")
</script>

<template>
    <div class="wrap ">
        <h1 class="menu-title"> Studio Silence </h1>
        <ul id="menu">
        </ul>
    </div>
</template>

<style scoped>
 .wrap {
    width: 30%;
 }

</style>