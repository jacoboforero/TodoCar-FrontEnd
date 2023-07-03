<script>
    // You can add your logic here.
  </script>
  
  <style>
    .footer {
      width: 100%;
      height: 350px;
      background-color: #202324;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 20px;
      box-sizing: border-box;
    }
    .columns {
      display: flex;
      justify-content: space-between;
      flex: 1;
    }
    .column {

      flex: 1;
      margin: 0 10px;
    }
    .mainColumns .column h1{
        color:white;
        font-size: 18px;
    }

#mainFooterTitle{

    font-size: 46px;
}


    .bottom {
      text-align: center;
    }
    .bottom p{
        color:white;
    }
  </style>
  
  <footer class="footer">
    <div class="columns mainColumns">
      <div class="column mainColumns">
        <h1>Company</h1>
      </div>
      <div class="column mainColumns">
        <h1>Resources</h1>
      </div>
      <div class="column mainColumns">
        <h1>Product</h1>
      </div>
      <div class="column rightColumn">
        <h1 id="mainFooterTitle">TodoCar</h1>
      </div>
    </div>
    <div class="bottom">
      <p>©2023 TodoCar</p>
      <!-- Social media links goes here -->
    </div>
  </footer>
  