<script>
	import { onMount } from 'svelte';

	const projects = [
		{
			id: '01',
			name: 'MuseVibe',
			kind: 'AI TOOL — WEB APP',
			desc: 'Prompt menjadi PRD, desain, dan scaffold kode. Dibangun untuk Meta AI Developer Hackathon, Indie Track.',
			stack: ['Next.js', 'Supabase', 'Muse Spark'],
			link: 'https://musevibe.vercel.app',
			linkLabel: 'musevibe.vercel.app'
		},
		{
			id: '02',
			name: 'Smart Irrigation',
			kind: 'IOT — DASHBOARD',
			desc: 'Monitoring kebun cabai: ESP32 kirim data lewat MQTT ke Laravel, lengkap dengan alert Telegram saat pompa berubah.',
			stack: ['ESP32', 'Laravel', 'Mosquitto', 'PostgreSQL'],
			link: 'https://iotdash.avriyyy.my.id',
			linkLabel: 'iotdash.avriyyy.my.id'
		},
		{
			id: '03',
			name: 'CPMK03 — CRUD Mahasiswa',
			kind: 'WEB — GO FIBER + MYSQL',
			desc: 'CRUD Data Mahasiswa & Program Studi dengan arsitektur MVC, validasi, dan export/import CSV. Tugas ujian Pemrograman Web II.',
			stack: ['Go', 'Fiber', 'MySQL'],
			link: 'https://youtu.be/P_pP8kBvH80',
			linkLabel: 'Lihat demo video'
		}
	];

	const socials = [
		{ mark: 'GH', name: 'GitHub', handle: '@avriyyy', href: 'https://github.com/avriyyy' },
		{ mark: 'in', name: 'LinkedIn', handle: '/in/apriyudha', href: 'https://www.linkedin.com/in/apriyudha' },
		{ mark: 'X', name: 'X', handle: '@Avriyyy23', href: 'https://x.com/Avriyyy23' },
		{ mark: 'IG', name: 'Instagram', handle: '@apriyudha_', href: 'https://www.instagram.com/apriyudha_' },
		{ mark: '@', name: 'Email', handle: 'apriyudha307@gmail.com', href: 'mailto:apriyudha307@gmail.com' }
	];

	const marquee = ['Web Development', 'IoT', 'AI Tools', 'Go', 'TypeScript', 'ESP32', 'Supabase', 'Cloudflare'];

	onMount(() => {
		const els = document.querySelectorAll('.reveal');
		const io = new IntersectionObserver(
			(entries) => {
				for (const e of entries) {
					if (e.isIntersecting) {
						e.target.classList.add('visible');
						io.unobserve(e.target);
					}
				}
			},
			{ threshold: 0.15 }
		);
		els.forEach((el) => io.observe(el));
		return () => io.disconnect();
	});
</script>

<svelte:head>
	<title>Apriyudha — Computer Engineering & Web Developer</title>
</svelte:head>

<!-- Announcement bar -->
<div class="announce">
	<a href="mailto:apriyudha307@gmail.com">
		Open for freelance &amp; collaboration <span aria-hidden="true">↗</span>
	</a>
</div>

<!-- Nav -->
<header class="nav">
	<div class="wrap nav-inner">
		<a href="#top" class="wordmark">apriyudha<span class="dot">.</span></a>
		<nav class="nav-links" aria-label="Navigasi utama">
			<a href="#about">Tentang</a>
			<a href="#projects">Project</a>
			<a href="#socials">Sosial Media</a>
		</nav>
		<a class="btn btn-primary btn-sm" href="mailto:apriyudha307@gmail.com">Contact ↗</a>
	</div>
</header>

