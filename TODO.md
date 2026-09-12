
- [x] In `index.html`, in the `addRow` function, insert the following HTML snippet right before the `<button class="x">` closing tag:
  ```html
  <button class="duplicate" title="Duplicate segment">Duplicate</button>
  ```
  This duplicates the segment right below it when clicked. The exact anchor line is:
  ```html
  '<td><button class="x" title="Remove segment">&times;</button></td>';
  ```

- [x] In `index.html`, immediately after the `addRow` function definition, add the following event listener for the duplicate button:
  ```javascript
  tr.querySelector("button.duplicate").addEventListener("click", function () {
      var seg = {
          len: tr.querySelector(".len").value,
          load: tr.querySelector(".load").value,
          size: tr.querySelector(".size").value
      };
      addRow(seg);
      update();
  });
  ```
  This code duplicates the segment when the duplicate button is clicked. The exact anchor line is:
  ```javascript
  tr.querySelector("button.x").addEventListener("click", function () {
      if (rowsEl.children.length > 1) { tr.remove(); update(); }
  });
  ```
  This ensures that the new event listener is added after the remove button's event listener.
