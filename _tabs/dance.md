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

  .dance-video-card img {
    width: 100%;
    display: block;
    border-radius: 0.75rem;
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
    <a href="https://youtu.be/2uGS1ruqipc" target="_blank" rel="noopener noreferrer">
      <img src="https://img.youtube.com/vi/2uGS1ruqipc/hqdefault.jpg" alt="Satanella Pas de Deux at UBC">
    </a>
    <p>Satanella Pas de Deux at UBC</p>
  </div>

  <div class="dance-video-card">
    <a href="https://youtu.be/Yv0ex0SMTR0" target="_blank" rel="noopener noreferrer">
      <img src="https://img.youtube.com/vi/Yv0ex0SMTR0/hqdefault.jpg" alt="Practicing some variations">
    </a>
    <p>Practicing some variations</p>
  </div>

  <div class="dance-video-card">
    <a href="https://youtu.be/pdTQLushxLI" target="_blank" rel="noopener noreferrer">
      <img src="https://img.youtube.com/vi/pdTQLushxLI/hqdefault.jpg" alt="Contemporary solo for YAGP">
    </a>
    <p>Contemporary solo for YAGP</p>
  </div>

  <div class="dance-video-card">
    <a href="https://youtu.be/H8MFB2deUvo" target="_blank" rel="noopener noreferrer">
      <img src="https://img.youtube.com/vi/H8MFB2deUvo/hqdefault.jpg" alt="Variations performed at Helsinki IBC">
    </a>
    <p>Variations performed at Helsinki IBC</p>
  </div>
</div>
