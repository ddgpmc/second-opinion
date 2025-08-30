<template>
  <header class="site-header">
    <div class="site-header-inner">
      <!-- Desktop Logo -->
      <div class="logo-ribbon desktop-logo">
        <img class="main-logo" src="/src/assets/logo.webp" alt="All-on-Four Dental Implant Center" />
      </div>

      <!-- Mobile Logo -->
      <div class="mobile-logo">
        <img src="/src/assets/logo-mobile.webp" alt="All-on-Four Dental Implant Center" />
      </div>

      <!-- Desktop Right Side -->
      <div class="header-right desktop-content">
        <div class="locations">
          <span class="location-dot">Westchester</span>
          <span class="location-dot">Manhattan</span>
          <span class="location-dot">Long Island</span>
          <span class="location-dot">New Jersey</span>
        </div>

        <div class="contact-info">
          <div class="urgent-call">
            <i class="fas fa-phone-alt"></i>
            <span>Got an urgent implant question? <br> Call us now - se habla español</span>
          </div>
          <a href="tel:8776964738" class="phone-number">(877) 696-4738</a>
        </div>
      </div>
    </div>
  </header>
</template>


<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'SiteHeader'
})
</script>

<style scoped>
.site-header {
    background: white;
    padding: 10px 0;
    position: relative;
}

.site-header-inner {
    max-width: 1350px;
    margin: 0 auto;
    padding: 0 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
    z-index: 2;
}
.mobile-logo {
  display: none;
  width: 100%;
  text-align: center;
}

.mobile-logo img {
  width: 80%; /* horizontal logo takes most of header width */
  height: auto;
}
/* Ribbon with folded edges */
.logo-ribbon {
    font-size: 50px;
    font-weight: bold;
    margin-top: -17%;
    margin-left: 5rem;
    margin-bottom: -15%;
    color: #fff;
    --r: .5em;
    /* control the cutout */

    border-inline: .5em solid #0000;
    padding: .5em .2em calc(var(--r) + .2em);
    clip-path: polygon(0 0,
            100% 0,
            100% 100%,
            calc(100% - .5em) 100%,
            50% calc(105% - var(--r)),
            .5em 100%,
            0 100%);
    background:
        radial-gradient(50% .2em at top, #000a, #0000) border-box,
        #0148a5 padding-box;
    /* the color */
    width: fit-content;
}

.main-logo {
    height: 70px;
    margin-top: 50px;
    width: auto;
    display:flex;
}

.urgent-call {
  display: flex;
  align-items: center;
  gap: 10px; /* space between icon and text */
  font-size: 16px;
  font-weight: 600;
  color: #000;
  margin-top: 5px;
}

.urgent-call i {
  color: #0077d9;  /* blue phone icon */
  font-size: 25px;
  rotate: 90deg;
}


/* Right side header */
.header-right {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  color: #003366;
}

.locations {
    display: flex;
    gap: 16px;
    align-items: center;
}

.location-dot {
    position: relative;
    font-size: 0.9rem;
    font-weight: 500;
    color: rgb(0, 0, 0);
    padding-left: 20px; /* leave space for icon */
}

.location-dot::before {
    content: '';
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 16px; /* adjust size to your icon */
    height: 16px;
    background-image: url('/src/assets/download.png');
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
}


.contact-info {
    text-align: right;
}

.urgent-text {
    display: block;
    font-size: 0.85rem;
    color: black;
    margin-bottom: 2px;
}

.phone-section {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
}

.call-text {
    font-size: 0.8rem;
    color: black;
    margin-bottom: 2px;
}

.phone-number {
    font-size: 16px;
    font-weight: 700;
    color: rgb(10, 10, 150);
    text-decoration: none;
    letter-spacing: 0.5px;
}

.phone-number:hover {
    text-decoration: underline;
}

/* Responsive tweaks */
@media (max-width: 1024px) {
    .logo-ribbon {
        margin-top: -40px;
        margin-bottom: -25%;
        align-self: self-start;
        font-size: 50px;
    }
    .locations {
        gap: 12px;
        margin-top: 20px;
    }

    .location-dot {
        font-size: 0.8rem;
    }

    .header-right {
        gap: 16px;
    }
}

@media (max-width: 768px) {
    .site-header-inner {
        flex-direction: column;
        gap: 16px;
        text-align: center;
    }

    .header-right {
        flex-direction: column;
        gap: 12px;
        width: 100%;
    }

    .locations {
        justify-content: center;
        flex-wrap: wrap;
    }

    .contact-info {
        text-align: center;
    }

    .phone-section {
        align-items: center;
    }
    .desktop-logo,
  .desktop-content {
    display: none;
  }

  .mobile-logo {
    display: block;
  }

  .site-header {
    padding: 10px 0;
  }

  .site-header-inner {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}

@media (max-width: 480px) {
    .locations {
        gap: 8px;
    }

    .location-dot {
        font-size: 0.75rem;
        padding-left: 10px;
    }

    .phone-number {
        font-size: 1.2rem;
    }
}
</style>
