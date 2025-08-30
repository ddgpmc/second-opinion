    <template>
        <section class="hero">
            <!-- Desktop background -->
            <div class="hero-bg desktop" :style="`background-image: url(${bgUrl})`"></div>
            <div class="hero-overlay desktop"></div>

            <!-- Mobile/Tablet top image -->
            <div class="hero-mobile">
                <img src="/src/assets/mobile-image.jpg" alt="hero mobile" class="mobile-img" />
            </div>

            <div class="hero-inner container">
                <!-- Left Content -->
                <div class="hero-left">
                    <small class="eyebrow">Not Sure About Your Implant Quote?</small>
                    <h1 class="headline">Get a Trusted Second Opinion Free.</h1>

                    <!-- Mobile form (shown only on mobile/tablet) -->
                    <aside class="form-wrapper mobile-form" ref="formBlockMobile">

                        <div class="hero-form">
                            <div class="form-header">
                                <h2 class="form-title">Get Your Free Second Opinion Today</h2>
                                <p class="form-desc">Upload your treatment quote for a free second opinion.</p>
                                <p class="form-sub">We'll review your plan using modern techniques — no pressure, just
                                    clarity.</p>
                            </div>
                            <form class="form" @submit.prevent="onSubmit">
                                <div class="field-row">
                                    <label class="field">
                                        <span class="label">Full name</span>
                                        <input v-model="form.name" type="text" required autocomplete="name" />
                                    </label>
                                    <label class="field">
                                        <span class="label">Phone</span>
                                        <input ref="phoneInputMobile" type="tel" placeholder="Enter phone number" />
                                    </label>
                                </div>

                                <div class="field-row">
                                    <label class="field">
                                        <span class="label">Email</span>
                                        <input v-model="form.email" type="email" required autocomplete="email" />
                                    </label>
                                    <label class="field">
                                        <span class="label">Best time to call</span>
                                        <div class="time-picker">
                                            <select v-model="form.bestTimeHour">
                                                <option disabled value="">Hour</option>
                                                <option v-for="h in 12" :key="h" :value="h">{{ h }}</option>
                                            </select>
                                            :
                                            <select v-model="form.bestTimeMinute">
                                                <option disabled value="">Minute</option>
                                                <option v-for="m in 60" :key="m" :value="m">
                                                    {{ m < 10 ? '0' + m : m }} </option>
                                            </select>
                                            <select v-model="form.bestTimeAmPm">
                                                <option value="AM">AM</option>
                                                <option value="PM">PM</option>
                                            </select>
                                        </div>
                                    </label>

                                </div>

                                <label class="field">
                                    <span class="label">Have a written quote?</span>
                                    <select v-model="form.hasQuote" required>
                                        <option value="">Choose an option</option>
                                        <option value="yes">Yes</option>
                                        <option value="no">No</option>
                                    </select>
                                </label>
                                <button class="submit" type="submit">Send my free second opinion</button>
                            </form>
                        </div>
                    </aside>

                    <!-- Normal content -->
                    <p class="sub">
                        Bring your quote and speak with New York's top full-mouth implant team.
                        Over 25 years of experience, same-day teeth, minimally invasive treatment,
                        and a price-match guarantee on any comparable plan.
                    </p>
                    <h2 class="why-title">Why Patients Choose Us:</h2>
                    <ul class="bullets">
                        <li><span>25+ years</span> of full-mouth implant expertise</li>
                        <li><span>Same-day tooth replacement.</span> Walk out smiling</li>
                        <li><span>Minimally invasive care</span> backed by advanced technology</li>
                        <li><span>Unmatched quality</span> at a better price</li>
                        <li><span>Flexible monthly payments*</span> starting from $299 per arch or $597 full mouth</li>
                    </ul>
                    <p class="note">
                        Financing available upon approved credit. Terms and conditions apply.
                    </p>
                    <div class="form-top-logos-mobile">
                        <img src="/src/assets/logos.webp" alt="logos" />
                    </div>
                    <!-- CTA Cards -->
                    <div class="cta-cards">
                        <div class="cta-card" @click="scrollToForm">
                            <i class="fas fa-dollar-sign cta-icon"></i>
                            <div class="cta-content">
                                <h3 class="cta-title">Bring your Quote</h3>
                                <p class="cta-desc">We’ll beat your quote without compromising quality.​</p>
                            </div>
                        </div>
                        <div class="cta-card" @click="scrollToForm">
                            <i class="fas fa-phone cta-icon"></i>
                            <div class="cta-content">
                                <h3 class="cta-title">Talk to us</h3>
                                <p class="cta-desc">Call or chat for help with pricing or treatment options.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Desktop sidebar form -->
                <aside class="form-wrapper desktop-form" ref="formBlock">
                    <div class="form-top-logos">
                        <img src="/src/assets/logos.webp" alt="logos" />
                    </div>
                    <div class="hero-form">
                        <div class="form-header">
                            <h2 class="form-title">Get Your Free Second Opinion Today</h2>
                            <p class="form-desc">Upload your treatment quote for a free second opinion.</p>
                            <p class="form-sub">We'll review your plan using modern techniques — no pressure, just
                                clarity.
                            </p>
                        </div>
                        <form class="form" @submit.prevent="onSubmit">
                            <div class="field-row">
                                <label class="field">
                                    <span class="label">Full name</span>
                                    <input v-model="form.name" type="text" required autocomplete="name" />
                                </label>
                                <label class="field">
                                    <span class="label">Phone</span>
                                    <input ref="phoneInputDesktop" type="tel" placeholder="Enter phone number" />
                                </label>
                            </div>

                            <div class="field-row">
                                <label class="field">
                                    <span class="label">Email</span>
                                    <input v-model="form.email" type="email" required autocomplete="email" />
                                </label>
                                <label class="field">
                                    <span class="label">Best time to call</span>
                                    <div class="time-picker">
                                        <select v-model="form.bestTimeHour">
                                            <option disabled value="">Hour</option>
                                            <option v-for="h in 12" :key="h" :value="h">{{ h }}</option>
                                        </select>
                                        <span>:</span>
                                        <select v-model="form.bestTimeMinute">
                                            <option disabled value="">Minute</option>
                                            <option v-for="m in 60" :key="m" :value="m">{{ m < 10 ? '0' + m : m
                                                    }}</option>
                                        </select>
                                        <select v-model="form.bestTimeAmPm">
                                            <option value="AM">AM</option>
                                            <option value="PM">PM</option>
                                        </select>
                                    </div>
                                </label>

                            </div>

                            <label class="field">
                                <span class="label">Have a written quote?</span>
                                <select v-model="form.hasQuote" required>
                                    <option value="">Choose an option</option>
                                    <option value="yes">Yes</option>
                                    <option value="no">No</option>
                                </select>
                            </label>
                            <button class="submit" type="submit">Send my free second opinion</button>
                        </form>
                    </div>
                </aside>
            </div>
        </section>
    </template>

