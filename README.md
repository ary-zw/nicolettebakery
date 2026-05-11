# nicolettebakery
Nicolette's Eatery &amp; Bakery website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="theme-color" content="#f8b4d9">
    <title>Nicolette's Eatery & Bakery</title>
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Poppins', sans-serif; background: #faf8f5; color: #333; line-height: 1.6; -webkit-tap-highlight-color: transparent; }
        .header { background: linear-gradient(135deg, #f8b4d9 0%, #f5a0c8 100%); padding: 20px 16px; text-align: center; position: relative; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        .logo-container { background: white; border-radius: 20px; padding: 15px 20px; display: inline-block; box-shadow: 0 4px 15px rgba(0,0,0,0.1); margin-bottom: 15px; }
        .logo-container img { max-width: 220px; height: auto; display: block; }
        .status-badge { display: inline-flex; align-items: center; gap: 8px; padding: 8px 20px; border-radius: 50px; font-weight: 600; font-size: 14px; transition: all 0.3s ease; margin-top: 10px; }
        .status-badge.open { background: #d4edda; color: #155724; }
        .status-badge.closed { background: #f8d7da; color: #721c24; }
        .status-dot { width: 10px; height: 10px; border-radius: 50%; animation: pulse 2s infinite; }
        .status-badge.open .status-dot { background: #28a745; }
        .status-badge.closed .status-dot { background: #dc3545; }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
        .quick-actions { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; padding: 20px 16px; background: white; margin-bottom: 12px; }
        .action-btn { display: flex; flex-direction: column; align-items: center; gap: 6px; text-decoration: none; color: #333; font-size: 12px; font-weight: 500; }
        .action-icon { width: 50px; height: 50px; border-radius: 50%; background: #f8b4d9; display: flex; align-items: center; justify-content: center; font-size: 20px; transition: transform 0.2s; }
        .action-btn:active .action-icon { transform: scale(0.95); }
        .info-section { padding: 0 16px; margin-bottom: 12px; }
        .card { background: white; border-radius: 16px; padding: 20px; margin-bottom: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.05); }
        .card-title { font-size: 18px; font-weight: 700; margin-bottom: 15px; display: flex; align-items: center; gap: 10px; color: #333; }
        .card-title .icon { font-size: 22px; }
        .hours-list { list-style: none; }
        .hours-list li { display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid #f0f0f0; font-size: 14px; }
        .hours-list li:last-child { border-bottom: none; }
        .hours-list li.today { background: #fff5f8; margin: 0 -10px; padding: 10px; border-radius: 10px; border-bottom: none; font-weight: 600; }
        .hours-list li.today .day { color: #e91e63; }
        .contact-item { display: flex; align-items: center; gap: 15px; padding: 12px 0; border-bottom: 1px solid #f0f0f0; text-decoration: none; color: #333; }
        .contact-item:last-child { border-bottom: none; }
        .contact-icon { width: 40px; height: 40px; border-radius: 50%; background: #f8b4d9; display: flex; align-items: center; justify-content: center; font-size: 18px; flex-shrink: 0; }
        .contact-text { font-size: 15px; }
        .contact-label { font-size: 12px; color: #888; }
        .gallery-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; }
        .gallery-item { border-radius: 12px; overflow: hidden; aspect-ratio: 1; position: relative; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.3s; }
        .gallery-item:active img { transform: scale(1.05); }
        .gallery-item.featured { grid-column: span 2; aspect-ratio: 16/9; }
        .menu-categories { display: flex; gap: 10px; overflow-x: auto; padding-bottom: 10px; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
        .menu-categories::-webkit-scrollbar { display: none; }
        .menu-chip { flex-shrink: 0; padding: 10px 20px; background: #f8b4d9; border-radius: 50px; font-size: 14px; font-weight: 500; white-space: nowrap; cursor: pointer; }
        .menu-chip.active { background: #e91e63; color: white; }
        .about-text { font-size: 14px; line-height: 1.8; color: #555; }
        .highlight { color: #e91e63; font-weight: 600; }
        .footer { text-align: center; padding: 30px 16px; background: #333; color: white; font-size: 12px; }
        .footer-logo { font-family: 'Pacifico', cursive; font-size: 24px; color: #f8b4d9; margin-bottom: 10px; }
        .map-container { width: 100%; height: 200px; background: linear-gradient(135deg, #e8e8e8 0%, #d0d0d0 100%); border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-direction: column; gap: 10px; color: #666; text-decoration: none; }
        .map-container .map-icon { font-size: 40px; }
        .review-card { background: #faf8f5; border-radius: 12px; padding: 15px; margin-bottom: 10px; }
        .review-header { display: flex; align-items: center; gap: 10px; margin-bottom: 8px; }
        .review-avatar { width: 40px; height: 40px; border-radius: 50%; background: #f8b4d9; display: flex; align-items: center; justify-content: center; font-weight: 600; color: white; }
        .review-name { font-weight: 600; font-size: 14px; }
        .review-stars { color: #ffc107; font-size: 14px; }
        .review-text { font-size: 13px; color: #555; line-height: 1.6; }
        html { scroll-behavior: smooth; }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="logo-container">
            <img src="C5BBE7A9-0DA7-4B14-8DD6-65ABFE9782E3.jpg" alt="Nicolette's Eatery & Bakery Logo">
        </div>
        <div id="statusBadge" class="status-badge closed">
            <span class="status-dot"></span>
            <span id="statusText">Closed</span>
        </div>
        <p style="color: white; margin-top: 8px; font-size: 13px; opacity: 0.9;">
            <span id="nextOpen">Opens Tuesday at 8:00 AM</span>
        </p>
    </header>

    <!-- Quick Actions -->
    <div class="quick-actions">
        <a href="tel:0775598964" class="action-btn">
            <div class="action-icon">📞</div>
            <span>Call</span>
        </a>
        <a href="https://maps.google.com/?q=67+Dundee+Dr+Bulawayo" class="action-btn" target="_blank">
            <div class="action-icon">🧭</div>
            <span>Directions</span>
        </a>
        <a href="#menu" class="action-btn">
            <div class="action-icon">🍽️</div>
            <span>Menu</span>
        </a>
        <a href="#photos" class="action-btn">
            <div class="action-icon">📸</div>
            <span>Photos</span>
        </a>
    </div>

    <!-- Info Section -->
    <div class="info-section">
        <!-- About -->
        <div class="card">
            <h2 class="card-title"><span class="icon">🏪</span>About</h2>
            <p class="about-text">
                Welcome to <span class="highlight">Nicolette's Eatery & Bakery</span>, Bulawayo's newest culinary destination! 
                Established in 2024, we bring you freshly baked goods, gourmet meals, and a cozy café experience. 
                From our signature donuts and artisan breads to hearty meals and wood-fired pizzas, 
                every dish is crafted with love and the finest ingredients.
            </p>
        </div>

        <!-- Hours -->
        <div class="card">
            <h2 class="card-title"><span class="icon">🕐</span>Opening Hours</h2>
            <ul class="hours-list" id="hoursList">
                <li data-day="1"><span class="day">Monday</span><span>Closed</span></li>
                <li data-day="2"><span class="day">Tuesday</span><span>8:00 AM – 6:00 PM</span></li>
                <li data-day="3"><span class="day">Wednesday</span><span>8:00 AM – 6:00 PM</span></li>
                <li data-day="4"><span class="day">Thursday</span><span>8:00 AM – 6:00 PM</span></li>
                <li data-day="5"><span class="day">Friday</span><span>8:00 AM – 6:00 PM</span></li>
                <li data-day="6"><span class="day">Saturday</span><span>8:00 AM – 6:00 PM</span></li>
                <li data-day="0"><span class="day">Sunday</span><span>8:00 AM – 6:00 PM</span></li>
            </ul>
        </div>

        <!-- Contact -->
        <div class="card">
            <h2 class="card-title"><span class="icon">📍</span>Contact & Location</h2>
            <a href="tel:0775598964" class="contact-item">
                <div class="contact-icon">📞</div>
                <div><div class="contact-text">077 559 8964</div><div class="contact-label">Tap to call</div></div>
            </a>
            <a href="https://maps.google.com/?q=67+Dundee+Dr+Bulawayo" class="contact-item" target="_blank">
                <div class="contact-icon">📍</div>
                <div><div class="contact-text">67 Dundee Dr, Bulawayo</div><div class="contact-label">Tap for directions</div></div>
            </a>
            <div class="contact-item" style="cursor: default;">
                <div class="contact-icon">🏷️</div>
                <div><div class="contact-text">Cafe • Bakery • Restaurant</div><div class="contact-label">Established 2024</div></div>
            </div>
        </div>

        <!-- Menu -->
        <div class="card" id="menu">
            <h2 class="card-title"><span class="icon">🍴</span>Our Menu</h2>
            <div class="menu-categories">
                <div class="menu-chip active">🍩 Donuts</div>
                <div class="menu-chip">🥐 Bakery</div>
                <div class="menu-chip">🍳 Breakfast</div>
                <div class="menu-chip">🍕 Pizza</div>
                <div class="menu-chip">🥩 Meals</div>
                <div class="menu-chip">☕ Coffee</div>
            </div>
            <p style="margin-top: 15px; font-size: 13px; color: #666; text-align: center;">
                Freshly baked daily • Made with love • Premium ingredients
            </p>
        </div>

        <!-- Photos -->
        <div class="card" id="photos">
            <h2 class="card-title"><span class="icon">📸</span>Gallery</h2>
            <div class="gallery-grid">
                <div class="gallery-item featured">
                    <img src="C054AA82-B706-4589-9CB9-3C3831190D3C.jpg" alt="Gourmet meal spread">
                </div>
                <div class="gallery-item">
                    <img src="FCDC57A5-CA5A-47D1-B138-EA338168DAE4.jpg" alt="Sugar donuts">
                </div>
                <div class="gallery-item">
                    <img src="C4A2DE1F-8D0A-45A7-A19C-D89BB4868C3C.jpg" alt="Chocolate donuts">
                </div>
                <div class="gallery-item">
                    <img src="D4985695-BFD1-41D7-AAAA-696037AE94E9.jpg" alt="Bruschetta toast">
                </div>
            </div>
        </div>

        <!-- Reviews -->
        <div class="card">
            <h2 class="card-title"><span class="icon">⭐</span>Reviews</h2>
            <div class="review-card">
                <div class="review-header">
                    <div class="review-avatar">S</div>
                    <div><div class="review-name">Sarah M.</div><div class="review-stars">⭐⭐⭐⭐⭐</div></div>
                </div>
                <p class="review-text">"The donuts are absolutely divine! Fresh, fluffy, and perfectly glazed. Best bakery in Bulawayo!"</p>
            </div>
            <div class="review-card">
                <div class="review-header">
                    <div class="review-avatar">J</div>
                    <div><div class="review-name">John K.</div><div class="review-stars">⭐⭐⭐⭐⭐</div></div>
                </div>
                <p class="review-text">"Amazing brunch spot! The wood-fired pizza and ribs are to die for. Great atmosphere too."</p>
            </div>
        </div>

        <!-- Map -->
        <div class="card">
            <h2 class="card-title"><span class="icon">🗺️</span>Find Us</h2>
            <a href="https://maps.google.com/?q=67+Dundee+Dr+Bulawayo" class="map-container" target="_blank">
                <div class="map-icon">🗺️</div>
                <div style="text-align: center;">
                    <div style="font-weight: 600; color: #333;">67 Dundee Dr, Bulawayo</div>
                    <div style="font-size: 12px; color: #888; margin-top: 4px;">Tap to open in Maps</div>
                </div>
            </a>
        </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-logo">Nicolette's</div>
        <p>Eatery & Bakery • Est. 2024</p>
        <p style="margin-top: 8px; opacity: 0.7;">67 Dundee Dr, Bulawayo</p>
        <p style="margin-top: 4px; opacity: 0.7;">077 559 8964</p>
    </footer>
    <script>
        const hoursConfig = {
            0: { open: '08:00', close: '18:00', name: 'Sunday' },
            1: null,
            2: { open: '08:00', close: '18:00', name: 'Tuesday' },
            3: { open: '08:00', close: '18:00', name: 'Wednesday' },
            4: { open: '08:00', close: '18:00', name: 'Thursday' },
            5: { open: '08:00', close: '18:00', name: 'Friday' },
            6: { open: '08:00', close: '18:00', name: 'Saturday' }
        };

        function updateStatus() {
            const now = new Date();
            const catTime = new Date(now.toLocaleString("en-US", { timeZone: "Africa/Harare" }));
            const day = catTime.getDay();
            const currentHour = catTime.getHours();
            const currentMinute = catTime.getMinutes();
            const currentTime = currentHour * 60 + currentMinute;

            const todayHours = hoursConfig[day];
            const statusBadge = document.getElementById('statusBadge');
            const statusText = document.getElementById('statusText');
            const nextOpenText = document.getElementById('nextOpen');

            document.querySelectorAll('.hours-list li').forEach(li => {
                li.classList.remove('today');
                if (parseInt(li.dataset.day) === day) li.classList.add('today');
            });

            if (!todayHours) {
                statusBadge.className = 'status-badge closed';
                statusText.textContent = 'Closed';
                let nextDay = day + 1;
                if (nextDay > 6) nextDay = 0;
                while (!hoursConfig[nextDay]) {
                    nextDay++;
                    if (nextDay > 6) nextDay = 0;
                }
                nextOpenText.textContent = `Opens ${hoursConfig[nextDay].name} at 8:00 AM`;
                return;
            }

            const openTime = parseInt(todayHours.open.split(':')[0]) * 60 + parseInt(todayHours.open.split(':')[1]);
            const closeTime = parseInt(todayHours.close.split(':')[0]) * 60 + parseInt(todayHours.close.split(':')[1]);

            if (currentTime >= openTime && currentTime < closeTime) {
                statusBadge.className = 'status-badge open';
                statusText.textContent = 'Open Now';
                const closeHour = Math.floor(closeTime / 60);
                const closeMin = closeTime % 60;
                nextOpenText.textContent = `Closes at ${String(closeHour).padStart(2, '0')}:${String(closeMin).padStart(2, '0')}`;
            } else {
                statusBadge.className = 'status-badge closed';
                statusText.textContent = 'Closed';
                if (currentTime < openTime) {
                    const openHour = Math.floor(openTime / 60);
                    const openMin = openTime % 60;
                    nextOpenText.textContent = `Opens at ${String(openHour).padStart(2, '0')}:${String(openMin).padStart(2, '0')}`;
                } else {
                    let nextDay = day + 1;
                    if (nextDay > 6) nextDay = 0;
                    while (!hoursConfig[nextDay]) {
                        nextDay++;
                        if (nextDay > 6) nextDay = 0;
                    }
                    nextOpenText.textContent = `Opens ${hoursConfig[nextDay].name} at 8:00 AM`;
                }
            }
        }

        updateStatus();
        setInterval(updateStatus, 60000);

        document.querySelectorAll('.menu-chip').forEach(chip => {
            chip.addEventListener('click', function() {
                document.querySelectorAll('.menu-chip').forEach(c => c.classList.remove('active'));
                this.classList.add('active');
            });
        });
    </script>
</body>
</html>
