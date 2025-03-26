<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Galery</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }
        .gallery img {
            width: 150px;
            height: 100px;
            cursor: pointer;
            border-radius: 5px;
            transition: transform 0.3s;
        }
        .gallery img:hover {
            transform: scale(1.1);
        }
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            justify-content: center;
            align-items: center;
        }
        .modal img {
            max-width: 90%;
            max-height: 80%;
            border-radius: 10px;
        }
        .close {
            position: absolute;
            top: 20px;
            right: 30px;
            font-size: 30px;
            color: white;
            cursor: pointer;
        }
	body {
   	 background-color: Black; 
	}
    </style>
</head>
<body>

<h2>Galery</h2>
<div class="gallery">
    <img src="14b.jpg" onclick="openModal(this)">
    <img src="15b.jpg" onclick="openModal(this)">
    <img src="20b.jpg" onclick="openModal(this)">
<img src="21c.jpg" onclick="openModal(this)">
<img src="24c.jpg" onclick="openModal(this)">
<img src="25c.jpg" onclick="openModal(this)">
<img src="26c.jpg" onclick="openModal(this)">
<img src="27c.jpg" onclick="openModal(this)">
<img src="31d.jpg" onclick="openModal(this)">
<img src="32d.jpg" onclick="openModal(this)">
<img src="157i.jpg" onclick="openModal(this)">
<img src="158i.jpg" onclick="openModal(this)">
<img src="162j.jpg" onclick="openModal(this)">
<img src="166j.jpg" onclick="openModal(this)">
<img src="168j.jpg" onclick="openModal(this)">
<img src="169j.jpg" onclick="openModal(this)">
<img src="170j.jpg" onclick="openModal(this)">
<img src="171k.jpg" onclick="openModal(this)">
<img src="172k.jpg" onclick="openModal(this)">
<img src="173k.jpg" onclick="openModal(this)">
<img src="174k.jpg" onclick="openModal(this)">
<img src="175k.jpg" onclick="openModal(this)">
<img src="189l.jpg" onclick="openModal(this)">
<img src="190l.jpg" onclick="openModal(this)">
<img src="191m.jpg" onclick="openModal(this)">
<img src="195m.jpg" onclick="openModal(this)">
<img src="196m.jpg" onclick="openModal(this)">
<img src="201n.jpg" onclick="openModal(this)">
<img src="202n.jpg" onclick="openModal(this)">
<img src="203n.jpg" onclick="openModal(this)">
</div>

<div class="modal" id="modal">
    <span class="close" onclick="closeModal()">&times;</span>
    <img id="modal-img">
</div>


<script>
    document.addEventListener("DOMContentLoaded", function () {
        let images = document.querySelectorAll(".gallery img");
        let modalImg = document.getElementById("modal-img");
        let modal = document.getElementById("modal");
        let currentIndex = 0;

        function openModal(img) {
            modal.style.display = "flex";
            modalImg.src = img.src;
            currentIndex = [...images].indexOf(img);
        }

        function closeModal() {
            modal.style.display = "none";
        }

        function changeImage(direction) {
            currentIndex += direction;
            if (currentIndex < 0) currentIndex = images.length - 1;
            if (currentIndex >= images.length) currentIndex = 0;
            modalImg.src = images[currentIndex].src;
        }

        images.forEach(img => {
            img.addEventListener("click", function () {
                openModal(this);
            });
        });

        document.addEventListener("keydown", function (event) {
            if (event.key === "ArrowRight") {
                changeImage(1);
            } else if (event.key === "ArrowLeft") {
                changeImage(-1);
            } else if (event.key === "Escape") {
                closeModal();
            }
        });

        document.querySelector(".close").addEventListener("click", closeModal);
    });

</script>

</body> 
</html>