<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue';
import 'intl-tel-input/build/css/intlTelInput.css';
import headerBg from '../assets/header-bg.webp';
import intlTelInput from 'intl-tel-input';
import '../assets/css/hero.css';

export default defineComponent({
    name: 'Hero',
    setup() {
        const bgUrl = headerBg;
        const form = ref({
            name: '', email: '', phone: '', bestTime: '', hasQuote: '', bestTimeHour: '',
            bestTimeMinute: '',
            bestTimeAmPm: '',
        });
        const formBlock = ref<HTMLElement | null>(null);
        const phoneInputMobile = ref<HTMLInputElement | null>(null);
        const phoneInputDesktop = ref<HTMLInputElement | null>(null);
        const itiMobile = ref<any>(null);
        const itiDesktop = ref<any>(null);

        onMounted(() => {
            if (phoneInputMobile.value) {
                itiMobile.value = intlTelInput(phoneInputMobile.value, {
                    initialCountry: 'us',
                    separateDialCode: false,
                    utilsScript: 'https://cdnjs.cloudflare.com/ajax/libs/intl-tel-input/17.0.19/js/utils.js',
                    nationalMode: true,
                    autoHideDialCode: true
                } as any);
            }
            if (phoneInputDesktop.value) {
                itiDesktop.value = intlTelInput(phoneInputDesktop.value, {
                    initialCountry: 'us',
                    separateDialCode: true,
                    utilsScript: 'https://cdnjs.cloudflare.com/ajax/libs/intl-tel-input/17.0.19/js/utils.js'
                } as any);
            }
        });

        function onSubmit() {
            if (itiMobile.value && phoneInputMobile.value?.offsetParent !== null) {
                form.value.phone = itiMobile.value.getNumber();
            } else if (itiDesktop.value && phoneInputDesktop.value?.offsetParent !== null) {
                form.value.phone = itiDesktop.value.getNumber();
            }

            fetch('https://eo21rwdrgep7m0l.m.pipedream.net', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(form.value)
            })
                .then(() => {
                    alert('Form submitted successfully!');
                    form.value = {
                        name: '', email: '', phone: '', bestTime: '', hasQuote: '', bestTimeHour: '',
                        bestTimeMinute: '',
                        bestTimeAmPm: ''
                    };
                })
                .catch((error) => {
                    console.error('Error submitting form:', error);
                    alert('Something went wrong. Please try again.');
                });
        }

        function scrollToForm() {
            formBlock.value?.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }

        return { bgUrl, form, onSubmit, formBlock, scrollToForm, phoneInputMobile, phoneInputDesktop };
    }
});
</script>



