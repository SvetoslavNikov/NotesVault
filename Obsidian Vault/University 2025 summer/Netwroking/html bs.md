Here are several options to format the table without using CSS:

1. **Add Borders to Table Cells:**  
    You can add `border` attributes to the `<td>` and `<th>` tags to create individual cell borders:
    
    ```html
    <table border="2" bgcolor="#99e6ff">
        <tr>
            <th border="2">topic</th>
            <th border="2">command</th>
            <th border="2">explanation</th>
        </tr>
    ```
    
2. **Cell Spacing and Padding:**  
    You can use the `cellspacing` and `cellpadding` attributes to add space between cells or inside cells:
    
    ```html
    <table border="2" bgcolor="#99e6ff" cellspacing="5" cellpadding="10">
    ```
    
3. **Column Width:**  
    You can control the width of columns using the `width` attribute in `<td>` and `<th>`:
    
    ```html
    <th width="150">topic</th>
    <th width="150">command</th>
    ```
    
4. **Alignment:**  
    You can align content horizontally and vertically using `align` and `valign`:
    
    ```html
    <td align="center" valign="middle">tmux</td>
    ```
    
5. **Rowspan and Colspan:**  
    You can merge cells using `rowspan` and `colspan`:
    
    ```html
    <td rowspan="2">session</td>
    ```
    

These HTML attributes allow basic formatting without relying on CSS.