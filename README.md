# Image-gallery
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Image Gallery</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f0f0;
      margin: 0;
      padding: 20px;
      display: flex;
      justify-content: center;
    }

    .gallery-container {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      text-align: center;
      max-width: 600px;
    }

    .gallery-container img {
      max-width: 100%;
      height: auto;
      border-radius: 10px;
    }

    .buttons {
      margin-top: 15px;
    }

    .buttons button {
      padding: 10px 15px;
      margin: 0 5px;
      border: none;
      border-radius: 5px;
      background-color: #3498db;
      color: white;
      cursor: pointer;
    }

    .buttons button:hover {
      background-color: #2980b9;
    }
  </style>
</head>
<body>
  <div class="gallery-container">
    <img id="galleryImage" src="https://via.placeholder.com/600x400?text=Image+1" alt="Gallery Image">
    <div class="buttons">
      <button onclick="prevImage()">Previous</button>
      <button onclick="nextImage()">Next</button>
    </div>
  </div>

  <script>
    const images = [
      "https://via.placeholder.com/600x400?text=Image+1",
      "https://via.placeholder.com/600x400?text=Image+2",
      "https://via.placeholder.com/600x400?text=Image+3"
    ];

    let currentIndex = 0;

    function updateImage() {
      document.getElementById("galleryImage").src = images[currentIndex];
    }

    function prevImage() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      updateImage();
    }

    function nextImage() {
      currentIndex = (currentIndex + 1) % images.length;
      updateImage();
    }
  </script>
</body>
</html>