<style scoped>
.hero {
    position: relative;
    min-height: 72vh;
    display: flex;
    flex-direction: column;
    align-items: center;
}

/* Desktop BG */
.hero-bg.desktop {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: right right;
    z-index: 0;
    filter: saturate(1.1) contrast(1);
}

.hero-overlay.desktop {
    position: absolute;
    inset: 0;
    z-index: 1;
    background: linear-gradient(90deg,
            #0660d4 0%,
            #5e93d8 35%,
            rgba(3, 53, 102, 0.15) 65%,
            rgba(218, 211, 211, 0) 85%);
}
/* Mobile/Tablet hero image */
.hero-mobile {
    display: none;
    position: relative;
    width: 50%;
    margin-top: 60px;
}

.mobile-img {
    width: 100%;
    display: block;
    margin-top: 50px;
}

/* Layout */
.container {
    width: 100%;
    max-width: 950px;
    margin: 0 auto;
    margin-left: 3%;
    padding: 30px 10px;
    z-index: 2;
    display: grid;
    grid-template-columns: 1fr 400px;
    gap: 22px;
    justify-content: start;
    align-items: center;
    position: relative;
}

.hero-left {
    color: white;
    align-self: center;
}

/* Content text styles */
.eyebrow {
    color: rgba(255, 255, 255, 0.9);
    font-weight: 600;
    letter-spacing: 0.6px;
}

.headline {
    font-size: clamp(1.6rem, 3vw, 2.6rem);
    margin: 12px 0 16px;
    line-height: 1.05;
}

.form-top-logos-mobile {
    display: none;
}

.sub {
    margin-bottom: 18px;
    opacity: 0.95;
}

.bullets {
    list-style: none;
    padding: 0;
    margin: 0 0 4px;
    display: grid;
    gap: 3px;
}

.bullets li::before {
    content: '✓';
    margin-right: 8px;
    color: #ffd;
}

.bullets li span {
    font-weight: 700;
}

.why-title {
    margin-top: 20px;
    font-size: 1.2rem;
    font-weight: 700;
}

.note {
    margin-top: 10px;
    font-size: 0.9rem;
    opacity: 0.85;
}

/* CTA Cards */
.cta-cards {
    display: flex;
    gap: 5px;
    margin-top: 10px;
}

.cta-card {
    flex: 1;
    display: flex;
    align-items: flex-start;
    background: #fff;
    color: #074c7f;
    padding: 5px;
    border-radius: 12px;
    cursor: pointer;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.cta-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.15);
}

.cta-icon {
    font-size: 2rem;
    margin-right: 12px;
    padding: 5px;
    align-self: center;
    color: #0148a5;
}

.time-picker {
    display: flex;
    align-items: center;
    gap: 8px;
}

.time-picker select {
    padding: 8px;
    border-radius: 4px;
    border: 1px solid #ccc;
    font-size: 1rem;
}

.cta-title {
    font-size: 1.1rem;
    font-weight: 600;
    margin-bottom: 4px;
}

.cta-desc {
    font-size: 0.9rem;
    color: #444;
    line-height: 1.3;
}

/* Form */
.hero-form {
    background: #fff;
    border-radius: 12px;
    padding: 18px;
    justify-self: center;
    color: black;
    align-self: start;
    box-shadow: 0 8px 30px rgba(2, 10, 24, 0.6);
}

.form-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.form-top-logos {
    margin-bottom: 20px;
    width: 100%;
    background-color: white;
}

.form-top-logos img {
    width: 350px;
    display: block;
    margin: 0 auto;
}

