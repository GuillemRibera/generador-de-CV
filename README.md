# 📄 Creador de Currículums Avançat

Un generador de currículums web bilingüe (Castellà / Català) contingut en un únic fitxer HTML. 
Aquesta eina permet als usuaris introduir les seves dades personals i professionals de manera intuïtiva, reorganitzar les seccions, personalitzar el disseny visualment i exportar el resultat a múltiples formats de manera local, garantint la privacitat.

## ✨ Característiques Principals

*   **Aplicació de Pàgina Única (Single-File):** Tot l'HTML, CSS i JavaScript està contingut dins del fitxer `CreadordeCV.html`. No requereix instal·lació, dependències externes ni base de dades.
*   **Bilingüe:** Interfície i plantilles disponibles en Castellà i Català, intercanviables en temps real.
*   **Privacitat Total i Autodesat (Auto-save):** Les dades no s'envien a cap servidor. Es guarden automàticament al navegador de l'usuari mitjançant `localStorage`.
*   **Importació i Exportació de Dades:** Les dades del formulari es poden descarregar com un fitxer `.json` i importar-les més endavant per continuar editant on ho vas deixar.
*   **Edició Visual Inline (WYSIWYG):** Fes clic directament sobre la previsualització del currículum per canviar la mida de la lletra, l'alineació, posar negretes o canviar els colors del text i fons.
*   **Drag & Drop (Arrossegar i Deixar Anar):** Reorganitza l'ordre de l'experiència, formació o idiomes arrossegant els blocs a la previsualització.
*   **Gestió d'Imatges Intel·ligent:** Puja o arrossega la teva foto de perfil. L'eina la redimensiona i comprimeix automàticament (per sota de 800px) per no saturar la memòria del navegador.
*   **Múltiples Formats d'Exportació:**
    *   **Imprimir / PDF:** Generat mitjançant la funcionalitat d'impressió nativa del navegador (esborra automàticament l'editor i els botons en la vista d'impressió).
    *   **Microsoft Word (.doc):** Exportació directa compatible amb programari d'ofimàtica de Microsoft.
    *   **LibreOffice (.odt):** Exportació directa a format de document obert.
*   **Disseny Responsiu:** L'eina s'adapta perfectament tant a ordinadors d'escriptori com a telèfons mòbils.

## 🚀 Com començar (Ús)

Com que el projecte no requereix cap entorn de servidor (Node.js, PHP, etc.), utilitzar-lo és tan fàcil com:

1. Descarregar o clonar aquest repositori.
2. Fer doble clic sobre el fitxer `CreadordeCV.html` per obrir-lo al teu navegador web preferit (Chrome, Firefox, Safari, Edge...).
3. Començar a omplir els teus dades!

## 🛠 Tecnologies Utilitzades

*   **HTML5** per a l'estructura semàntica.
*   **CSS3** amb variables (Custom Properties) per a l'estil, incloent `@media print` per a la conversió neta a PDF, i disseny basat en `Flexbox` per fer-lo responsiu en mòbils.
*   **Vanilla JavaScript (ES6)**:
    *   `localStorage` per a la persistència de dades.
    *   `FileReader` i `Canvas API` per a la lectura i compressió d'imatges.
    *   `HTML5 Drag and Drop API` per a reordenar seccions a la previsualització.
    *   Exportació de l'HTML generat cap a formats Office mitjançant `Blob`.

## 📁 Estructura del Codi

Tot el codi es troba dividit lògicament dins l'HTML:
*   `<style>`: Estils globals, components de formulari, estils de previsualització, variables de color i control responsiu.
*   `<div id="form-section">`: Interfície d'entrada de dades (Formulari principal).
*   `<div id="preview-section">`: Eines de format (barra superior) i zona on es genera l'HTML final del currículum.
*   `<script>`:
    *   `translations`: Diccionari d'idiomes.
    *   Gestió d'Imatges (Canvas & FileReader).
    *   Lògica del formulari dinàmic (afegir/eliminar experiència, idiomes...).
    *   Lògica de generació del CV (`generatePreview`).
    *   Controls d'edició visual.
    *   Exportacions (Doc/ODT/JSON).

## 📝 Crèdits i Llicència

Eina creada pel Dani, l'Adrià i el Guillem amb l'ajuda de IA per als Punts Òmnia.

Aquest projecte es distribueix sota la llicència **Creative Commons BY-NC-SA 4.0** (Atribució - No Comercial - Compartir Igual). Això vol dir que pots modificar i adaptar aquest codi lliurement, sempre que n'esmentis l'autoria original, no l'utilitzis per a fins comercials, i comparteixis les teves adaptacions sota la mateixa llicència.
