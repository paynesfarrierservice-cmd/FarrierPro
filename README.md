# <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Farrier Pro Trial</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      overflow: hidden;
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
    }
    #app-container {
      flex: 1;
    }
    .subscription-container {
      display: none;
      text-align: center;
      padding: 50px;
    }
    .subscription-container button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <div id="app-container">
    <iframe src="YOUR_VIBECODE_WEB_PREVIEW_URL" 
            style="width:100%; height:100%; border:none;"></iframe>
  </div>

  <div class="subscription-container" id="subscription">
    <h2>Your trial has ended.</h2>
    <!-- Paste your PayPal code here -->
    YOUR_PAYPAL_CODE
  </div>

  <script>
    const trialDays = 30;
    if (!localStorage.getItem('trialStart')) {
      localStorage.setItem('trialStart', Date.now());
    }

    const start = new Date(parseInt(localStorage.getItem('trialStart')));
    const now = new Date();
    const diffDays = Math.floor((now - start) / (1000 * 60 * 60 * 24));

    if (diffDays > trialDays) {
      // Hide the app and show subscription
      document.getElementById('app-container').style.display = 'none';
      document.getElementById('subscription').style.display = 'block';
    }
  </script>

</body>
</html>
