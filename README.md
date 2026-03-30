<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Portfolio + Đèn kéo quân</title>

<style>
* { margin: 0; padding: 0; box-sizing: border-box; }

body {
    font-family: Arial;
    background: #f4f4f4;
}

/* MENU */
nav {
    background: #333;
    padding: 10px;
    text-align: center;
}

nav a {
    color: white;
    margin: 10px;
    text-decoration: none;
    cursor: pointer;
}

/* SECTION */
.page {
    display: none;
    padding: 30px;
}

.active {
    display: block;
}

header {
    text-align: center;
    padding: 40px;
    background: #333;
    color: white;
}

.project {
    background: white;
    padding: 20px;
    margin: 10px 0;
    border-radius: 8px;
}

/* ĐÈN KÉO QUÂN */
.scene {
    width: 300px;
    height: 300px;
    margin: 50px auto;
    perspective: 1000px;
}

.carousel {
    width: 100%;
    height: 100%;
    position: relative;
    transform-style: preserve-3d;
    animation: spin 10s linear infinite;
}

.carousel img {
    position: absolute;
    width: 200px;
    height: 200px;
    left: 50px;
    top: 50px;
    border-radius: 10px;
}

/* 6 mặt */
.img1 { transform: rotateY(0deg) translateZ(250px); }
.img2 { transform: rotateY(60deg) translateZ(250px); }
.img3 { transform: rotateY(120deg) translateZ(250px); }
.img4 { transform: rotateY(180deg) translateZ(250px); }
.img5 { transform: rotateY(240deg) translateZ(250px); }
.img6 { transform: rotateY(300deg) translateZ(250px); }

@keyframes spin {
    from { transform: rotateY(0deg); }
    to { transform: rotateY(360deg); }
}

.paused {
    animation-play-state: paused;
}

img.avatar {
    width: 150px;
    border-radius: 50%;
}
</style>

</head>
<body>

<!-- MENU -->
<nav>
    <a onclick="showPage('home')">Trang chủ</a>
    <a onclick="showPage('about')">Giới thiệu</a>
    <a onclick="showPage('contact')">Liên hệ</a>
    <a onclick="showPage('lantern')">Đèn kéo quân</a>
</nav>

<!-- HOME -->
<div id="home" class="page active">
    <header>
        <h1>Xin chào! Mình là Lê Huỳnh Quốc An</h1>
        <p>Full-stack Developer tương lai</p>
    </header>

    <section>
        <h2>Dự án</h2>
        <div class="project">Todo List</div>
        <div class="project">Weather App</div>
    </section>
</div>

<!-- ABOUT -->
<div id="about" class="page">
    <h1>Giới thiệu</h1>
    <img src="https://th.bing.com/th/id/OIP.xKodv7xekwyyH2RQHNNJGQHaHa?w=179&h=150&c=6&o=7&pid=1.7&rm=3">
    <p>Mình là sinh viên IT</p>
    <p>Đam mê lập trình Web</p>
</div>

<!-- CONTACT -->
<div id="contact" class="page">
    <h1>Liên hệ</h1>
    <p>Email: quocanlehuynh@gmail.com</p>
    <p>Facebook:fb.com/AnLe</p>
</div>

<!-- LANTERN -->
<div id="lantern" class="page">
    <h1 style="text-align:center">Đèn kéo quân</h1>

    <div class="scene">
        <div class="carousel" id="c">
            <img src="https://th.bing.com/th/id/OIP.oR_rmJmIS3PcE90KeR8GYQHaFj?w=246&h=184&c=7&r=0&o=7&pid=1.7&rm=3"class="img1">
            <img src="https://th.bing.com/th/id/OIP.yTARsAdGt6Y44EIke23PGAHaKL?w=135&h=186&c=7&r=0&o=7&pid=1.7&rm=3" class="img2">
            <img src="https://th.bing.com/th?q=Hinh+Cho+%c4%90en+Keo+Quan&w=120&h=120&c=1&rs=1&qlt=70&o=7&cb=1&pid=InlineBlock&rm=3&mkt=en-WW&cc=VN&setlang=en&adlt=moderate&t=1&mw=247" class="img3">
            <img src="https://th.bing.com/th/id/OIP.KlmKxq2yttNkEuqnwhvUbgHaFF?w=217&h=180&c=7&r=0&o=7&pid=1.7&rm=3" class="img4">
            <img src="https://th.bing.com/th/id/OIP.p6CRcmIWhud4S7BJnTVyiwHaLJ?w=124&h=187&c=7&r=0&o=7&pid=1.7&rm=3" class="img5">
            <img src="https://th.bing.com/th/id/OIP.81nJpCzRqOo9AKAdxcsAzwHaEK?w=333&h=187&c=7&r=0&o=7&pid=1.7&rm=3" class="img6">
        </div>
    </div>
</div>

<script>
// CHUYỂN TRANG
function showPage(page) {
    let pages = document.querySelectorAll(".page");
    pages.forEach(p => p.classList.remove("active"));

    document.getElementById(page).classList.add("active");
}

// DỪNG KHI HOVER
let c = document.getElementById("c");

c.addEventListener("mouseenter", () => {
    c.classList.add("paused");
});

c.addEventListener("mouseleave", () => {
    c.classList.remove("paused");
});
</script>

</body>
</html>
