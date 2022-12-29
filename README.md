# Flexi-box

Flexi Box item to select multiple items from a collection with fixed price.

Follow the followings steps into your Dawn theme code:

1. Include the jQuery CDN link to the section of your theme.liquid file.

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>

2. Create a new section file flexi-box-multi-product.liquid in the sections directory.

3. Paste the code from the flexi-box-multi-product.liquid file.

4. Create a new product template in JSON format product.flexi-box-product.json in the templates directory.

<img src="https://camo.githubusercontent.com/422b7cbccaaa44f732dc42a3f77db62a08dbf45b9f912fc45dc942c7b62e0b93/68747470733a2f2f63646e2e73686f706966792e636f6d2f732f66696c65732f312f303536312f393235362f353239322f66696c65732f50696374757265312e706e673f763d31363530383733333533" style="width:50%;">


5. Paste the code from the product.flexi-box-product.json file.

6. Create a new product for the Flexi Box item with title and price (eg. Ultimate Perfume Box/Rs. 999/-) and choose the template flexi-box-product.

7. Create a new manual/smart collection for Flexi Box item with a title (eg. Flexi Box Collection).

8. Create a new asset file flexi-box-multi.css in the assets directory.

9. Paste the code from the flexi-box-multi.css file.

10. Create a new asset file flexi-box-multi.js in the assets directory.

11. Paste the code from the flexi-box-multi.js file.

12. Create a new liquid snippet file flexi-box-img-wrapper.liquid in the snippets directory.

13. Paste the code from the flexi-box-img-wrapper.liquid file.

14. Open Customize editor and go to the Flexi box item and open Flexi Box Product section. Choose your Flexi Box collection and select the maximum allowed products.

<img src="https://camo.githubusercontent.com/1fc10a8dcf5ba8b32f68cab677d046f5826ebe11ad0156b6fb95671e4957fbc5/68747470733a2f2f63646e2e73686f706966792e636f6d2f732f66696c65732f312f303536312f393235362f353239322f66696c65732f50696374757265322e706e673f763d31363530383733333533" style="width:30%;">

15. Add hidden tag to the Flexi Box item to hide it from the collection pages and the search page results.

16. Go to the file main-collection-product-grid.liquid in the sections directory and find(Ctrl + F) {%- for product in collection.products -%}. Paste the following code, best right after {% for product in collection.products %} and before the <b>li</b> tag.


{% assign displayProduct = true %}
  {% if product.tags contains 'hidden' %}
  {% assign displayProduct = false %}
  {% endif %}
  {% if displayProduct %}
  

17. And paste {% endif %} after the closing the </li> tag and before the {% endfor %}. This will probably look similar to this:

<img src="https://camo.githubusercontent.com/183ca0a7864c902f4a07b7ede62d7c8de8c8dc020ee9fc2cdd61d8d5101c8240/68747470733a2f2f63646e2e73686f706966792e636f6d2f732f66696c65732f312f303536312f393235362f353239322f66696c65732f50696374757265332e706e67" style="width:50%;">

18. Go to the file main-search.liquid in the sections directory and find(Ctrl + F) {%- for item in search.results -%}. Paste the following code, best right after {%- for item in search.results -%} and before the <b>li</b> tag.

{% assign displayProduct = true %}
  {% if product.tags contains 'hidden' %}
  {% assign displayProduct = false %}
  {% endif %}
  {% if displayProduct %}

19. And paste {% endif %} after the closing the </li> tag and before the {% endfor %}. This will probably look similar to this:

<img src="https://camo.githubusercontent.com/746f34629bc1ccbec730c5d47fa6c4491df79373980c098a04c45fcd89cffed7/68747470733a2f2f63646e2e73686f706966792e636f6d2f732f66696c65732f312f303536312f393235362f353239322f66696c65732f50696374757265342e706e67" style="width:50%;">