.form {
    display: grid;
    gap: 12px;
}

.form-title {
    font-size: 1.3rem;
    text-align: center;
}

.form-desc,
.form-sub {
    font-size: 14px;
    text-align: center;
}

.form-sub {
    font-weight: 700;
}

.field {
    display: block;
}

.field-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
}

.label {
    display: block;
    margin-bottom: 6px;
    font-size: 0.85rem;
    color: rgba(0, 0, 0, 0.9);
}

input,
select {
    width: 100%;
    padding: 10px 12px;
    border-radius: 8px;
    border: 1px solid rgba(0, 0, 0, 0.3);
    background: rgba(255, 255, 255, 0.1);
    color: rgb(0, 0, 0);
}

input::placeholder {
    color: rgba(0, 0, 0, 0.5);
}

.submit {
    margin-top: 6px;
    padding: 12px;
    border-radius: 8px;
    border: 0;
    background: #0077d9;
    color: white;
    font-weight: 700;
    cursor: pointer;
}
.iti input,
.iti__tel-input,
.iti input[type="tel"],
input[type="tel"],
.field input[type="tel"] {
    border: 2px solid blue !important;
    width: 200px !important;
    box-sizing: border-box !important;
}

/* Also target the container */
/* Target intl-tel-input wrapper */
.iti {
    width: 100% !important;
}

.iti input {
    width: 100% !important;
    box-sizing: border-box; /* makes padding included in width */
}
.field {
    width: 100%;
    display: block;
}

/* Alternative: Target by attribute */
input[placeholder="Enter phone number"] {
    border: 2px solid purple !important;
    width: 500px !important;
}

/* Target by ref name if needed */
.field input[ref="phoneInputMobile"],
.field input[ref="phoneInputDesktop"] {
    border: 2px solid orange !important;
    width: 500px !important;
}
/* Responsive */

/* Mobile + Tablet (up to 900px) */
@media (max-width: 900px) {
    .hero {
        background: linear-gradient(to bottom, #0660d4, #5e93d8);
        text-align: center;
        /* Center text */
        justify-items: center;
        padding: 30px;
    }

.iti input,
.iti__tel-input,
.iti input[type="tel"],
input[type="tel"],
.field input[type="tel"] {
    border: 2px solid blue !important;
    width: 200px !important;
    box-sizing: border-box !important;
}
.iti {
    width: 500px !important;
    border: 2px solid green !important;
}

/* Alternative: Target by attribute */
input[placeholder="Enter phone number"] {
    border: 2px solid purple !important;
    width: 500px !important;
}

/* Target by ref name if needed */
.field input[ref="phoneInputMobile"],
.field input[ref="phoneInputDesktop"] {
    border: 2px solid orange !important;
    width: 200px !important;
}
    .hero-mobile {
        display: block;
        margin: 0 auto 15 auto;
    }

    .hero-bg.desktop,
    .hero-overlay.desktop {
        display: none;
    }

    .form-top-logos-mobile {
        display: block;
        margin-top: 15px;
    }
.form-top-logos-mobile img {
    width: 80%;      /* scale down for smaller screens */
    max-width: 300px; /* optional cap */
    display: block;
    margin: 0 auto;
}
    .desktop-form {
        display: none;
    }

    .form-wrapper.mobile-form .form-top-logos-mobile {
        order: 4;
        /* move below other content */
    }

    .note {
        order: 1;
        /* keep the financing note above the logos */
        margin-top: 15px;
    }

    .hero-form {
        order: 0;
        /* form stays above the logos */
    }

    /* Show only mobile form */
    .desktop-form {
        display: none;
    }

    .form-wrapper {
        justify-self: center;
    }

    .container {
        display: flex;
        flex-direction: column;
        padding: 0 15px;
        margin: 0 auto;
        max-width: 100%;
        justify-content: center;
        align-items: center;
        gap: 20px;
    }

    .hero-left {
        align-items: center;
    }

    .cta-cards {
        flex-direction: column;
        align-items: center;
    }

    .field-row {
        grid-template-columns: 1fr;
    }
}

/* Desktop (above 900px) */
@media (min-width: 901px) {
    .hero-mobile {
        display: none;
    }

    .mobile-form {
        display: none;
    }

    /* Show only desktop form */
    .mobile-form {
        display: none;

        justify-self: center;
    }
}
</style>
