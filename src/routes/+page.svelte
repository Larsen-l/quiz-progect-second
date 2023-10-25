
<body>

    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img src="background.png" alt="this is the background image">
<div class="bg-text">

    <form>
        <input type="text" id="username"  placeholder="username">
        <input type="submit" id="log in" value="log in">
      </form>
    </div>  
</body>

<head>
    <style>
    body {
      background-color:#FBB900 ;
    }
    .bg-text {
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(255,255,255, 0.7); /* Black w/opacity/see-through */
  color: black;
  font-size: 80px;
  border: 10px solid black;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 225px;
  padding: 225px;
  text-align: center;
}
.img {
    position: center;
}

    </style>
    </head>