# dxDataGrid - How to implement a custom store with CRUD operations


<p>The <a href="http://js.devexpress.com/Documentation/Howto/UI_Widgets/Data_Grid/Data_Binding/#UI_Widgets_Data_Grid_Data_Binding_Provide_Data_Using_the_Data_Library_Using_a_CustomStore">dxDataGrid binding using a CustomStore</a> help topic and the <a href="https://www.devexpress.com/Support/Center/p/KA18955">A custom data source does not apply paging, filtering, sorting and grouping</a> article describe how to implement a custom data source that loads data for a <a href="http://js.devexpress.com/Documentation/ApiReference/UI_Widgets/dxDataGrid">dxDataGrid</a>. This example demonstrates how to make a custom store for the dxDataGrid widget manipulate data. For this purpose, we need to implement the <a href="http://js.devexpress.com/Documentation/ApiReference/Data_Library/CustomStore/Methods/#insertvalues">insert</a>, <a href="http://js.devexpress.com/Documentation/ApiReference/Data_Library/CustomStore/Methods/#updatekey_values">update</a> and <a href="http://js.devexpress.com/Documentation/ApiReference/Data_Library/CustomStore/Methods/#removekey">remove</a> methods in our custom store. Each of these methods will be called automatically by the widget. <br><br>The <strong>insert</strong> method accepts a parameter that contains values for a new item. The <strong>update</strong> method accepts two parameters: the first one is a key value of the editing row, and the second one contains values of modified data fields. The <strong>remove</strong> method accepts a parameter that contains a key value of the deleted row. When a method is called, we need to send a corresponding request to our data service and pass the required parameters. We use <a href="http://api.jquery.com/jquery.ajax/">jQuery.ajax</a> for sending requests to our data service.<br><br></p>
<p><strong>Starting with 15.2, </strong>dxDataGrid supports the sorting, filtering, grouping, paging and summary operations on the server side. See <a href="http://js.devexpress.com/Documentation/Guide/UI_Widgets/Data_Grid/Use_Custom_Store/#Remote_Operations">Use CustomStore - Remote Operations</a> to learn more. It is not necessary to implement a custom store manually. It is sufficient to create it using the <strong>DevExpress.data.AspNet.createStore</strong> method implemented in the <strong>dx.aspnet.data.js</strong> library. This library is a part of the <a href="https://github.com/DevExpress/DevExtreme.AspNet.Data">DevExtreme.AspNet.Data</a> data layer extension for ASP.NET MVC. Please take a look at the <strong>db.js</strong> file to see how to create a custom data store using the <strong>DevExpress.data.AspNet.createStore</strong> method. You can test this solution with the data service implemented in the <a href="https://www.devexpress.com/Support/Center/p/T334360">How to implement a data service that supports remote operations for dxDataGrid</a> example. </p>
<p><br><strong>For versions prior to 15.2: </strong><br> This example can be tested with a data service from <a href="https://www.devexpress.com/Support/Center/p/E4462">How to implement the Rest service based on an ASP.NET WebAPI application</a>.</p>
<br><strong>See also:<br></strong><a href="http://js.devexpress.com/Documentation/Guide/UI_Widgets/Data_Grid/Use_Custom_Store/#Remote_Operations">Use CustomStore - Remote Operations</a><strong><br></strong><a href="http://api.jquery.com/category/deferred-object/">Deferred Object</a><strong> <br></strong><a href="http://api.jquery.com/jquery.extend/">jQuery.extend</a> <br><a href="https://www.devexpress.com/Support/Center/p/E4816">How to implement CRUD operations with a DataSource</a><br><a href="https://www.devexpress.com/Support/Center/p/T218257">dxDataGrid - How to implement a custom store with CRUD operations (SQLite)</a>

<br/>


