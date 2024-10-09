## Project-2

Landing page

## what you will learn?

- Two Div overlaping problem when one is absolute

  ![absolute overlap on normal div](./images/problem.png)

- HTML:

  ````<body>
   <div class="main">
   <div class="intro">
   <div class="name">
   <h1>Isha Gupta</h1>
   <h1 id="box-h1">FullStack Developer</h1>
   <h3>(India)</h3>
   </div>
   <div class="scroll">
   <button><i class="ri-arrow-right-down-line"></i>Scroll Down</button>
   </div>
   </div>
   </div>
     </body>
       ```

  ````

- CSS:

  ```
  * {
    margin: 0;
    padding: 0;
    box-model: boder-box;
    font-family: areal;
    }
    html,
    body {
    width: 100%;
    height: 100%;
    }
    .main {
    height: 100%;
    width: 100%;
    }
    .intro {
    background-color: #cf77;
    border: 2px solid red;
    height: 40%;
    width: 100%;
    // display: flex;
    /_ flex: wrap; _/
    }
    .name {
    /_ font-size:30px; _/
    font-weight: 500;
    padding: 20px;
    line-height: null;
    border: 2px solid blue;
    width: fit-content;
    }
    #box-h1 {
    background-color: white;
    width: fit-content;
    color: blue;
    }
    .name h3 {
    font-size: 9px;
    }

    .header {
    border: 2px solid green;
    }
    .scroll {
    position: absolute;
    top: 5px;
    right: 5px;
    display: flex;
    border: 2px solid blue;
    padding: 5px;
    }
  ```
