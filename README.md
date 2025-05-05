<!DOCTYPE html>
<html>
  <head>
    <title>Parcel Sandbox</title>
    <meta charset="UTF-8" />
  </head>

  <body>
    <div id="app">
      <div
        id="myElement"
        style="width: 200px; height: 100px; background: lightblue"
      >
        Texte à convertir en SVG
      </div>
      <button onclick="convertHtmlToSvg(document.getElementById('myElement'))">
        Convertir en SVG
      </button>
    </div>

    <script>
      import { toSvg } from "html-to-image";

      function convertHtmlToSvg(element) {
        toSvg(element)
          .then((dataUrl) => {
            console.log("SVG généré : ", dataUrl);

            // Créer un élément <img> pour afficher le SVG
            const img = document.createElement("img");
            img.src = dataUrl;
            document.body.appendChild(img);
          })
          .catch((error) => {
            console.error("Erreur lors de la conversion en SVG :", error);
          });
      }
    </script>
    <script src="src/index.js"></script>
  </body>
</html>
