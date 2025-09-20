<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Unlimited QR Scanner</title>
  <script src="https://unpkg.com/html5-qrcode/minified/html5-qrcode.min.js"></script>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; margin: 20px; }
    #reader { width: 300px; margin: auto; }
    #result { margin-top: 20px; font-weight: bold; }
  </style>
</head>
<body>
  <h2>Unlimited QR Scanner</h2>
  <div id="reader"></div>
  <div id="result">Scan a QR code...</div>

  <script>
    function onScanSuccess(decodedText) {
      document.getElementById("result").innerText = "Scanned: " + decodedText;
      // You can keep scanning — it won’t block repeats
    }

    function onScanError(errorMessage) {
      // Ignore errors quietly
    }

    let html5QrcodeScanner = new Html5QrcodeScanner(
      "reader", { fps: 10, qrbox: 250 });
    html5QrcodeScanner.render(onScanSuccess, onScanError);
  </script>
</body>
</html>
