<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Love Question</title>

<style>
  body {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #ffe6f0;
    font-family: Arial, sans-serif;
    overflow: hidden;
  }

  .box {
    text-align: center;
  }

  h1 {
    font-size: 28px;
  }

  button {
    padding: 12px 25px;
    font-size: 18px;
    margin: 10px;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  #yes {
    background: #ff4d6d;
    color: white;
  }

  #no {
    background: #999;
    color: white;
    position: absolute;
  }
</style>
</head>

<body>

<div class="box">
  <h1 id="text">Do you love me Jeetika 🙂</h1>
  <button id="yes" onclick="yesClick()">Yes</button>
  <button id="no">No</button>
</div>

<script>
  let noCount = 0;
  let yesSize = 18;

  const messages = [
    "Soch lo Jeetika 😏",
    "Ek aur baar soch lo 🙄",
    "Sach me No? 😢",
    "Dil toot raha hai 💔",
    "Ab bhi No? 😐",
    "Man jao na 🥺",
    "Ye No pakka nahi hai 😄"
  ];

  const noBtn = document.getElementById("no");
  const yesBtn = document.getElementById("yes");

  // No click disable
  noBtn.addEventListener("click", e => e.preventDefault());

  // Hover / touch पर भागे (unlimited)
  noBtn.addEventListener("mouseover", moveNo);
  noBtn.addEventListener("touchstart", moveNo);

  function moveNo() {
    noCount++;

    // Message loop
    document.getElementById("text").innerText =
      messages[noCount % messages.length];

    // Yes button grows
    yesSize += 4;
    yesBtn.style.fontSize = yesSize + "px";

    // Random position for No
    noBtn.style.left = Math.random() * 75 + "%";
    noBtn.style.top = Math.random() * 75 + "%";
  }

  function yesClick() {
    document.body.innerHTML = `
      <h1 style="color:#ff1e56; font-size:40px; text-align:center;">
        thenkyu ❤️😊
      </h1>
    `;
  }
</script>

</body>
</html>
