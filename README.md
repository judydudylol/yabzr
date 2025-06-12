# yabzr<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>Dislike Party</title>
<style>
  body { margin:0; overflow:hidden; background:#111; }
  .thumb {
    position: absolute;
    font-size: 48px;
    color: #555;
    opacity: 0;
    animation: fall 3s ease-in forwards;
  }
  @keyframes fall {
    to { transform: translateY(100vh); opacity:1; }
  }
</style>
</head>
<body>
<script>
  let count = 0;
  function dropThumb() {
    const d = document.createElement('div');
    d.className = 'thumb';
    d.textContent = '👎';
    d.style.left = Math.random()*100 + 'vw';
    d.style.animationDelay = Math.random()*2 + 's';
    document.body.appendChild(d);
    count++;
    if(count < 200) setTimeout(dropThumb, 100);
  }
  window.onload = () => dropThumb();
</script>
</body>
</html>
