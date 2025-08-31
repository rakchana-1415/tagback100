<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TagBack – Secure QR</title>
<style>
body{font-family:sans-serif;background:#f0f0f0;color:#000;text-align:center;padding:20px;}
input{padding:10px;margin:5px;width:80%;border-radius:5px;}
button{padding:10px 20px;margin:10px;border-radius:5px;}
#qrcode{margin-top:20px;}
</style>
</head>
<body>

<h1>TagBack – Create Your QR Tag</h1>

<p>Enter your details to generate a QR for your valuables:</p>

<input id="name" type="text" placeholder="Your Name"><br>
<input id="phone" type="text" placeholder="Phone Number"><br>
<button id="generate">Generate QR</button>

<div id="qrcode"></div>

<!-- QRCode library -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<script>
const generateBtn = document.getElementById('generate');
const qrBox = document.getElementById('qrcode');

generateBtn.onclick = () => {
  const name = document.getElementById('name').value.trim();
  const phone = document.getElementById('phone').value.trim();
  if(!name || !phone){
    alert("Please fill both fields");
    return;
  }
  qrBox.innerHTML = '';
  new QRCode(qrBox, {
    text: `Name: ${name}\nPhone: ${phone}`,
    width: 200,
    height: 200
  });
};
</script>

</body>
</html>
