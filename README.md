<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CreatoEdits — Varun | Vertical Video Editor, Bhopal</title>
    <meta name="description" content="Creato.Edits — vertical-first video editing by Varun, based in Bhopal.">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link
        href="https://fonts.googleapis.com/css2?family=Unbounded:wght@400;600;800;900&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap"
        rel="stylesheet">
    <style>
        :root {
            --bg: #08080a;
            --bg-elev: #0e0e11;
            --bg-card: #141417;
            --line: rgba(255, 255, 255, 0.09);
            --line-strong: rgba(255, 255, 255, 0.2);
            --text: #f5f5f3;
            --muted: #8d8d95;
            --blue: #6C90E8;
            --green: #A9E86C;
            --mint: #9BEFC4;
            --magenta: #C94FC0;
            --purple: #8B6CE8;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: var(--bg);
            color: var(--text);
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            line-height: 1.65;
        }

        ::selection {
            background: var(--magenta);
            color: #08080a;
        }

        .mono {
            font-family: 'JetBrains Mono', monospace;
        }

        .wrap {
            max-width: 1180px;
            margin: 0 auto;
            padding: 0 32px;
        }

        img {
            max-width: 100%;
            display: block;
        }

        /* ---------- nav ---------- */
        header {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 100;
            backdrop-filter: blur(14px);
            background: rgba(8, 8, 10, 0.75);
            border-bottom: 0.5px solid var(--line);
        }

        nav {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 14px 32px;
            max-width: 1180px;
            margin: 0 auto;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
            color: var(--text);
        }

        .brand img {
            width: 34px;
            height: 34px;
            object-fit: contain;
        }

        .brand-name {
            font-family: 'Unbounded', sans-serif;
            font-weight: 600;
            font-size: 15px;
            letter-spacing: 0.2px;
        }

        .brand-name .dot {
            color: var(--magenta);
        }

        .navlinks {
            display: flex;
            gap: 34px;
            list-style: none;
        }

        .navlinks a {
            color: var(--muted);
            text-decoration: none;
            font-size: 14px;
            font-weight: 500;
            transition: color 0.25s;
            position: relative;
        }

        .navlinks a:hover {
            color: var(--text);
        }

        .navlinks a::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -5px;
            width: 0;
            height: 1px;
            background: var(--green);
            transition: width 0.25s;
        }

        .navlinks a:hover::after {
            width: 100%;
        }

        @media(max-width:720px) {
            .navlinks {
                display: none;
            }
        }

        .btn {
            font-family: 'Inter', sans-serif;
            font-weight: 600;
            font-size: 13.5px;
            padding: 11px 22px;
            border-radius: 100px;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s, color 0.25s;
        }

        .btn-primary {
            background: var(--text);
            color: var(--bg);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 26px rgba(169, 232, 108, 0.2);
        }

        .btn-ghost {
            border: 0.5px solid var(--line-strong);
            color: var(--text);
        }

        .btn-ghost:hover {
            border-color: var(--green);
            color: var(--green);
            transform: translateY(-2px);
        }

        /* ---------- hero ---------- */
        .hero {
            position: relative;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 150px 32px 90px;
            z-index: 2;
            overflow: hidden;
        }

        .hero-glow {
            position: absolute;
            top: -10%;
            left: 50%;
            transform: translateX(-50%);
            width: 900px;
            height: 900px;
            pointer-events: none;
            z-index: -1;
            background: radial-gradient(circle, rgba(139, 108, 232, 0.14) 0%, transparent 60%);
        }

        .hero-mark {
            width: 150px;
            opacity: 0;
            animation: pop-in 0.9s cubic-bezier(.2, .9, .25, 1.2) forwards 0.1s;
        }

        @keyframes pop-in {
            from {
                opacity: 0;
                transform: scale(0.6) rotate(-8deg);
            }

            to {
                opacity: 1;
                transform: scale(1) rotate(0deg);
            }
        }

        .eyebrow {
            display: inline-flex;
            align-items: center;
            gap: 9px;
            margin-top: 26px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: var(--muted);
            letter-spacing: 1.5px;
            text-transform: uppercase;
            opacity: 0;
            animation: fadeUp 0.8s ease forwards 0.5s;
        }

        .eyebrow::before {
            content: '';
            width: 7px;
            height: 7px;
            border-radius: 50%;
            background: var(--green);
            animation: pulse 1.6s ease-in-out infinite;
        }

        @keyframes pulse {

            0%,
            100% {
                opacity: 1;
            }

            50% {
                opacity: 0.25;
            }
        }

        .hero h1 {
            font-family: 'Unbounded', sans-serif;
            font-weight: 800;
            font-size: clamp(42px, 8.4vw, 104px);
            line-height: 0.98;
            letter-spacing: -1px;
            margin-top: 22px;
        }

        .hero h1 .line {
            display: block;
            opacity: 0;
            animation: fadeUp 0.9s ease forwards;
        }

        .hero h1 .line1 {
            animation-delay: 0.65s;
        }

        .hero h1 .line2 {
            animation-delay: 0.85s;
            background: linear-gradient(100deg, var(--blue) 0%, var(--green) 30%, var(--magenta) 65%, var(--purple) 100%);
            background-size: 220% 100%;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: fadeUp 0.9s ease forwards 0.85s, shimmer 7s ease-in-out infinite 1.6s;
        }

        @keyframes shimmer {

            0%,
            100% {
                background-position: 0% 50%;
            }

            50% {
                background-position: 100% 50%;
            }
        }

        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(22px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero-sub {
            max-width: 520px;
            margin: 26px auto 0;
            font-size: 16.5px;
            color: var(--muted);
            opacity: 0;
            animation: fadeUp 0.9s ease forwards 1.05s;
        }

        .hero-sub strong {
            color: var(--text);
            font-weight: 600;
        }

        .hero-cta {
            display: flex;
            gap: 14px;
            margin-top: 36px;
            flex-wrap: wrap;
            justify-content: center;
            opacity: 0;
            animation: fadeUp 0.9s ease forwards 1.2s;
        }

        .shard {
            position: absolute;
            pointer-events: none;
            z-index: -1;
            opacity: 0.5;
        }

        .shard-1 {
            width: 60px;
            height: 52px;
            top: 20%;
            left: 8%;
            background: linear-gradient(135deg, var(--blue), var(--green));
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
            animation: drift-a 10s ease-in-out infinite;
        }

        .shard-2 {
            width: 38px;
            height: 34px;
            top: 68%;
            left: 14%;
            background: linear-gradient(135deg, var(--magenta), var(--purple));
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
            animation: drift-b 12s ease-in-out infinite;
        }

        .shard-3 {
            width: 24px;
            height: 80px;
            top: 26%;
            left: 88%;
            background: linear-gradient(135deg, var(--green), var(--mint));
            clip-path: polygon(30% 0%, 70% 0%, 40% 100%, 0% 100%);
            animation: drift-a 14s ease-in-out infinite reverse;
        }

        .shard-4 {
            width: 46px;
            height: 40px;
            top: 72%;
            left: 84%;
            background: linear-gradient(135deg, var(--purple), var(--magenta));
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
            animation: drift-b 11s ease-in-out infinite;
        }

        @media(max-width:720px) {
            .shard {
                display: none;
            }
        }

        @keyframes drift-a {

            0%,
            100% {
                transform: translate(0, 0) rotate(0deg);
            }

            50% {
                transform: translate(14px, -20px) rotate(10deg);
            }
        }

        @keyframes drift-b {

            0%,
            100% {
                transform: translate(0, 0) rotate(0deg);
            }

            50% {
                transform: translate(-14px, 16px) rotate(-8deg);
            }
        }

        /* ---------- angled divider ---------- */
        .divider {
            position: relative;
            height: 70px;
            margin-top: -1px;
            z-index: 3;
            background: var(--bg-elev);
            clip-path: polygon(0 100%, 100% 0, 100% 100%);
        }

        /* ---------- ticker ---------- */
        .timeline-strip {
            position: relative;
            border-top: 0.5px solid var(--line);
            border-bottom: 0.5px solid var(--line);
            padding: 14px 0;
            overflow: hidden;
            background: var(--bg-elev);
            z-index: 2;
        }

        .ticker-track {
            display: flex;
            gap: 44px;
            white-space: nowrap;
            width: max-content;
            animation: scroll-left 24s linear infinite;
        }

        .ticker-track span {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12.5px;
            color: var(--muted);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .ticker-track span::before {
            content: '//';
            color: var(--magenta);
        }

        @keyframes scroll-left {
            from {
                transform: translateX(0);
            }

            to {
                transform: translateX(-50%);
            }
        }

        /* ---------- sections ---------- */
        section {
            position: relative;
            z-index: 2;
            padding: 110px 0;
        }

        .section-head {
            margin-bottom: 52px;
            max-width: 600px;
        }

        .kicker {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: var(--green);
            letter-spacing: 1.5px;
            text-transform: uppercase;
            margin-bottom: 14px;
            display: block;
        }

        .section-head h2 {
            font-family: 'Unbounded', sans-serif;
            font-weight: 800;
            font-size: clamp(30px, 4.6vw, 50px);
            letter-spacing: -0.5px;
            line-height: 1.05;
        }

        .section-head p {
            color: var(--muted);
            margin-top: 16px;
            font-size: 15px;
        }

        .reveal {
            opacity: 0;
            transform: translateY(26px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }

        .reveal.in {
            opacity: 1;
            transform: translateY(0);
        }

        /* ---------- work grid ---------- */
        .reel-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 18px;
            perspective: 900px;
        }

        @media(max-width:980px) {
            .reel-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        @media(max-width:620px) {
            .reel-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        .reel-card {
            position: relative;
            aspect-ratio: 9/16;
            border-radius: 12px;
            overflow: hidden;
            background: var(--bg-card);
            border: 0.5px solid var(--line);
            border-top: 3px solid var(--edge, var(--blue));
            cursor: pointer;
            transition: transform 0.35s ease, border-color 0.35s ease, box-shadow 0.35s ease;
            transform-style: preserve-3d;
        }

        .reel-card:hover {
            transform: translateY(-8px) rotateX(4deg) rotateY(-4deg);
            box-shadow: 0 16px 32px rgba(0, 0, 0, 0.35);
        }

        .reel-card video,
        .reel-card .reel-fallback {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .reel-fallback {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 10px;
            color: var(--muted);
            background: linear-gradient(160deg, rgba(255, 255, 255, 0.03), transparent);
        }

        .reel-fallback .num {
            font-family: 'Unbounded', sans-serif;
            font-weight: 800;
            font-size: 28px;
            color: var(--line-strong);
        }

        .reel-fallback .label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 9.5px;
            letter-spacing: 1px;
        }

        .reel-tag {
            position: absolute;
            top: 9px;
            left: 9px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 9.5px;
            color: var(--muted);
            background: rgba(0, 0, 0, 0.45);
            padding: 3px 8px;
            border-radius: 100px;
            border: 0.5px solid var(--line);
            z-index: 2;
        }

        /* ---------- mute / sound toggle button ---------- */
        .mute-btn {
            position: absolute;
            bottom: 9px;
            right: 9px;
            z-index: 3;
            width: 34px;
            height: 34px;
            border-radius: 50%;
            border: 1px solid rgba(255, 255, 255, 0.25);
            background: rgba(0, 0, 0, 0.55);
            backdrop-filter: blur(4px);
            color: #fff;
            font-size: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: border-color 0.25s, background 0.25s, transform 0.2s;
        }

        .mute-btn:hover {
            border-color: var(--green);
            background: rgba(0, 0, 0, 0.75);
            transform: scale(1.08);
        }

        .mute-btn:active {
            transform: scale(0.95);
        }

        /* ---------- about ---------- */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 64px;
            align-items: start;
        }

        @media(max-width:780px) {
            .about-grid {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .about-grid {
                display: flex;
                flex-direction: column-reverse;
            }
        }

        .photo-slot {
            aspect-ratio: 4/5;
            border-radius: 16px;
            overflow: hidden;
            position: relative;
            background: var(--bg-card);
            border: 0.5px solid var(--line);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 10px;
            color: var(--muted);
        }

        .photo-slot::before {
            content: '';
            position: absolute;
            width: 70px;
            height: 60px;
            top: -18px;
            right: -18px;
            background: linear-gradient(135deg, var(--magenta), var(--purple));
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
            opacity: 0.7;
            z-index: -1;
        }

        .photo-slot img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .photo-slot .ph-icon {
            width: 54px;
            height: 54px;
            border-radius: 50%;
            border: 1px dashed var(--line-strong);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
        }

        .about-copy h3 {
            font-family: 'Unbounded', sans-serif;
            font-weight: 800;
            font-size: 30px;
            margin-bottom: 18px;
            letter-spacing: -0.5px;
        }

        .about-copy p {
            color: var(--muted);
            font-size: 15.5px;
            max-width: 560px;
            margin-bottom: 16px;
        }

        .about-copy p strong {
            color: var(--text);
            font-weight: 600;
        }

        .stat-row {
            display: flex;
            gap: 36px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .stat b {
            font-family: 'Unbounded', sans-serif;
            font-weight: 800;
            font-size: 32px;
            background: linear-gradient(100deg, var(--blue), var(--green), var(--magenta));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: block;
        }

        .stat span {
            font-size: 11.5px;
            color: var(--muted);
            font-family: 'JetBrains Mono', monospace;
            letter-spacing: 0.5px;
        }

        /* ---------- contact ---------- */
        .contact-card {
            position: relative;
            border: 0.5px solid var(--line);
            border-radius: 20px;
            padding: 56px;
            background: linear-gradient(160deg, rgba(108, 144, 232, 0.05), rgba(201, 79, 192, 0.05));
            display: grid;
            grid-template-columns: 1.2fr 1fr;
            gap: 48px;
            overflow: hidden;
        }

        .contact-card::after {
            content: '';
            position: absolute;
            width: 180px;
            height: 150px;
            bottom: -40px;
            right: -40px;
            background: linear-gradient(135deg, var(--green), var(--blue));
            opacity: 0.08;
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
        }

        @media(max-width:780px) {
            .contact-card {
                grid-template-columns: 1fr;
                padding: 32px;
            }
        }

        .contact-card h2 {
            font-family: 'Unbounded', sans-serif;
            font-weight: 800;
            font-size: clamp(28px, 4.6vw, 44px);
            line-height: 1.08;
            letter-spacing: -0.5px;
        }

        .contact-card>div:first-child p {
            color: var(--muted);
            margin-top: 16px;
            max-width: 380px;
        }

        .contact-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
            position: relative;
            z-index: 1;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 14px;
        }

        .contact-item .ic {
            width: 36px;
            height: 36px;
            border-radius: 10px;
            flex-shrink: 0;
            background: var(--bg-card);
            border: 0.5px solid var(--line);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 15px;
        }

        .contact-item a,
        .contact-item span.val {
            color: var(--text);
            text-decoration: none;
            font-weight: 600;
            font-size: 14.5px;
        }

        .contact-item a:hover {
            color: var(--green);
        }

        .contact-item .lbl {
            display: block;
            font-size: 10.5px;
            color: var(--muted);
            font-family: 'JetBrains Mono', monospace;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            margin-bottom: 2px;
        }

        footer {
            padding: 34px 0;
            border-top: 0.5px solid var(--line);
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--muted);
            font-size: 12.5px;
            flex-wrap: wrap;
            gap: 12px;
            z-index: 2;
            position: relative;
        }

        footer .flogo {
            display: flex;
            align-items: center;
            gap: 9px;
        }

        footer .flogo img {
            width: 20px;
            height: 20px;
            object-fit: contain;
        }

        footer .mono {
            color: var(--line-strong);
        }

        a:focus-visible,
        button:focus-visible {
            outline: 2px solid var(--green);
            outline-offset: 3px;
        }

        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>

<body>

    <header>
        <nav>
            <a href="#top" class="brand">
                <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPAAAADwCAIAAACxN37FAAAdOklEQVR42u2deZwV1Zn3n+csVXfpbpp9h2YRRURFQQhoooAaI1FMVIxmkmjAGeNEzWvMRsZo3EJMNKPvhCQY0YxZdGKiToxRxKAmxh0XUARDEAFBlm56uffWcp5n/jjNtaEbaE23Md3P93M/cLturad+9dTvPHXOKQBBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEDoM1FoDADNLWQj/rCJG9BJGRCkNoWuJ+yeLFiEgAAPsHqT9XwgdFbtxzw28v8fZoVvvkLW9h5X8Y8vw79znll+8vrDlvwgALcWGzbaBgYEBAZj98gxcjsTMjIjMzeolIjzooIN8uGbmXVva1z6/K3037yUAMgACwzvlgbsuFf+lfDx7TN9jbXv8hOiPr/l421xJy0uU27HdNje321Z2nZPmk7GXZVuvtrwz5ZXsd7utj6LlzG3Oubdl97aVva2tlcLamNLmGW9eya7yaT7MspD3I/6W+4y7mwo/CVuvBxERkchdddVVZtWqVXKfEroGmzZtMuKjhS6AUoqIgiAwkt8QugC8CyVlIXSdFAeACFroWt5DikAQQQuCCFoQxEMLgkRoQQQtCCJoQfhgeWgUQQsSoQXhAxujRdCCRGhBEEELgghaEETQgghaELoADNLAX+hSSNpO6EpylggtdC3LIR5a6FIRWiyH0LUQQQsiaEEQQQuCCFoQ3gWS5RC6FNLrW+hqMVoELXSpGC2CFqRSKAgf0EqhWA5BLIcgfEDlLJZDEMshCGI5BEEsR9coZEQFiCix432xHEZKobML+Z0Xov7j3wTb5SM0iqA7NTaDUnbs0Zdlex24/oXbt/xtKaJiJimazkPug51XPVHMPO6YC8Yee3GvwYeNn3ldjz4HMpN4j061HFK4nRScFRNV9xk57rgLo8JGdDtQwaiJX2zPC6+Fv8dyiKA7S9EAPGnWfJvroZGCTA64UD30Q/1HzGAmRC0lJJbjn8pskBs+bvrIyaenpTobBEobGxiEuGbCXGMy0FxBFDrccoigOyU2gzbB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"
                    alt="Creato.Edits logo">
                <span class="brand-name">CREATO<span class="dot">.</span>EDITS</span>
            </a>
            <ul class="navlinks">
                <li><a href="#work">Work</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <a href="#contact" class="btn btn-ghost">Hire me</a>
        </nav>
    </header>

    <main id="top">

        <section class="hero">
            <div class="hero-glow"></div>
            <div class="shard shard-1"></div>
            <div class="shard shard-2"></div>
            <div class="shard shard-3"></div>
            <div class="shard shard-4"></div>

            <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAggAAAGyCAIAAAAOJ6u6AABzHklEQVR42u2deZwV1Zn3n+csVXfpbpp9h2YRRURFQQhoooAaI1FMVIxmkmjAGeNEzWvMRsZo3EJMNKPvhCQY0YxZdGKiToxRxKAmxh0XUARDEAFBlm56uffWcp5n/jjNtaEbaE23Md3P93M/cLturad+9dTvPHXOKQBBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEDoM1FoDADNLWQj/rCJG9BJGRCkNoWuJ+yeLFiEgAAPsHqT9XwgdFbtxzw28v8fZoVvvkLW9h5X8Y8vw79znll+8vrDlvwgALcWGzbaBgYEBAZj98gxcjsTMjIjMzeolIjzooIN8uGbmXVva1z6/K3037yUAMgACwzvlgbsuFf+lfDx7TN9jbXv8hOiPr/l421xJy0uU27HdNje321Z2nZPmk7GXZVuvtrwz5ZXsd7utj6LlzG3Oubdl97aVva2tlcLamNLmGW9eya7yaT7MspD3I/6W+4y7mwo/CVuvBxERkchdddVVZtWqVXKfEroGmzZtMuKjhS6AUoqIgiAwkt8QugC8CyVlIXSdFAeACFroWt5DikAQQQuCCFoQxEMLgkRoQQQtCCJoQfhgeWgUQQsSoQXhAxujRdCCRGhBEEELgghaEETQgghaELoADNLAX+hSSNpO6EpylggtdC3LIR5a6FIRWiyH0LUQQQsiaEEQQQuCCFoQ3gWS5RC6FNLrW+hqMVoELXSpGC2CFqRSKAgf0EqhWA5BLIcgfEDlLJZDEMshCGI5BEEsR9coZEQFiCix432xHEZKobML+Z0Xov7j3wTb5SM0iqA7NTaDUnbs0Zdlex24/oXbt/xtKaJiJimazkPug51XPVHMPO6YC8Yee3GvwYeNn3ldjz4HMpN4j061HFK4nRScFRNV9xk57rgLo8JGdDtQwaiJX2zPC6+Fv8dyiKA7S9EAPGnWfJvroZGCTA64UD30Q/1HzGAmRC0lJJbjn8pskBs+bvrIyaenpTobBEobGxiEuGbCXGMy0FxBFDrccoigOyU2gzbB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"
                alt="Creato.Edits" class="hero-mark">

            <span class="eyebrow">Bhopal &middot; Vertical video editor</span>
            <h1>
                <span class="line line1">FIRST FRAME</span>
                <span class="line line2">TO FINAL HOOK.</span>
            </h1>
            <p class="hero-sub">
                I'm <strong>Varun</strong>. I cut vertical-first video for creators and brands &mdash;
                reels, shorts and stories, paced and graded to hold attention till the last second.
            </p>
            <div class="hero-cta">
                <a href="#work" class="btn btn-primary">View the work</a>
                <a href="#contact" class="btn btn-ghost">Start a project</a>
            </div>
        </section>

        <div class="divider"></div>

        <div class="timeline-strip">
            <div class="ticker-track">
                <span>REEL EDITING</span><span>COLOR GRADING</span><span>SOUND DESIGN</span>
                <span>MOTION TEXT</span><span>SHORT FORM</span><span>VERTICAL FIRST</span>
                <span>REEL EDITING</span><span>COLOR GRADING</span><span>SOUND DESIGN</span>
                <span>MOTION TEXT</span><span>SHORT FORM</span><span>VERTICAL FIRST</span>
            </div>
        </div>

        <section id="work" class="wrap">
            <div class="section-head reveal">
                <span class="kicker">Portfolio</span>
                <h2>MADE TO KEEP WATCHING</h2>
                <p>A mix of ad films, mythological drama and short-form work &mdash; all cut vertical-first. Tap the
                    speaker icon to turn sound on.</p>
            </div>
            <div class="reel-grid">
                <div class="reel-card reveal" style="--edge:var(--blue); transition-delay:0.02s">
                    <div class="reel-tag">01</div>
                    <video src="1.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--green); transition-delay:0.04s">
                    <div class="reel-tag">02</div>
                    <video src="2.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--magenta); transition-delay:0.06s">
                    <div class="reel-tag">03</div>
                    <video src="3.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--purple); transition-delay:0.08s">
                    <div class="reel-tag">04</div>
                    <video src="4.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--mint); transition-delay:0.10s">
                    <div class="reel-tag">05</div>
                    <video src="6.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--blue); transition-delay:0.12s">
                    <div class="reel-tag">06</div>
                    <video src="7.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--green); transition-delay:0.14s">
                    <div class="reel-tag">07</div>
                    <video src="8.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--magenta); transition-delay:0.16s">
                    <div class="reel-tag">08</div>
                    <video src="9.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--purple); transition-delay:0.18s">
                    <div class="reel-tag">09</div>
                    <video src="10.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--mint); transition-delay:0.20s">
                    <div class="reel-tag">10</div>
                    <video src="" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--blue); transition-delay:0.22s">
                    <div class="reel-tag">11</div>
                    <video src="11.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--green); transition-delay:0.24s">
                    <div class="reel-tag">12</div>
                    <video src="12.mp4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
                <div class="reel-card reveal" style="--edge:var(--magenta); transition-delay:0.26s">
                    <div class="reel-tag">13</div>
                    <video src="13.MP4" autoplay muted loop playsinline preload="metadata"></video>
                    <button class="mute-btn" aria-label="Toggle sound">&#128264;</button>
                </div>
            </div>
        </section>

        <section id="about" class="wrap">
            <div class="about-grid">
                <div class="about-copy reveal">
                    <span class="kicker">About</span>
                    <h3>Hi, I'm Varun.</h3>
                    <p>I run <strong>Creato.Edits</strong> out of <strong>Bhopal</strong>, editing vertical-first
                        content for creators and brands. Every project comes down to three things: pacing that
                        keeps people watching, sound design that carries the emotion, and color that gives the
                        footage a mood.</p>
                    <p>The thirteen edits above are a mix of client work and personal projects &mdash; scroll up
                        to see them, or send me your footage and let's find out what it becomes.</p>
                    <div class="stat-row">
                        <div class="stat"><b>13</b><span>EDITS SHOWCASED</span></div>
                        <div class="stat"><b>9:16</b><span>VERTICAL FIRST</span></div>
                        <div class="stat"><b>BPL</b><span>BASED IN BHOPAL</span></div>
                    </div>
                </div>
                <div class="photo-slot reveal">
                     <img src="1.jpg" alt="">
                    <div class="varun soni  ">varun soni </div>
                    <span style="font-size:11.5px;font-family:'JetBrains Mono',monospace;"></span>
                </div>
            </div>
        </section>

        <section id="contact" class="wrap">
            <div class="contact-card reveal">
                <div>
                    <span class="kicker">Contact</span>
                    <h2>Let's start<br>your edit.</h2>
                    <p>Send your footage or brief my way &mdash; I usually reply within a day.</p>
                </div>
                <div class="contact-list">
                    <div class="contact-item">
                        <div class="ic">&#9993;</div>
                        <div><span class="lbl">Email</span><a
                                href="mailto:creato9977@gmail.com">creato9977@gmail.com</a></div>
                    </div>
                    <div class="contact-item">
                        <div class="ic">&#9742;</div>
                        <div><span class="lbl">Phone</span><a href="tel:+919977978575">+91 99779 78575</a></div>
                    </div>
                    <div class="contact-item">
                        <div class="ic">&#128205;</div>
                        <div><span class="lbl">Location</span><span class="val">Bhopal, Madhya Pradesh</span></div>
                    </div>
                    <div class="contact-item">
                        <div class="ic">&#9997;</div>
                        <div><span class="lbl">Founder</span><span class="val">Varun</span></div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <footer class="wrap">
        <div class="flogo">
            <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPAAAADwCAIAAACxN37FAAAdOklEQVR42u2deZwV1Zn3n+csVXfpbpp9h2YRRURFQQhoooAaI1FMVIxmkmjAGeNEzWvMRsZo3EJMNKPvhCQY0YxZdGKiToxRxKAmxh0XUARDEAFBlm56uffWcp5n/jjNtaEbaE23Md3P93M/cLturad+9dTvPHXOKQBBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEARBEDoM1FoDADNLWQj/rCJG9BJGRCkNoWuJ+yeLFiEgAAPsHqT9XwgdFbtxzw28v8fZoVvvkLW9h5X8Y8vw79znll+8vrDlvwgALcWGzbaBgYEBAZj98gxcjsTMjIjMzeolIjzooIN8uGbmXVva1z6/K3037yUAMgACwzvlgbsuFf+lfDx7TN9jbXv8hOiPr/l421xJy0uU27HdNje321Z2nZPmk7GXZVuvtrwz5ZXsd7utj6LlzG3Oubdl97aVva2tlcLamNLmGW9eya7yaT7MspD3I/6W+4y7mwo/CVuvBxERkchdddVVZtWqVXKfEroGmzZtMuKjhS6AUoqIgiAwkt8QugC8CyVlIXSdFAeACFroWt5DikAQQQuCCFoQxEMLgkRoQQQtCCJoQfhgeWgUQQsSoQXhAxujRdCCRGhBEEELgghaEETQgghaELoADNLAX+hSSNpO6EpylggtdC3LIR5a6FIRWiyH0LUQQQsiaEEQQQuCCFoQ3gWS5RC6FNLrW+hqMVoELXSpGC2CFqRSKAgf0EqhWA5BLIcgfEDlLJZDEMshCGI5BEEsR9coZEQFiCix432xHEZKobML+Z0Xov7j3wTb5SM0iqA7NTaDUnbs0Zdlex24/oXbt/xtKaJiJimazkPug51XPVHMPO6YC8Yee3GvwYeNn3ldjz4HMpN4j061HFK4nRScFRNV9xk57rgLo8JGdDtQwaiJX2zPC6+Fv8dyiKA7S9EAPGnWfJvroZGCTA64UD30Q/1HzGAmRC0lJJbjn8pskBs+bvrIyaenpTobBEobGxiEuGbCXGMy0FxBFDrccoigOyU2gzbB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"
                alt="Creato.Edits">
            <span>&copy; <span id="year"></span> Creato.Edits &mdash; Varun, Bhopal</span>
        </div>
        <span class="mono">// EDIT.EXPORT.REPEAT</span>
    </footer>

    <script>
        document.getElementById('year').textContent = new Date().getFullYear();

        const revealEls = document.querySelectorAll('.reveal');
        const io = new IntersectionObserver((entries) => {
            entries.forEach(e => {
                if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); }
            });
        }, { threshold: 0.15 });
        revealEls.forEach(el => io.observe(el));

        // ---- sound toggle for reel videos ----
        document.querySelectorAll('.reel-card').forEach(card => {
            const video = card.querySelector('video');
            const btn = card.querySelector('.mute-btn');
            if (!video || !btn) return;

            btn.addEventListener('click', (e) => {
                e.stopPropagation();

                // mute all other videos first, so only one plays with sound at a time
                document.querySelectorAll('.reel-card video').forEach(v => {
                    if (v !== video) v.muted = true;
                });
                document.querySelectorAll('.mute-btn').forEach(b => {
                    if (b !== btn) b.innerHTML = '&#128264;';
                });

                video.muted = !video.muted;
                btn.innerHTML = video.muted ? '&#128264;' : '&#128266;';
                video.play().catch(() => { });
            });

            // if a muted video scrolls out of view, keep it muted so sound doesn't
            // keep playing off-screen
            const soundObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (!entry.isIntersecting && !video.muted) {
                        video.muted = true;
                        btn.innerHTML = '&#128264;';
                    }
                });
            }, { threshold: 0.1 });
            soundObserver.observe(card);
        });
    </script>

</body>

</html>
