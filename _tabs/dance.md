---
title: Dance
icon: fas fa-music
order: 3
---

<style>
  .dance-video-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1.5rem;
    margin-top: 1.5rem;
  }

  .dance-video-trigger {
    position: relative;
    display: block;
    width: 100%;
    padding: 0;
    border: 0;
    background: transparent;
    cursor: pointer;
  }

  .dance-video-card img {
    width: 100%;
    display: block;
    border-radius: 0.75rem;
  }

  .dance-video-trigger::after {
    content: "\f04b";
    font: var(--fa-font-solid);
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 3.75rem;
    height: 3.75rem;
    display: grid;
    place-items: center;
    border-radius: 999px;
    background: rgba(0, 0, 0, 0.65);
    color: #fff;
    font-size: 1.2rem;
  }

  .dance-video-card p {
    margin: 0.75rem 0 0;
  }

  @media (max-width: 768px) {
    .dance-video-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="dance-video-grid">
  <div class="dance-video-card">
    <button class="dance-video-trigger" type="button" data-video-url="https://www.youtube.com/watch?v=2uGS1ruqipc">
      <img src="https://img.youtube.com/vi/2uGS1ruqipc/hqdefault.jpg" alt="Satanella Pas de Deux at UBC">
    </button>
    <p>Satanella Pas de Deux at UBC</p>
  </div>

  <div class="dance-video-card">
    <button class="dance-video-trigger" type="button" data-video-url="https://www.youtube.com/watch?v=Yv0ex0SMTR0">
      <img src="https://img.youtube.com/vi/Yv0ex0SMTR0/hqdefault.jpg" alt="Practicing some variations">
    </button>
    <p>Practicing some variations</p>
  </div>

  <div class="dance-video-card">
    <button class="dance-video-trigger" type="button" data-video-url="https://www.youtube.com/watch?v=pdTQLushxLI">
      <img src="https://img.youtube.com/vi/pdTQLushxLI/hqdefault.jpg" alt="Contemporary solo for YAGP">
    </button>
    <p>Contemporary solo for YAGP</p>
  </div>

  <div class="dance-video-card">
    <button class="dance-video-trigger" type="button" data-video-url="https://www.youtube.com/watch?v=H8MFB2deUvo">
      <img src="https://img.youtube.com/vi/H8MFB2deUvo/hqdefault.jpg" alt="Variations performed at Helsinki IBC">
    </button>
    <p>Variations performed at Helsinki IBC</p>
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    document.querySelectorAll('.dance-video-trigger').forEach(function(button) {
      button.addEventListener('click', function() {
        const url = button.getAttribute('data-video-url');
        if (url) {
          window.open(url, '_blank', 'noopener,noreferrer');
        }
      });
    });
  });
</script>
