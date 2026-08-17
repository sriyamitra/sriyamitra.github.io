---
layout: about
title: about
permalink: /

subtitle: MSBA Student at UC Davis Graduate School of Management

profile:
  align: right
  image: sriya_photo.jpg
  image_circular: false # crops the image to make it circular
  more_info: >

selected_papers: false # set to true when you add papers marked as "selected={true}" to _bibliography/papers.bib
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # set to true to include news announcements from _news/
  scrollable: true
  limit: 5

latest_posts:
  enabled: false # set to true to include blog posts from _posts/
  scrollable: true
  limit: 3
---

I am an MSBA (Master of Science in Business Analytics) student at **UC Davis** with an engineering and business foundation and **4 years of experience** in consulting and marketing automation. My work spans product strategy, data analytics, and cross-functional collaboration.


<div class="hero__companies">
  <div class="hero__companies-logos">
    <img src="{{ 'https://1000logos.net/wp-content/uploads/2024/01/UC-Davis-logo.png' | relative_url }}" alt="UC Davis" class="company-logo" style="height: 60px;">
    <img src="{{ '/assets/img/companies/AccentureLogo.svg' | relative_url }}" alt="Accenture" class="company-logo" style="height: 26px; position: relative; top: -6px;">
    <img src="{{ '/assets/img/companies/EYLogo.svg' | relative_url }}" alt="EY" class="company-logo" style="height: 30px; position: relative; top: -7px;">
    <img src="{{ 'https://symhealth.siu.edu.in/assets/SIUDeemedUniversity151.png' | relative_url }}" alt="EY" class="company-logo" style="height: 30px;">
    <img src="{{ 'https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Tata_Consultancy_Services_old_logo.svg/1280px-Tata_Consultancy_Services_old_logo.svg.png?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=thumbnail' | relative_url }}" alt="TCS" class="company-logo" style="height: 36px;">
  </div>
</div>

<!-- PLACEHOLDER_SECTION: You can add an Experience or Education timeline here, or link to your CV in _pages/cv.md -->

<!-- Asciify Interactive Component for Profile Photo -->
<style>
  .profile {
    position: relative;
    user-select: none;
  }
  .asciify-wrapper {
    position: relative;
    display: inline-block;
    overflow: hidden;
    border-radius: 6px;
    cursor: crosshair;
  }
  .asciify-canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 10;
    border-radius: 6px;
  }
</style>

<script>
window.addEventListener('DOMContentLoaded', () => {
  const profileImg = document.querySelector('.profile img');
  if (!profileImg) return;

  // Wrap image and attach canvas
  const wrapper = document.createElement('div');
  wrapper.className = 'asciify-wrapper';
  profileImg.parentNode.insertBefore(wrapper, profileImg);
  wrapper.appendChild(profileImg);

  const canvas = document.createElement('canvas');
  canvas.className = 'asciify-canvas';
  wrapper.appendChild(canvas);

  let mouseX = -1000;
  let mouseY = -1000;
  let isHovered = false;

  const charRamp = "@%#*+=-:. ";
  const cellSize = 8;

  function drawAsciify() {
    const width = profileImg.clientWidth;
    const height = profileImg.clientHeight;
    if (!width || !height) return;

    canvas.width = width;
    canvas.height = height;
    const ctx = canvas.getContext('2d');

    // Create offscreen sampling canvas
    const sampleCanvas = document.createElement('canvas');
    sampleCanvas.width = width;
    sampleCanvas.height = height;
    const sCtx = sampleCanvas.getContext('2d');
    sCtx.drawImage(profileImg, 0, 0, width, height);
    const imgData = sCtx.getImageData(0, 0, width, height).data;

    ctx.clearRect(0, 0, width, height);

    if (!isHovered) return;

    ctx.font = 'bold 8px monospace';
    ctx.textBaseline = 'middle';
    ctx.textAlign = 'center';

    const radius = Math.round(height * 0.4);
    const softEdge = radius; // softness = 1.0

    for (let y = cellSize / 2; y < height; y += cellSize) {
      for (let x = cellSize / 2; x < width; x += cellSize) {
        const dx = x - mouseX;
        const dy = y - mouseY;
        const dist = Math.sqrt(dx * dx + dy * dy);
        if (dist > radius + softEdge) continue;

        let alpha = 1;
        if (dist > radius) {
          alpha = Math.max(0, 1 - (dist - radius) / softEdge);
        }

        const idx = (Math.floor(y) * width + Math.floor(x)) * 4;
        const r = imgData[idx];
        const g = imgData[idx + 1];
        const b = imgData[idx + 2];

        const lum = (0.299 * r + 0.587 * g + 0.114 * b) / 255;
        const charIndex = Math.min(charRamp.length - 1, Math.floor(lum * charRamp.length));
        const char = charRamp[charIndex];

        // Draw soft circular lens background
        ctx.fillStyle = `rgba(255,255,255,${0.9 * alpha})`;
        ctx.fillRect(x - cellSize / 2, y - cellSize / 2, cellSize, cellSize);

        ctx.fillStyle = `rgba(${r}, ${g}, ${b}, ${alpha})`;
        ctx.fillText(char, x, y);
      }
    }
  }

  wrapper.addEventListener('mousemove', (e) => {
    const rect = wrapper.getBoundingClientRect();
    mouseX = e.clientX - rect.left;
    mouseY = e.clientY - rect.top;
    isHovered = true;
    drawAsciify();
  });

  wrapper.addEventListener('mouseleave', () => {
    isHovered = false;
    drawAsciify();
  });

  if (profileImg.complete) {
    drawAsciify();
  } else {
    profileImg.addEventListener('load', drawAsciify);
  }
});
</script>
