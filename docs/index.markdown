---
layout: home
---

<style>
.intro-section {
  display: flex;
  gap: 30px;
  align-items: flex-start;
  margin-bottom: 30px;
}

.carousel-column {
  flex: 0 0 260px;
}

.bio-column {
  flex: 1;
}

.photo-carousel {
  position: relative;
  width: 260px;
  text-align: center;
}

.carousel-slide {
  display: none;
}

.carousel-slide.active {
  display: block;
}

.carousel-slide img {
  width: 260px;
  height: 320px;
  object-fit: cover;
  border-radius: 6px;
}

.carousel-caption {
  margin-top: 7px;
  font-size: 0.8em;
  color: #666;
}

.carousel-prev,
.carousel-next {
  position: absolute;
  top: 145px;
  transform: translateY(-50%);
  background: rgba(255, 255, 255, 0.75);
  border: none;
  font-size: 24px;
  padding: 5px 9px;
  cursor: pointer;
  border-radius: 3px;
}

.carousel-prev {
  left: 5px;
}

.carousel-next {
  right: 5px;
}

.carousel-dots {
  margin-top: 8px;
}

.carousel-dot {
  height: 7px;
  width: 7px;
  margin: 0 3px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  cursor: pointer;
}

.carousel-dot.active {
  background-color: #555;
}

/* Stack carousel above text on smaller screens */
@media (max-width: 600px) {
  .intro-section {
    display: block;
  }

  .carousel-column {
    margin: 0 auto 25px auto;
    width: 260px;
  }
}
</style>


<div class="intro-section">

  <div class="carousel-column">

    <div class="photo-carousel">

      <div class="carousel-slide active">
        <img src="{{ '/files/marthawebsite.jpg' | relative_url }}" alt="Photo 1">
        <div class="carousel-caption">We love the Viaflo</div>
      </div>

      <div class="carousel-slide">
        <img src="{{ '/files/photo2.jpg' | relative_url }}" alt="Photo 2">
        <div class="carousel-caption">Cool gene-edited bugs I got to work with at the Akbari Lab</div>
      </div>

      <div class="carousel-slide">
        <img src="{{ '/files/photo3.jpg' | relative_url }}" alt="Photo 3">
        <div class="carousel-caption">Caption for photo 3</div>
      </div>

      <div class="carousel-slide">
        <img src="{{ '/files/photo4.jpg' | relative_url }}" alt="Photo 4">
        <div class="carousel-caption">Caption for photo 4</div>
      </div>

      <div class="carousel-slide">
        <img src="{{ '/files/photo5.jpg' | relative_url }}" alt="Photo 5">
        <div class="carousel-caption">Caption for photo 5</div>
      </div>

      <button class="carousel-prev" onclick="changeSlide(-1)">&#10094;</button>
      <button class="carousel-next" onclick="changeSlide(1)">&#10095;</button>

      <div class="carousel-dots">
        <span class="carousel-dot active" onclick="showSlide(0)"></span>
        <span class="carousel-dot" onclick="showSlide(1)"></span>
        <span class="carousel-dot" onclick="showSlide(2)"></span>
        <span class="carousel-dot" onclick="showSlide(3)"></span>
        <span class="carousel-dot" onclick="showSlide(4)"></span>
      </div>

    </div>

  </div>


  <div class="bio-column">

    <p>
      I am a first-year Civil and Environmental PhD student at MIT, working on bio-fabricated materials for preservation. I am a
      <a href="https://croucher.org.hk/en/fellows-and-scholars/martha-chow">Croucher Scholar</a>,
      advised by
      <a href="https://marelli.mit.edu/">Prof. Benedetto Marelli</a>.
    </p>

    <p>
      I grew up in Hong Kong and received my B.S. in Cell and Molecular Biology from the University of California, San Diego.
      Before MIT, I trained under the supervision of Dr. Keith Joung at Arena Bioworks, and Prof. Michael Springer at Harvard Medical School.
    </p>

  </div>

</div>


# Research

1. [Eliminating malaria vectors with precision-guided sterile males.](https://www.pnas.org/doi/10.1073/pnas.2312456121) (2nd co-author). <em>Proceedings of the National Academy of Sciences.</em> June 25, 2024.

2. [A natural non-synonymous single nucleotide polymorphism in GmbHLH113 negates its inhibitory effect on root hair elongation in soybean.](https://onlinelibrary.wiley.com/share/C2TBCFJKKCA7VTYUXA8I?target=10.1111/tpj.16258) <em>The Plant Journal.</em> April 24, 2023.


<script>
let currentSlide = 0;

function showSlide(index) {
  const slides = document.querySelectorAll(".carousel-slide");
  const dots = document.querySelectorAll(".carousel-dot");

  if (index >= slides.length) {
    currentSlide = 0;
  } else if (index < 0) {
    currentSlide = slides.length - 1;
  } else {
    currentSlide = index;
  }

  slides.forEach(slide => slide.classList.remove("active"));
  dots.forEach(dot => dot.classList.remove("active"));

  slides[currentSlide].classList.add("active");
  dots[currentSlide].classList.add("active");
}

function changeSlide(direction) {
  showSlide(currentSlide + direction);
}
</script>