<main id="top">
	<!-- Hero -->
	<section class="hero">
		<div class="blob blob-a" aria-hidden="true"></div>
		<div class="blob blob-b" aria-hidden="true"></div>
		<div class="blob blob-c" aria-hidden="true"></div>
		<div class="wrap hero-inner">
			<p class="eyebrow reveal">Apriyudha — Computer Engineering, Unsoed</p>
			<h1 class="reveal">
				Building for the web,<br />
				and the world <span class="accent">beyond it.</span>
			</h1>
			<p class="hero-sub reveal">
				Mahasiswa Teknik Komputer di Universitas Jenderal Soedirman. Saya membangun produk web,
				dashboard IoT, dan AI tools — dari ide sampai live.
			</p>
			<div class="hero-cta reveal">
				<a class="btn btn-primary" href="#projects"
					>Lihat Project <span class="arrow" aria-hidden="true">↗</span></a
				>
				<a class="btn btn-ghost" href="https://github.com/avriyyy" target="_blank" rel="noreferrer"
					>GitHub</a
				>
			</div>
		</div>
		<div class="marquee" aria-hidden="true">
			<div class="marquee-track">
				{#each [...marquee, ...marquee] as item}
					<span>{item}</span><i>▫</i>
				{/each}
			</div>
		</div>
	</section>

	<!-- About -->
	<section class="section" id="about">
		<div class="wrap about-grid">
			<figure class="photo-card reveal">
				<img src="/profile.jpg" alt="Foto Apriyudha" width="400" height="400" />
				<figcaption>
					<strong>Apriyudha</strong>
					<span>Teknik Komputer ’24 — Unsoed</span>
				</figcaption>
			</figure>
			<div class="about-text reveal">
				<p class="eyebrow">Tentang</p>
				<h2>Mahasiswa yang suka membangun sampai jadi.</h2>
				<p>
					Saya Apriyudha, mahasiswa Teknik Komputer angkatan 2024 di Universitas Jenderal
					Soedirman, berbasis di Cirebon. Fokus saya: web development, IoT, dan AI tools.
				</p>
				<p>
					Saya percaya project yang bagus adalah yang selesai dan dipakai — bukan yang berhenti di
					slide presentasi. Semua project di bawah ini live dan bisa dibuka.
				</p>
				<ul class="facts">
					<li><span>Universitas</span><strong>Unsoed — Teknik Komputer</strong></li>
					<li><span>Angkatan</span><strong>2024</strong></li>
					<li><span>Berbasis di</span><strong>Cirebon, Jawa Barat</strong></li>
					<li><span>Fokus</span><strong>Web · IoT · AI Tools</strong></li>
				</ul>
			</div>
		</div>
	</section>

	<!-- Projects -->
	<section class="section projects" id="projects">
		<div class="wrap">
			<div class="section-head reveal">
				<p class="eyebrow">Project</p>
				<h2>Sudah jadi, sudah live.</h2>
				<p>Hanya project yang selesai dan bisa dibuka — tanpa mockup, tanpa janji.</p>
			</div>
			<div class="project-grid">
				{#each projects as p}
					<article class="project-card reveal">
						<div class="project-visual visual-{p.id}">
							{#if p.id === '01'}
								<div class="mini-window">
									<div class="mini-bar"><i></i><i></i><i></i><span>musevibe — prd.md</span></div>
									<div class="mini-lines">
										<span class="l-title"># SoloStride — PRD</span>
										<span class="l"></span><span class="l short"></span>
										<span class="l"></span><span class="l mid"></span>
										<span class="l-check">✓ 8 tasks mapped</span>
										<span class="l-check">✓ 3/3 designs ready</span>
									</div>
								</div>
							{:else if p.id === '02'}
								<div class="mini-chart">
									<div class="mini-stats">
										<div><small>Kelembapan tanah</small><strong>58%</strong></div>
										<div><small>Suhu</small><strong>31°C</strong></div>
										<div><small>Pompa</small><strong class="on">● Nyala</strong></div>
									</div>
									<svg viewBox="0 0 320 90" aria-hidden="true">
										<polyline
											points="0,70 40,62 80,66 120,48 160,54 200,36 240,42 280,24 320,30"
											fill="none"
											stroke="#005cff"
											stroke-width="2.5"
										/>
										<polyline
											points="0,78 40,74 80,76 120,70 160,72 200,64 240,66 280,58 320,60"
											fill="none"
											stroke="#9dc0ff"
											stroke-width="2"
										/>
									</svg>
								</div>
							{:else}
								<div class="mini-table">
									<div class="mini-row head"><span>NIM</span><span>Nama</span><span>Prodi</span></div>
									<div class="mini-row"><span>H1H024010</span><span>Apriyudha</span><span>Tekkom</span></div>
									<div class="mini-row"><span>H1H024011</span><span>Mahasiswa</span><span>Tekkom</span></div>
									<div class="mini-row"><span>H1H024012</span><span>Mahasiswa</span><span>Tekkom</span></div>
									<div class="mini-foot"><span>GET /mahasiswa</span><span class="ok">200 OK</span></div>
								</div>
							{/if}
						</div>
						<div class="project-body">
							<p class="mono project-kind">{p.id} — {p.kind}</p>
							<h3>{p.name}</h3>
							<p class="project-desc">{p.desc}</p>
							<div class="tags">
								{#each p.stack as t}
									<span>{t}</span>
								{/each}
							</div>
							<a class="project-link" href={p.link} target="_blank" rel="noreferrer">
								{p.linkLabel} <span aria-hidden="true">↗</span>
							</a>
						</div>
					</article>
				{/each}
			</div>
		</div>
	</section>

	<!-- Socials -->
	<section class="section" id="socials">
		<div class="wrap">
			<div class="section-head reveal">
				<p class="eyebrow">Sosial Media</p>
				<h2>Temui saya di sini.</h2>
				<p>Untuk kerja sama, pertanyaan, atau sekadar menyapa.</p>
			</div>
			<div class="social-grid reveal">
				{#each socials as s}
					<a class="social-card" href={s.href} target="_blank" rel="noreferrer">
						<span class="social-mark">{s.mark}</span>
						<span class="social-info">
							<strong>{s.name}</strong>
							<span>{s.handle}</span>
						</span>
						<span class="social-arrow" aria-hidden="true">↗</span>
					</a>
				{/each}
			</div>
		</div>
	</section>
</main>

<footer class="footer">
	<div class="wrap footer-inner">
		<p>© 2026 Apriyudha — Cirebon, Indonesia</p>
		<p class="mono footer-note">Built with SvelteKit · Deployed on Vercel</p>
	</div>
</footer>

<style>
	/* Announcement bar */
	.announce {
		background: #000;
		color: #fff;
		text-align: center;
		font-size: 13px;
		font-weight: 500;
		padding: 10px 16px;
	}
	.announce a:hover {
		text-decoration: underline;
	}

	/* Nav */
	.nav {
		position: sticky;
		top: 0;
		z-index: 50;
		background: rgba(255, 255, 255, 0.85);
		backdrop-filter: blur(12px);
		border-bottom: 1px solid var(--line);
	}
	.nav-inner {
		display: flex;
		align-items: center;
		justify-content: space-between;
		height: 64px;
	}
	.wordmark {
		font-size: 19px;
		font-weight: 800;
		letter-spacing: -0.03em;
	}
	.wordmark .dot {
		color: var(--accent);
	}
	.nav-links {
		display: flex;
		gap: 32px;
		font-size: 15px;
		font-weight: 500;
		color: var(--muted);
	}
	.nav-links a:hover {
		color: #000;
	}
	.btn-sm {
		padding: 9px 18px;
		font-size: 14px;
	}

	/* Hero */
	.hero {
		position: relative;
		background: linear-gradient(180deg, #fdf8fd 0%, #ffffff 70%);
		overflow: hidden;
		padding-top: 110px;
	}
	.hero-inner {
		position: relative;
		z-index: 2;
		text-align: center;
		padding-bottom: 90px;
	}
	.hero h1 {
		font-size: clamp(44px, 6.5vw, 72px);
		margin-top: 22px;
	}
	.hero h1 .accent {
		color: var(--accent);
	}
	.hero-sub {
		color: var(--muted);
		font-size: clamp(17px, 2vw, 20px);
		line-height: 1.6;
		max-width: 620px;
		margin: 26px auto 0;
	}
	.hero-cta {
		display: flex;
		gap: 14px;
		justify-content: center;
		margin-top: 38px;
		flex-wrap: wrap;
	}
	.blob {
		position: absolute;
		border-radius: 50%;
		filter: blur(70px);
		opacity: 0.55;
		z-index: 1;
		animation: drift 14s ease-in-out infinite alternate;
	}
	.blob-a {
		width: 340px;
		height: 340px;
		background: #d9c8ff;
		top: 8%;
		left: 6%;
	}
	.blob-b {
		width: 300px;
		height: 300px;
		background: #bcd6ff;
		top: 22%;
		right: 4%;
		animation-delay: -5s;
	}
	.blob-c {
		width: 220px;
		height: 220px;
		background: #ffd9ec;
		bottom: 18%;
		left: 38%;
		animation-delay: -9s;
	}
	@keyframes drift {
		from {
			transform: translate(0, 0) scale(1);
		}
		to {
			transform: translate(24px, -28px) scale(1.08);
		}
	}

	/* Marquee */
	.marquee {
		position: relative;
		z-index: 2;
		background: #000;
		color: #fff;
		overflow: hidden;
		padding: 18px 0;
	}
	.marquee-track {
		display: flex;
		gap: 28px;
		width: max-content;
		animation: scroll 26s linear infinite;
		font-size: 22px;
		font-weight: 700;
		letter-spacing: -0.02em;
		text-transform: uppercase;
		white-space: nowrap;
	}
	.marquee-track i {
		font-style: normal;
		color: var(--accent);
	}
	@keyframes scroll {
		to {
			transform: translateX(-50%);
		}
	}

	/* About */
	.about-grid {
		display: grid;
		grid-template-columns: 380px 1fr;
		gap: 72px;
		align-items: start;
	}
	.photo-card {
		margin: 0;
	}
	.photo-card img {
		width: 100%;
		aspect-ratio: 1;
		object-fit: cover;
		border-radius: var(--radius);
		border: 1px solid var(--line);
	}
	.photo-card figcaption {
		display: flex;
		flex-direction: column;
		margin-top: 16px;
	}
	.photo-card figcaption strong {
		font-size: 17px;
		letter-spacing: -0.02em;
	}
	.photo-card figcaption span {
		color: var(--muted);
		font-size: 14px;
	}
	.about-text h2 {
		font-size: clamp(30px, 3.8vw, 44px);
		margin: 18px 0 22px;
	}
	.about-text p {
		color: var(--muted);
		font-size: 17px;
		line-height: 1.7;
		margin-bottom: 16px;
	}
	.facts {
		list-style: none;
		margin: 32px 0 0;
		padding: 0;
		border-top: 1px solid var(--line);
	}
	.facts li {
		display: flex;
		justify-content: space-between;
		gap: 24px;
		padding: 14px 0;
		border-bottom: 1px solid var(--line);
		font-size: 15px;
	}
	.facts li span {
		color: var(--muted);
	}
	.facts li strong {
		font-weight: 600;
		text-align: right;
	}

	/* Projects */
	.projects {
		background: var(--bg-soft);
	}
	.project-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 28px;
	}
	.project-card {
		background: #fff;
		border: 1px solid var(--line);
		border-radius: var(--radius);
		overflow: hidden;
		display: flex;
		flex-direction: column;
		transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease;
	}
	.project-card:hover {
		transform: translateY(-4px);
		border-color: var(--line-strong);
		box-shadow: 0 16px 40px rgba(0, 0, 0, 0.07);
	}
	.project-visual {
		aspect-ratio: 16 / 10;
		background: var(--surface);
		border-bottom: 1px solid var(--line);
		padding: 20px;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.project-body {
		padding: 26px;
		display: flex;
		flex-direction: column;
		flex: 1;
	}
	.project-kind {
		font-size: 11px;
		letter-spacing: 0.14em;
		color: var(--muted);
		margin-bottom: 10px;
	}
	.project-body h3 {
		font-size: 23px;
		margin-bottom: 10px;
	}
	.project-desc {
		color: var(--muted);
		font-size: 15px;
		line-height: 1.65;
		flex: 1;
	}
	.tags {
		display: flex;
		flex-wrap: wrap;
		gap: 8px;
		margin: 20px 0 18px;
	}
	.tags span {
		font-size: 12px;
		font-weight: 500;
		padding: 5px 11px;
		border-radius: 999px;
		background: var(--surface);
		border: 1px solid var(--line);
	}
	.project-link {
		font-size: 14px;
		font-weight: 600;
		color: var(--accent);
	}
	.project-link:hover {
		text-decoration: underline;
	}

	/* Mini visuals */
	.mini-window {
		width: 100%;
		background: #0b0d12;
		border-radius: 12px;
		overflow: hidden;
		color: #e8eaf0;
		box-shadow: 0 10px 28px rgba(0, 0, 0, 0.18);
	}
	.mini-bar {
		display: flex;
		align-items: center;
		gap: 6px;
		padding: 9px 12px;
		background: #161a23;
		font-family: 'JetBrains Mono', monospace;
		font-size: 11px;
		color: #8b93a7;
	}
	.mini-bar i {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background: #3a4152;
	}
	.mini-bar span {
		margin-left: 6px;
	}
	.mini-lines {
		padding: 14px 16px 16px;
		display: flex;
		flex-direction: column;
		gap: 8px;
		font-family: 'JetBrains Mono', monospace;
		font-size: 11.5px;
	}
	.mini-lines .l-title {
		color: #fff;
		font-weight: 500;
		margin-bottom: 2px;
	}
	.mini-lines .l {
		height: 7px;
		border-radius: 4px;
		background: #232838;
	}
	.mini-lines .l.short {
		width: 62%;
	}
	.mini-lines .l.mid {
		width: 82%;
	}
	.mini-lines .l-check {
		color: #5eeaa0;
		margin-top: 2px;
	}
	.mini-chart {
		width: 100%;
	}
	.mini-stats {
		display: flex;
		gap: 18px;
		margin-bottom: 12px;
	}
	.mini-stats small {
		display: block;
		font-size: 10px;
		letter-spacing: 0.08em;
		text-transform: uppercase;
		color: var(--muted);
	}
	.mini-stats strong {
		font-size: 17px;
		letter-spacing: -0.02em;
	}
	.mini-stats strong.on {
		color: #0a9d4d;
	}
	.mini-chart svg {
		width: 100%;
		height: auto;
	}
	.mini-table {
		width: 100%;
		background: #fff;
		border: 1px solid var(--line);
		border-radius: 12px;
		overflow: hidden;
		font-family: 'JetBrains Mono', monospace;
		font-size: 11.5px;
	}
	.mini-row {
		display: grid;
		grid-template-columns: 1.2fr 1fr 0.8fr;
		padding: 9px 14px;
		border-bottom: 1px solid var(--line);
	}
	.mini-row.head {
		background: var(--surface);
		color: var(--muted);
		text-transform: uppercase;
		font-size: 10px;
		letter-spacing: 0.1em;
	}
	.mini-foot {
		display: flex;
		justify-content: space-between;
		padding: 9px 14px;
		background: var(--surface);
		color: var(--muted);
	}
	.mini-foot .ok {
		color: #0a9d4d;
		font-weight: 500;
	}

	/* Socials */
	.social-grid {
		display: grid;
		grid-template-columns: repeat(5, 1fr);
		gap: 16px;
	}
	.social-card {
		display: flex;
		align-items: center;
		gap: 14px;
		padding: 20px;
		border: 1px solid var(--line);
		border-radius: 16px;
		background: #fff;
		transition: transform 0.2s ease, border-color 0.2s ease;
	}
	.social-card:hover {
		transform: translateY(-3px);
		border-color: #000;
	}
	.social-mark {
		width: 42px;
		height: 42px;
		flex-shrink: 0;
		border-radius: 12px;
		background: #000;
		color: #fff;
		display: flex;
		align-items: center;
		justify-content: center;
		font-family: 'JetBrains Mono', monospace;
		font-size: 14px;
		font-weight: 500;
	}
	.social-info {
		display: flex;
		flex-direction: column;
		min-width: 0;
	}
	.social-info strong {
		font-size: 15px;
		letter-spacing: -0.01em;
	}
	.social-info span {
		font-size: 13px;
		color: var(--muted);
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
	.social-arrow {
		margin-left: auto;
		color: var(--muted);
		font-size: 15px;
	}

	/* Footer */
	.footer {
		border-top: 1px solid var(--line);
		padding: 36px 0;
	}
	.footer-inner {
		display: flex;
		justify-content: space-between;
		gap: 16px;
		flex-wrap: wrap;
		font-size: 14px;
		color: var(--muted);
	}
	.footer-note {
		font-size: 12px;
		letter-spacing: 0.06em;
	}

	/* Reveal */
	.reveal {
		opacity: 0;
		transform: translateY(18px);
		transition: opacity 0.7s ease, transform 0.7s ease;
	}
	.reveal.visible {
		opacity: 1;
		transform: translateY(0);
	}

	@media (max-width: 900px) {
		.about-grid {
			grid-template-columns: 1fr;
			gap: 40px;
		}
		.photo-card {
			max-width: 380px;
		}
		.project-grid {
			grid-template-columns: 1fr;
		}
		.social-grid {
			grid-template-columns: repeat(2, 1fr);
		}
		.nav-links {
			display: none;
		}
	}
	@media (max-width: 520px) {
		.social-grid {
			grid-template-columns: 1fr;
		}
		.hero {
			padding-top: 72px;
		}
	}
</style>
