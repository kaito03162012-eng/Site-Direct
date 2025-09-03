<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>My Browser</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
    }
    input {
      width: 300px;
      padding: 8px;
    }
    button {
      padding: 8px 12px;
      margin-left: 10px;
      cursor: pointer;
    }
    iframe {
      margin-top: 20px;
      width: 90%;
      height: 600px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>
  <h1>My Browser</h1>
  <input type="text" id="urlInput" placeholder="サイトのURLを入力してね">
  <button onclick="openSite()">開く</button>

  <div id="frameContainer"></div>

  <script>
    function openSite() {
      let url = document.getElementById("urlInput").value;

      // 入力が "http://" や "https://" で始まってなかったら付ける
      if (!url.startsWith("http://") && !url.startsWith("https://")) {
        url = "https://" + url;
      }

      // iframe にサイトを表示
      document.getElementById("frameContainer").innerHTML =
        `<iframe src="${url}"></iframe>`;
    }
  </script>
</body>
</html>
