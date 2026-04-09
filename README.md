
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TorqueFix Auto Repair</title>
  <meta name="description" content="Professional auto repair shop template with booking, services, and pricing." />
  <style>
    :root{
      --bg:#0b1020;
      --panel:#121936;
      --panel-2:#182246;
      --text:#eef3ff;
      --muted:#aab6d3;
      --primary:#ff5a36;
      --primary-2:#ff8a36;
      --accent:#36c2ff;
      --line:rgba(255,255,255,.08);
      --success:#20c997;
      --shadow:0 20px 50px rgba(0,0,0,.35);
      --radius:20px;
      --radius-sm:14px;
      --max:1200px;
    }

    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      font-family:Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color:var(--text);
      background:
        radial-gradient(circle at top left, rgba(255,90,54,.18), transparent 28%),
        radial-gradient(circle at top right, rgba(54,194,255,.12), transparent 22%),
        linear-gradient(180deg, #0a0f1f 0%, #0b1020 100%);
      overflow-x:hidden;
    }

    a{text-decoration:none;color:inherit}
    img{max-width:100%;display:block}
    .container{width:min(var(--max), calc(100% - 2rem)); margin:auto}

    .btn{
      display:inline-flex; align-items:center; justify-content:center;
      gap:.6rem; border:none; cursor:pointer;
      padding:1rem 1.3rem; border-radius:999px; font-weight:700;
      transition:.25s ease; font-size:.98rem;
    }
    .btn-primary{
      background:linear-gradient(135deg, var(--primary), var(--primary-2));
      color:white; box-shadow:0 12px 30px rgba(255,90,54,.35);
    }
    .btn-primary:hover{transform:translateY(-2px); filter:brightness(1.05)}
    .btn-secondary{
      background:rgba(255,255,255,.06); color:var(--text);
      border:1px solid rgba(255,255,255,.08);
    }
    .btn-secondary:hover{background:rgba(255,255,255,.1); transform:translateY(-2px)}
    .tag{
      display:inline-flex; align-items:center; gap:.5rem;
      padding:.45rem .8rem; border-radius:999px;
      background:rgba(255,255,255,.06); border:1px solid var(--line);
      color:#dce6ff; font-size:.85rem; font-weight:600;
      backdrop-filter: blur(8px);
    }
    .section{padding:88px 0}
    .section-title{
      font-size:clamp(1.9rem,4vw,3rem);
      line-height:1.05; margin:0 0 .8rem;
      letter-spacing:-.03em;
    }
    .section-text{color:var(--muted); font-size:1.02rem; line-height:1.7; max-width:700px}
    .grid{display:grid; gap:1.25rem}

    header{
      position:sticky; top:0; z-index:50;
      backdrop-filter: blur(14px);
      background:rgba(7,10,22,.65);
      border-bottom:1px solid rgba(255,255,255,.06);
    }
    .nav{
      display:flex; align-items:center; justify-content:space-between;
      min-height:76px;
    }
    .brand{
      display:flex; align-items:center; gap:.85rem; font-weight:800; letter-spacing:-.02em;
    }
    .brand-badge{
      width:42px;height:42px;border-radius:14px;
      background:linear-gradient(135deg, var(--primary), var(--primary-2));
      display:grid;place-items:center; box-shadow:0 10px 24px rgba(255,90,54,.28);
      font-size:1.2rem;
    }
    .nav-links{
      display:flex; align-items:center; gap:1.2rem; color:#d8e1ff;
    }
    .nav-links a{font-size:.95rem; color:#d5ddf7}
    .nav-links a:hover{color:#fff}
    .menu-btn{display:none}

    .hero{padding:72px 0 40px}
    .hero-wrap{
      display:grid; grid-template-columns:1.15fr .85fr; gap:1.5rem; align-items:stretch;
    }
    .hero-card, .glass{
      background:linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.03));
      border:1px solid var(--line);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
      overflow:hidden;
      position:relative;
    }
    .hero-left{padding:2.4rem}
    .hero-left h1{
      font-size:clamp(2.3rem,5vw,4.8rem);
      line-height:.96; letter-spacing:-.05em; margin:.8rem 0 1rem;
      max-width:760px;
    }
    .hero-left p{font-size:1.08rem; line-height:1.75; color:var(--muted); max-width:650px}
    .hero-cta{display:flex; gap:.85rem; flex-wrap:wrap; margin-top:1.4rem}
    .hero-stats{
      display:grid; grid-template-columns:repeat(3,1fr); gap:1rem; margin-top:1.8rem;
    }
    .stat{
      padding:1rem; border-radius:18px; background:rgba(255,255,255,.04); border:1px solid var(--line);
    }
    .stat strong{display:block; font-size:1.4rem}
    .stat span{color:var(--muted); font-size:.92rem}
    .hero-right{
      min-height:100%; display:flex; flex-direction:column;
      background:
        linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02)),
        radial-gradient(circle at top right, rgba(255,90,54,.18), transparent 26%);
    }
    .hero-image{
      flex:1;
      min-height:420px;
      background:
        linear-gradient(180deg, rgba(10,15,31,.05), rgba(10,15,31,.45)),
        url('https://images.unsplash.com/photo-1487754180451-c456f719a1fc?auto=format&fit=crop&w=1400&q=80') center/cover;
    }
    .hero-overlay-card{
      position:absolute; right:18px; bottom:18px; left:18px;
      padding:1rem; border-radius:18px;
      background:rgba(11,16,32,.78); border:1px solid rgba(255,255,255,.09);
      display:flex; justify-content:space-between; gap:1rem; align-items:center;
    }
    .hero-overlay-card .small{color:var(--muted); font-size:.88rem}
    .hero-overlay-card strong{display:block; font-size:1.05rem}

    .trust-bar{
      margin-top:22px;
      display:grid; grid-template-columns:repeat(4,1fr); gap:1rem;
    }
    .trust{
      padding:1rem 1.2rem; border-radius:18px; border:1px solid var(--line);
      background:rgba(255,255,255,.04); color:#dbe5ff; text-align:center; font-weight:600;
    }

    .services-grid{grid-template-columns:repeat(3,1fr)}
    .card{
      padding:1.35rem; border-radius:var(--radius-sm);
      background:linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.03));
      border:1px solid var(--line); box-shadow:var(--shadow);
      transition:.25s ease;
    }
    .card:hover{transform:translateY(-5px); border-color:rgba(255,255,255,.14)}
    .icon{
      width:52px;height:52px;border-radius:16px; display:grid; place-items:center;
      background:linear-gradient(135deg, rgba(255,90,54,.22), rgba(255,138,54,.08));
      border:1px solid rgba(255,255,255,.08);
      font-size:1.4rem; margin-bottom:1rem;
    }
    .card h3{margin:.2rem 0 .5rem; font-size:1.14rem}
    .card p{margin:0; color:var(--muted); line-height:1.7; font-size:.96rem}

    .pricing-wrap{
      display:grid; grid-template-columns:.9fr 1.1fr; gap:1.25rem; align-items:start;
    }
    .pricing-list{display:grid; gap:1rem}
    .price-item{
      display:flex; align-items:center; justify-content:space-between; gap:1rem;
      padding:1rem 1.1rem; border-radius:16px; background:rgba(255,255,255,.04); border:1px solid var(--line);
    }
    .price-item small{display:block; color:var(--muted); margin-top:.2rem}
    .price{
      font-size:1.15rem; font-weight:800;
      color:#fff;
    }

    .booking-panel{padding:1.4rem}
    .form-grid{display:grid; grid-template-columns:repeat(2,1fr); gap:1rem}
    .field{display:flex; flex-direction:column; gap:.45rem}
    .field label{font-size:.92rem; color:#dce5ff; font-weight:600}
    .field input,.field select,.field textarea{
      width:100%; padding:.95rem 1rem; border-radius:14px;
      border:1px solid rgba(255,255,255,.09);
      background:#0d1430; color:#fff; outline:none;
      transition:.2s ease;
    }
    .field input:focus,.field select:focus,.field textarea:focus{
      border-color:rgba(255,90,54,.7); box-shadow:0 0 0 4px rgba(255,90,54,.12);
    }
    .field textarea{min-height:110px; resize:vertical}
    .full{grid-column:1/-1}
    .helper{font-size:.85rem; color:var(--muted)}
    .booking-success{
      margin-top:1rem; display:none; padding:.95rem 1rem; border-radius:14px;
      background:rgba(32,201,151,.12); border:1px solid rgba(32,201,151,.28); color:#d7fff1;
    }

    .split{
      display:grid; grid-template-columns:1fr 1fr; gap:1.25rem;
    }

    .testimonial{
      display:flex; flex-direction:column; gap:1rem;
      min-height:100%;
    }
    .stars{color:#ffcf5c; letter-spacing:.1em}
    .quote{font-size:1rem; color:#e9efff; line-height:1.8}
    .person{display:flex; align-items:center; gap:.85rem; margin-top:auto}
    .avatar{
      width:48px;height:48px;border-radius:50%;
      background:linear-gradient(135deg, var(--accent), #7a8cff);
      display:grid;place-items:center; font-weight:800;
    }
    .muted{color:var(--muted)}

    .cta{
      padding:2rem; text-align:center;
      background:
        radial-gradient(circle at top center, rgba(255,90,54,.22), transparent 35%),
        linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.03));
    }
    .cta h2{margin:.2rem 0 .75rem; font-size:clamp(1.8rem,4vw,3rem)}
    .cta p{margin:0 auto 1.2rem; color:var(--muted); max-width:700px; line-height:1.8}

    footer{
      padding:28px 0 46px;
      color:#ced7f6;
    }
    .footer-grid{
      display:grid; grid-template-columns:1.1fr .8fr .8fr .9fr; gap:1.25rem;
    }
    .footer-grid h4{margin:0 0 .8rem; font-size:1rem}
    .footer-grid a,.footer-grid p{color:var(--muted); margin:.45rem 0; display:block}
    .footer-bottom{
      margin-top:1.25rem; padding-top:1rem; border-top:1px solid var(--line);
      display:flex; justify-content:space-between; gap:1rem; flex-wrap:wrap; color:var(--muted);
      font-size:.92rem;
    }

    .reveal{opacity:0; transform:translateY(18px); transition:.6s ease}
    .reveal.visible{opacity:1; transform:none}

    @media (max-width: 1024px){
      .hero-wrap,.pricing-wrap,.split,.footer-grid{grid-template-columns:1fr}
      .services-grid{grid-template-columns:repeat(2,1fr)}
      .trust-bar{grid-template-columns:repeat(2,1fr)}
    }

    @media (max-width: 760px){
      .nav-links{
        position:absolute; top:76px; left:1rem; right:1rem;
        display:none; flex-direction:column; align-items:flex-start;
        padding:1rem; border-radius:18px;
        background:rgba(11,16,32,.96); border:1px solid var(--line);
      }
      .nav-links.open{display:flex}
      .menu-btn{
        display:inline-flex; width:46px; height:46px; border-radius:14px;
        border:1px solid var(--line); background:rgba(255,255,255,.05); color:#fff;
        align-items:center; justify-content:center; cursor:pointer;
      }
      .hero-left{padding:1.4rem}
      .hero-stats,.services-grid,.form-grid,.trust-bar{grid-template-columns:1fr}
      .hero{padding-top:28px}
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <a href="#" class="brand">
        <span class="brand-badge">⚙️</span>
        <span>TorqueFix Auto Repair</span>
      </a>

      <nav class="nav-links" id="navLinks">
        <a href="#services">Services</a>
        <a href="#pricing">Pricing</a>
        <a href="#booking">Book Now</a>
        <a href="#reviews">Reviews</a>
        <a href="#contact">Contact</a>
        <a href="#booking" class="btn btn-primary" style="padding:.8rem 1rem">Schedule Service</a>
      </nav>

      <button class="menu-btn" id="menuBtn" aria-label="Toggle menu">☰</button>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="container hero-wrap">
        <div class="hero-card hero-left reveal">
          <span class="tag">Trusted Local Mechanics • Same-Day Service Available</span>
          <h1>Fast, honest auto repair that keeps you on the road.</h1>
          <p>
            From oil changes and brake service to diagnostics and engine repair, TorqueFix delivers reliable workmanship, transparent pricing, and easy online booking.
          </p>

          <div class="hero-cta">
            <a href="#booking" class="btn btn-primary">Book a Service</a>
            <a href="#pricing" class="btn btn-secondary">View Pricing</a>
          </div>

          <div class="hero-stats">
            <div class="stat">
              <strong>15+</strong>
              <span>Years Experience</span>
            </div>
            <div class="stat">
              <strong>4.9/5</strong>
              <span>Customer Rating</span>
            </div>
            <div class="stat">
              <strong>2,500+</strong>
              <span>Vehicles Serviced</span>
            </div>
          </div>
        </div>

        <div class="hero-card hero-right reveal">
          <div class="hero-image"></div>
          <div class="hero-overlay-card">
            <div>
              <span class="small">Open Today</span>
              <strong>Mon–Sat • 8:00 AM – 6:00 PM</strong>
            </div>
            <a href="#booking" class="btn btn-primary" style="padding:.85rem 1rem">Get Started</a>
          </div>
        </div>
      </div>

      <div class="container trust-bar reveal">
        <div class="trust">ASE-Certified Techs</div>
        <div class="trust">Warranty on Repairs</div>
        <div class="trust">Free Multi-Point Inspection</div>
        <div class="trust">Easy Online Booking</div>
      </div>
    </section>

    <section class="section" id="services">
      <div class="container">
        <span class="tag reveal">Our Services</span>
        <h2 class="section-title reveal">Complete repair and maintenance services.</h2>
        <p class="section-text reveal">
          Professional care for domestic, import, and fleet vehicles with modern diagnostics and experienced technicians.
        </p>

        <div class="grid services-grid" style="margin-top:1.4rem">
          <div class="card reveal">
            <div class="icon">🛢️</div>
            <h3>Oil Change & Fluids</h3>
            <p>Full synthetic and conventional oil changes, filters, coolant, transmission, and brake fluid service.</p>
          </div>
          <div class="card reveal">
            <div class="icon">🛑</div>
            <h3>Brake Repair</h3>
            <p>Brake pad replacement, rotor resurfacing, caliper repair, and complete brake system inspections.</p>
          </div>
          <div class="card reveal">
            <div class="icon">🔍</div>
            <h3>Engine Diagnostics</h3>
            <p>Check engine light scans, performance diagnostics, and expert troubleshooting for complex issues.</p>
          </div>
          <div class="card reveal">
            <div class="icon">🔋</div>
            <h3>Battery & Electrical</h3>
            <p>Battery testing, alternators, starters, wiring checks, and electrical fault diagnosis and repair.</p>
          </div>
          <div class="card reveal">
            <div class="icon">🛞</div>
            <h3>Tires & Alignment</h3>
            <p>Tire rotation, balancing, replacement, wheel alignment, and suspension safety inspections.</p>
          </div>
          <div class="card reveal">
            <div class="icon">❄️</div>
            <h3>A/C & Heating</h3>
            <p>Climate control diagnostics, refrigerant recharge, compressor service, and cabin comfort repairs.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="pricing" style="padding-top:20px">
      <div class="container pricing-wrap">
        <div class="glass" style="padding:1.6rem" >
          <span class="tag reveal">Transparent Pricing</span>
          <h2 class="section-title reveal">Popular services with clear starting rates.</h2>
          <p class="section-text reveal">Final pricing may vary by vehicle make, model, parts, and labor. We always confirm estimates before work begins.</p>

          <div class="pricing-list" style="margin-top:1.2rem">
            <div class="price-item reveal">
              <div>
                <strong>Conventional Oil Change</strong>
                <small>Includes filter and inspection</small>
              </div>
              <div class="price">$49</div>
            </div>
            <div class="price-item reveal">
              <div>
                <strong>Synthetic Oil Change</strong>
                <small>Premium synthetic oil and filter</small>
              </div>
              <div class="price">$79</div>
            </div>
            <div class="price-item reveal">
              <div>
                <strong>Brake Pad Replacement</strong>
                <small>Per axle, parts + labor starting at</small>
              </div>
              <div class="price">$149</div>
            </div>
            <div class="price-item reveal">
              <div>
                <strong>Diagnostic Scan</strong>
                <small>Check engine light and system scan</small>
              </div>
              <div class="price">$89</div>
            </div>
            <div class="price-item reveal">
              <div>
                <strong>Wheel Alignment</strong>
                <small>4-wheel alignment service</small>
              </div>
              <div class="price">$119</div>
            </div>
            <div class="price-item reveal">
              <div>
                <strong>A/C Service</strong>
                <small>Inspection and recharge starting at</small>
              </div>
              <div class="price">$129</div>
            </div>
          </div>
        </div>

        <div class="glass booking-panel reveal" id="booking">
          <span class="tag">Book Service</span>
          <h3 style="font-size:1.8rem; margin:.9rem 0 .5rem; letter-spacing:-.03em">Schedule your appointment online.</h3>
          <p class="helper" style="margin:0 0 1rem">Choose a service, preferred date, and we’ll confirm your booking shortly.</p>

          <form id="bookingForm">
            <div class="form-grid">
              <div class="field">
                <label for="name">Full Name</label>
                <input id="name" name="name" type="text" placeholder="John Carter" required />
              </div>
              <div class="field">
                <label for="phone">Phone Number</label>
                <input id="phone" name="phone" type="tel" placeholder="(555) 123-4567" required />
              </div>

              <div class="field">
                <label for="email">Email Address</label>
                <input id="email" name="email" type="email" placeholder="you@example.com" required />
              </div>
              <div class="field">
                <label for="vehicle">Vehicle</label>
                <input id="vehicle" name="vehicle" type="text" placeholder="2019 Toyota Camry" required />
              </div>

              <div class="field">
                <label for="service">Service Needed</label>
                <select id="service" name="service" required>
                  <option value="">Select a service</option>
                  <option>Oil Change</option>
                  <option>Brake Repair</option>
                  <option>Engine Diagnostics</option>
                  <option>Battery & Electrical</option>
                  <option>Tires & Alignment</option>
                  <option>A/C & Heating</option>
                  <option>General Maintenance</option>
                </select>
              </div>
              <div class="field">
                <label for="date">Preferred Date</label>
                <input id="date" name="date" type="date" required />
              </div>

              <div class="field full">
                <label for="notes">Notes</label>
                <textarea id="notes" name="notes" placeholder="Tell us about symptoms, warning lights, or preferred time."></textarea>
              </div>

              <div class="field full">
                <button type="submit" class="btn btn-primary" style="width:100%">Confirm Booking Request</button>
              </div>
            </div>
            <div class="booking-success" id="bookingSuccess">
              Thanks! Your booking request has been received. Our team will contact you shortly to confirm your appointment.
            </div>
          </form>
        </div>
      </div>
    </section>

    <section class="section" id="reviews">
      <div class="container">
        <span class="tag reveal">Customer Reviews</span>
        <h2 class="section-title reveal">Drivers trust TorqueFix for reliable service.</h2>
        <div class="split" style="margin-top:1.3rem">
          <div class="card testimonial reveal">
            <div class="stars">★★★★★</div>
            <div class="quote">“Quick diagnosis, fair pricing, and no upselling. They had my brakes done the same day and the car feels great.”</div>
            <div class="person">
              <div class="avatar">MS</div>
              <div>
                <strong>Maria S.</strong>
                <div class="muted">Brake Service</div>
              </div>
            </div>
          </div>
          <div class="card testimonial reveal">
            <div class="stars">★★★★★</div>
            <div class="quote">“Best repair shop in town. Booking online was easy and they explained everything clearly before starting the work.”</div>
            <div class="person">
              <div class="avatar">DT</div>
              <div>
                <strong>David T.</strong>
                <div class="muted">Engine Diagnostic</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section" style="padding-top:10px">
      <div class="container">
        <div class="glass cta reveal">
          <span class="tag">Need urgent service?</span>
          <h2>Call now for same-day availability.</h2>
          <p>Talk to our team for diagnostics, maintenance, and repair scheduling. We’ll help you get back on the road fast.</p>
          <a href="tel:+15551234567" class="btn btn-primary">(555) 123-4567</a>
        </div>
      </div>
    </section>
  </main>

  <footer id="contact">
    <div class="container">
      <div class="footer-grid">
        <div>
          <div class="brand" style="margin-bottom:.7rem">
            <span class="brand-badge">⚙️</span>
            <span>TorqueFix Auto Repair</span>
          </div>
          <p>Professional auto repair, maintenance, and diagnostics with transparent pricing and dependable service.</p>
        </div>
        <div>
          <h4>Hours</h4>
          <a href="#">Mon–Fri: 8:00 AM – 6:00 PM</a>
          <a href="#">Saturday: 8:00 AM – 4:00 PM</a>
          <a href="#">Sunday: Closed</a>
        </div>
        <div>
          <h4>Contact</h4>
          <a href="tel:+15551234567">(555) 123-4567</a>
          <a href="mailto:service@torquefix.com">service@torquefix.com</a>
          <a href="#">123 Garage Ave, Your City, ST 10001</a>
        </div>
        <div>
          <h4>Quick Links</h4>
          <a href="#services">Services</a>
          <a href="#pricing">Pricing</a>
          <a href="#booking">Book Service</a>
          <a href="#reviews">Reviews</a>
        </div>
      </div>

      <div class="footer-bottom">
        <span>© 2026 TorqueFix Auto Repair. All rights reserved.</span>
        <span>Built for modern auto service businesses.</span>
      </div>
    </div>
  </footer>

  <script>
    const menuBtn = document.getElementById('menuBtn');
    const navLinks = document.getElementById('navLinks');

    menuBtn.addEventListener('click', () => {
      navLinks.classList.toggle('open');
    });

    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', () => navLinks.classList.remove('open'));
    });

    const observer = new IntersectionObserver((entries)=>{
      entries.forEach(entry=>{
        if(entry.isIntersecting) entry.target.classList.add('visible');
      });
    },{threshold:.12});

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

    const dateInput = document.getElementById('date');
    const today = new Date();
    const yyyy = today.getFullYear();
    const mm = String(today.getMonth()+1).padStart(2,'0');
    const dd = String(today.getDate()).padStart(2,'0');
    dateInput.min = `${yyyy}-${mm}-${dd}`;

    const form = document.getElementById('bookingForm');
    const success = document.getElementById('bookingSuccess');

    form.addEventListener('submit', function(e){
      e.preventDefault();
      success.style.display = 'block';
      form.reset();
      dateInput.min = `${yyyy}-${mm}-${dd}`;
      success.scrollIntoView({behavior:'smooth', block:'nearest'});
      setTimeout(() => { success.style.display = 'none'; }, 6000);
    });
  </script>
</body>
</html>
