# Portfolio-website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ankita Roy - AI & ML Engineer Portfolio</title>
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #020617;
            --bg-secondary: #1e293b;
            --bg-tertiary: #334155;
            --text-primary: #f8fafc;
            --text-secondary: #cbd5e1;
            --text-muted: #94a3b8;
            --cyan-400: #22d3ee;
            --cyan-500: #06b6d4;
            --cyan-600: #0891b2;
            --blue-400: #60a5fa;
            --blue-500: #3b82f6;
            --purple-500: #a855f7;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.5;
            font-size: 16px;
            overflow-x: hidden;
        }

        /* Typography */
        h1 {
            font-size: 3rem;
            font-weight: 500;
            line-height: 1.2;
        }

        h2 {
            font-size: 2.5rem;
            font-weight: 500;
            line-height: 1.3;
        }

        h3 {
            font-size: 1.5rem;
            font-weight: 500;
            line-height: 1.4;
        }

        h4 {
            font-size: 1.125rem;
            font-weight: 500;
            line-height: 1.5;
        }

        p, button, label {
            font-size: 1rem;
            font-weight: 400;
            line-height: 1.5;
        }

        button {
            font-weight: 500;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            background: rgba(2, 6, 23, 0.95);
            backdrop-filter: blur(12px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            border-bottom: 1px solid #334155;
        }

        .nav-container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 64px;
        }

        .nav-logo {
            font-size: 1.25rem;
        }

        .nav-logo .highlight {
            color: var(--cyan-400);
        }

        .nav-menu {
            display: flex;
            gap: 0.25rem;
            list-style: none;
        }

        .nav-menu button {
            background: none;
            border: none;
            color: var(--text-secondary);
            padding: 0.5rem 0.75rem;
            border-radius: 0.5rem;
            cursor: pointer;
            transition: color 0.2s;
        }

        .nav-menu button:hover {
            color: var(--cyan-400);
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text-secondary);
            cursor: pointer;
            padding: 0.5rem;
        }

        .mobile-menu {
            display: none;
            background: rgba(2, 6, 23, 0.98);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid #334155;
            padding: 0.5rem;
        }

        .mobile-menu.active {
            display: block;
        }

        .mobile-menu button {
            display: block;
            width: 100%;
            text-align: left;
            background: none;
            border: none;
            color: var(--text-secondary);
            padding: 0.5rem 0.75rem;
            border-radius: 0.5rem;
            cursor: pointer;
            transition: color 0.2s;
        }

        .mobile-menu button:hover {
            color: var(--cyan-400);
        }

        /* Container */
        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 1rem;
        }

        /* Section */
        section {
            padding: 6rem 0;
            position: relative;
            overflow: hidden;
        }

        /* Hero Section */
        #home {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding-top: 4rem;
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 2fr 3fr;
            gap: 3rem;
            align-items: center;
        }

        .hero-image-wrapper {
            display: flex;
            justify-content: center;
        }

        .hero-image-container {
            position: relative;
        }

        .hero-glow {
            position: absolute;
            inset: 0;
            background: rgba(34, 211, 238, 0.2);
            border-radius: 50%;
            filter: blur(80px);
        }

        .hero-image {
            position: relative;
            width: 384px;
            height: 384px;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid rgba(51, 65, 85, 0.5);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
        }

        .hero-content {
            animation: fadeInRight 0.6s ease-out 0.2s both;
        }

        .hero-greeting {
            color: var(--cyan-400);
            margin-bottom: 0.5rem;
        }

        .hero-title {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        .hero-subtitle {
            font-size: 1.875rem;
            color: var(--text-muted);
            margin-bottom: 1.5rem;
        }

        .hero-description {
            color: var(--text-secondary);
            max-width: 42rem;
            margin-bottom: 1rem;
        }

        .hero-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            padding-top: 1rem;
        }

        .btn {
            padding: 0.75rem 1.5rem;
            border-radius: 0.5rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.2s;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            border: none;
        }

        .btn-primary {
            background: var(--cyan-600);
            color: white;
        }

        .btn-primary:hover {
            background: #0e7490;
        }

        .btn-secondary {
            background: #1e293b;
            color: white;
            border: 1px solid #334155;
        }

        .btn-secondary:hover {
            background: #334155;
        }

        .hero-socials {
            display: flex;
            gap: 1rem;
            padding-top: 0.5rem;
        }

        .social-link {
            padding: 0.625rem;
            background: rgba(30, 41, 59, 0.8);
            border-radius: 0.5rem;
            border: 1px solid #334155;
            transition: all 0.2s;
            color: var(--text-primary);
            text-decoration: none;
            display: inline-flex;
        }

        .social-link:hover {
            background: var(--cyan-600);
        }

        /* About Section */
        #about {
            background: rgba(15, 23, 42, 0.3);
        }

        .section-header {
            margin-bottom: 4rem;
        }

        .section-title {
            margin-bottom: 0.75rem;
        }

        .title-underline {
            width: 5rem;
            height: 4px;
            background: var(--cyan-500);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .about-card {
            background: rgba(30, 41, 59, 0.4);
            padding: 2rem;
            border-radius: 0.75rem;
            border: 1px solid rgba(51, 65, 85, 0.5);
        }

        .about-card h3 {
            margin-bottom: 1rem;
        }

        .about-card p {
            color: var(--text-secondary);
            margin-bottom: 1rem;
        }

        .expertise-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.75rem;
        }

        .expertise-item {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            color: var(--text-secondary);
        }

        .expertise-dot {
            width: 6px;
            height: 6px;
            background: var(--cyan-500);
            border-radius: 50%;
            flex-shrink: 0;
        }

        .highlights-grid {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .highlight-card {
            background: rgba(30, 41, 59, 0.4);
            padding: 1.5rem;
            border-radius: 0.75rem;
            border: 1px solid rgba(51, 65, 85, 0.5);
            transition: border-color 0.3s;
        }

        .highlight-card:hover {
            border-color: rgba(34, 211, 238, 0.3);
        }

        .highlight-header {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }

        .highlight-icon {
            padding: 0.75rem;
            background: rgba(34, 211, 238, 0.1);
            border-radius: 0.5rem;
        }

        .highlight-icon svg {
            width: 24px;
            height: 24px;
            color: var(--cyan-400);
        }

        .highlight-card h4 {
            margin-bottom: 0.5rem;
        }

        .highlight-card p {
            color: var(--text-muted);
        }

        /* Skills Section */
        #skills {
            position: relative;
        }

        .bg-decoration {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            pointer-events: none;
        }

        .bg-decoration-1 {
            top: 25%;
            right: -12rem;
            width: 24rem;
            height: 24rem;
            background: rgba(34, 211, 238, 0.1);
        }

        .bg-decoration-2 {
            bottom: 25%;
            left: -12rem;
            width: 24rem;
            height: 24rem;
            background: rgba(59, 130, 246, 0.1);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
            margin-bottom: 3rem;
            position: relative;
            z-index: 10;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(30, 41, 59, 0.3) 100%);
            padding: 1.5rem;
            border-radius: 1rem;
            border: 1px solid rgba(51, 65, 85, 0.5);
            transition: all 0.3s;
            backdrop-filter: blur(8px);
        }

        .skill-card:hover {
            border-color: rgba(34, 211, 238, 0.5);
            transform: translateY(-2px);
        }

        .skill-header {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            margin-bottom: 1.25rem;
        }

        .skill-icon {
            padding: 0.625rem;
            background: linear-gradient(135deg, rgba(34, 211, 238, 0.2) 0%, rgba(59, 130, 246, 0.2) 100%);
            border-radius: 0.5rem;
            transition: all 0.3s;
        }

        .skill-card:hover .skill-icon {
            background: linear-gradient(135deg, rgba(34, 211, 238, 0.3) 0%, rgba(59, 130, 246, 0.3) 100%);
        }

        .skill-icon svg {
            width: 22px;
            height: 22px;
            color: var(--cyan-400);
        }

        .skill-header h3 {
            color: var(--cyan-400);
            font-size: 1.125rem;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .skill-tag {
            padding: 0.375rem 0.75rem;
            background: rgba(2, 6, 23, 0.5);
            color: var(--text-secondary);
            border-radius: 0.5rem;
            border: 1px solid rgba(51, 65, 85, 0.4);
            font-size: 0.875rem;
            transition: all 0.2s;
            cursor: default;
        }

        .skill-tag:hover {
            border-color: rgba(34, 211, 238, 0.6);
            background: rgba(30, 41, 59, 0.5);
            color: white;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1rem;
            position: relative;
            z-index: 10;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(30, 41, 59, 0.3) 100%);
            padding: 1.5rem;
            border-radius: 0.75rem;
            border: 1px solid rgba(51, 65, 85, 0.5);
            text-align: center;
            backdrop-filter: blur(8px);
        }

        .stat-value {
            font-size: 1.875rem;
            margin-bottom: 0.5rem;
            background: linear-gradient(90deg, var(--cyan-400) 0%, var(--blue-400) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            color: var(--text-muted);
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            position: relative;
            z-index: 10;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(30, 41, 59, 0.3) 100%);
            backdrop-filter: blur(8px);
            border-radius: 1rem;
            overflow: hidden;
            transition: all 0.3s;
            border: 1px solid rgba(51, 65, 85, 0.5);
        }

        .project-card:hover {
            transform: scale(1.05);
            border-color: rgba(34, 211, 238, 0.5);
        }

        .project-image-wrapper {
            position: relative;
            height: 14rem;
            overflow: hidden;
        }

        .project-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .project-card:hover .project-image {
            transform: scale(1.1);
        }

        .project-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(180deg, transparent 0%, rgba(2, 6, 23, 0.6) 50%, #020617 100%);
        }

        .project-content {
            padding: 1.5rem;
            position: relative;
        }

        .project-content h3 {
            margin-bottom: 0.75rem;
            transition: color 0.3s;
        }

        .project-card:hover h3 {
            color: var(--cyan-400);
        }

        .project-description {
            color: var(--text-muted);
            margin-bottom: 1rem;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .project-tag {
            padding: 0.375rem 0.75rem;
            background: rgba(34, 211, 238, 0.1);
            color: var(--cyan-400);
            border-radius: 0.5rem;
            border: 1px solid rgba(34, 211, 238, 0.3);
            font-size: 0.875rem;
            transition: all 0.2s;
        }

        .project-tag:hover {
            background: rgba(34, 211, 238, 0.2);
        }

        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--cyan-400);
            text-decoration: none;
            transition: color 0.3s;
        }

        .project-link:hover {
            color: #67e8f9;
        }

        .project-link svg {
            width: 18px;
            height: 18px;
            transition: transform 0.3s;
        }

        .project-link:hover svg {
            transform: rotate(12deg);
        }

        /* Certifications Section */
        #certifications {
            background: rgba(15, 23, 42, 0.3);
        }

        .certifications-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
            position: relative;
            z-index: 10;
        }

        .cert-card {
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(30, 41, 59, 0.3) 100%);
            padding: 1.5rem;
            border-radius: 1rem;
            border: 1px solid rgba(51, 65, 85, 0.5);
            transition: all 0.3s;
            backdrop-filter: blur(8px);
            text-decoration: none;
            color: inherit;
            display: block;
        }

        .cert-card:hover {
            transform: scale(1.05);
            border-color: rgba(34, 211, 238, 0.5);
        }

        .cert-header {
            display: flex;
            align-items: flex-start;
            justify-content: space-between;
            margin-bottom: 0.75rem;
        }

        .cert-card h3 {
            margin-bottom: 0.5rem;
            transition: color 0.3s;
            flex: 1;
        }

        .cert-card:hover h3 {
            color: var(--cyan-400);
        }

        .cert-icon {
            color: var(--text-muted);
            transition: all 0.3s;
            flex-shrink: 0;
            margin-left: 0.5rem;
        }

        .cert-card:hover .cert-icon {
            color: var(--cyan-400);
            transform: translate(2px, -2px);
        }

        .cert-issuer {
            color: var(--text-muted);
            margin-bottom: 0.25rem;
        }

        .cert-date {
            color: #64748b;
            font-size: 0.875rem;
        }

        .cert-summary {
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(30, 41, 59, 0.3) 100%);
            padding: 2rem;
            border-radius: 1rem;
            border: 1px solid rgba(34, 211, 238, 0.3);
            text-align: center;
            backdrop-filter: blur(8px);
            margin-top: 3rem;
        }

        .cert-summary h3 {
            font-size: 1.5rem;
            margin-bottom: 0.75rem;
            background: linear-gradient(90deg, var(--cyan-400) 0%, var(--blue-400) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .cert-summary p {
            color: var(--text-secondary);
            max-width: 48rem;
            margin: 0 auto;
        }

        /* Contact Section */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            position: relative;
            z-index: 10;
        }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .contact-info > p {
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
        }

        .contact-links {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1.25rem;
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(30, 41, 59, 0.3) 100%);
            border-radius: 1rem;
            border: 1px solid rgba(51, 65, 85, 0.5);
            transition: all 0.3s;
            backdrop-filter: blur(8px);
            text-decoration: none;
            color: inherit;
        }

        .contact-link:hover {
            border-color: rgba(34, 211, 238, 0.5);
            transform: scale(1.05);
        }

        .contact-icon {
            padding: 0.75rem;
            background: linear-gradient(135deg, rgba(34, 211, 238, 0.2) 0%, rgba(59, 130, 246, 0.2) 100%);
            border-radius: 0.75rem;
            transition: all 0.3s;
        }

        .contact-link:hover .contact-icon {
            background: linear-gradient(135deg, rgba(34, 211, 238, 0.3) 0%, rgba(59, 130, 246, 0.3) 100%);
        }

        .contact-icon svg {
            width: 24px;
            height: 24px;
            color: var(--cyan-400);
        }

        .contact-details p:first-child {
            color: var(--text-muted);
            font-size: 0.875rem;
        }

        .contact-details p:last-child {
            color: var(--text-secondary);
            transition: color 0.3s;
        }

        .contact-link:hover .contact-details p:last-child {
            color: var(--cyan-400);
        }

        .info-cards {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .info-card {
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(30, 41, 59, 0.3) 100%);
            padding: 2rem;
            border-radius: 1rem;
            border: 1px solid rgba(51, 65, 85, 0.5);
            backdrop-filter: blur(8px);
        }

        .info-card-header {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .info-card h4 {
            margin-bottom: 0.5rem;
        }

        .info-card p {
            color: var(--text-secondary);
        }

        .info-card-small {
            color: var(--text-muted);
            font-size: 0.875rem;
        }

        .interest-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .interest-tag {
            padding: 0.375rem 0.75rem;
            background: rgba(34, 211, 238, 0.1);
            color: var(--cyan-400);
            border-radius: 0.5rem;
            border: 1px solid rgba(34, 211, 238, 0.3);
            font-size: 0.875rem;
            transition: all 0.2s;
            cursor: default;
        }

        .interest-tag:hover {
            background: rgba(34, 211, 238, 0.2);
            border-color: rgba(34, 211, 238, 0.5);
        }

        .highlight-card-special {
            background: linear-gradient(135deg, rgba(34, 211, 238, 0.1) 0%, rgba(59, 130, 246, 0.1) 25%, rgba(168, 85, 247, 0.1) 100%);
            border-color: rgba(34, 211, 238, 0.3);
        }

        .highlight-card-special h4 {
            color: var(--cyan-400);
            margin-bottom: 0.75rem;
        }

        /* Footer */
        .footer {
            text-align: center;
            margin-top: 4rem;
            padding-top: 2rem;
            border-top: 1px solid #1e293b;
        }

        .footer p {
            color: var(--text-muted);
        }

        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .fade-in {
            opacity: 0;
            animation: fadeIn 0.6s ease-out forwards;
        }

        /* Responsive */
        @media (max-width: 1024px) {
            .hero-grid {
                grid-template-columns: 1fr;
            }

            .hero-title {
                font-size: 3rem;
            }

            .about-grid {
                grid-template-columns: 1fr;
            }

            .skills-grid,
            .projects-grid,
            .certifications-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            h1 {
                font-size: 2.5rem;
            }

            h2 {
                font-size: 2rem;
            }

            .hero-image {
                width: 288px;
                height: 288px;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.5rem;
            }

            .skills-grid,
            .projects-grid,
            .certifications-grid,
            .stats-grid,
            .expertise-grid {
                grid-template-columns: 1fr;
            }

            section {
                padding: 4rem 0;
            }
        }

        @media (max-width: 640px) {
            .hero-image {
                width: 224px;
                height: 224px;
            }

            .hero-title {
                font-size: 2rem;
            }

            .hero-subtitle {
                font-size: 1.25rem;
            }
        }

        /* Smooth Scrolling */
        html {
            scroll-behavior: smooth;
        }

        /* SVG Icons Styles */
        svg {
            display: block;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navigation">
        <div class="nav-container">
            <div class="nav-logo">
                <span class="highlight">Ankita</span> Roy
            </div>
            
            <ul class="nav-menu">
                <li><button onclick="scrollToSection('#home')">Home</button></li>
                <li><button onclick="scrollToSection('#about')">About</button></li>
                <li><button onclick="scrollToSection('#skills')">Skills</button></li>
                <li><button onclick="scrollToSection('#projects')">Projects</button></li>
                <li><button onclick="scrollToSection('#certifications')">Certifications</button></li>
                <li><button onclick="scrollToSection('#contact')">Contact</button></li>
            </ul>

            <button class="mobile-menu-btn" onclick="toggleMobileMenu()">
                <svg id="menu-icon" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <line x1="3" y1="12" x2="21" y2="12"></line>
                    <line x1="3" y1="6" x2="21" y2="6"></line>
                    <line x1="3" y1="18" x2="21" y2="18"></line>
                </svg>
                <svg id="close-icon" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="display: none;">
                    <line x1="18" y1="6" x2="6" y2="18"></line>
                    <line x1="6" y1="6" x2="18" y2="18"></line>
                </svg>
            </button>
        </div>
        
        <div class="mobile-menu" id="mobile-menu">
            <button onclick="scrollToSection('#home')">Home</button>
            <button onclick="scrollToSection('#about')">About</button>
            <button onclick="scrollToSection('#skills')">Skills</button>
            <button onclick="scrollToSection('#projects')">Projects</button>
            <button onclick="scrollToSection('#certifications')">Certifications</button>
            <button onclick="scrollToSection('#contact')">Contact</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home">
        <div class="container" style="padding: 5rem 1rem;">
            <div class="hero-grid">
                <div class="hero-image-wrapper">
                    <div class="hero-image-container">
                        <div class="hero-glow"></div>
                        <img src="https://dry-scarlet-h1sr3sw1ns.edgeone.app/IMG-20251016-WA0034[1].jpg" alt="Ankita Roy" class="hero-image">
                    </div>
                </div>

                <div class="hero-content">
                    <p class="hero-greeting">Hello, I'm</p>
                    <h1 class="hero-title">Ankita Roy</h1>
                    <div class="hero-subtitle">AI & ML Engineer | Web Developer</div>

                    <div style="margin-bottom: 1rem;">
                        <p class="hero-description">
                            Computer Science & Engineering student at Guru Nanak Institute of Technology, 
                            specializing in Artificial Intelligence, Machine Learning, and Web Development.
                        </p>
                        <p class="hero-description">
                            Microsoft & Google certified professional with expertise in Generative AI, 
                            Natural Language Processing, and Azure AI Services.
                        </p>
                    </div>

                    <div class="hero-buttons">
                        <button class="btn btn-primary" onclick="scrollToSection('#contact')">Get In Touch</button>
                        <button class="btn btn-secondary">
                            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                                <polyline points="7 10 12 15 17 10"></polyline>
                                <line x1="12" y1="15" x2="12" y2="3"></line>
                            </svg>
                            Resume
                        </button>
                    </div>

                    <div class="hero-socials">
                        <a href="mailto:ankita.ai.dev@gmail.com" class="social-link" aria-label="Email">
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <rect x="2" y="4" width="20" height="16" rx="2"></rect>
                                <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"></path>
                            </svg>
                        </a>
                        <a href="https://github.com/ankitaaidev" target="_blank" rel="noopener noreferrer" class="social-link" aria-label="GitHub">
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path>
                                <path d="M9 18c-4.51 2-5-2-7-2"></path>
                            </svg>
                        </a>
                        <a href="https://www.linkedin.com/in/ankita-ai-dev" target="_blank" rel="noopener noreferrer" class="social-link" aria-label="LinkedIn">
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
                                <rect x="2" y="9" width="4" height="12"></rect>
                                <circle cx="4" cy="4" r="2"></circle>
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">About Me</h2>
                <div class="title-underline"></div>
            </div>

            <div class="about-grid">
                <div>
                    <div class="about-card" style="margin-bottom: 2rem;">
                        <h3>Professional Summary</h3>
                        <div>
                            <p>
                                I'm a passionate AI & ML engineer Web Development enthusiast with a strong academic 
                                foundation and hands-on expertise in cutting-edge technologies. Currently pursuing my 
                                B.Tech in Computer Science and Engineering, I'm driven by a vision to contribute to 
                                intelligent and scalable solutions that shape the future.
                            </p>
                            <p>
                                My technical skillset spans across Web Development, Generative AI, LLM Models, Natural Language 
                                Processing, and the specialized domain of Machine Learning . I leverage these skills 
                                to optimize AI system performance and create innovative solutions for real-world challenges.
                            </p>
                            <p>
                                As a Microsoft and Google certified professional, I demonstrate both conceptual mastery 
                                and practical excellence. I continuously seek to blend innovation with impact, actively 
                                contributing to next-generation development projects and collaborative tech communities.
                            </p>
                        </div>
                    </div>

                    <div class="about-card">
                        <h3>Areas of Expertise</h3>
                        <div class="expertise-grid">
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Artificial Intelligence & Machine Learning</span>
                            </div>
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Generative AI & Large Language Models</span>
                            </div>
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Natural Language Processing</span>
                            </div>
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Data Science & Analytics</span>
                            </div>
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Deep Learning</span>
                            </div>
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Azure AI Services</span>
                            </div>
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Web Development</span>
                            </div>
                            <div class="expertise-item">
                                <div class="expertise-dot"></div>
                                <span>Research & Innovation</span>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="highlights-grid">
                    <div class="highlight-card">
                        <div class="highlight-header">
                            <div class="highlight-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path d="M22 10v6M2 10l10-5 10 5-10 5z"></path>
                                    <path d="M6 12v5c3 3 9 3 12 0v-5"></path>
                                </svg>
                            </div>
                            <div>
                                <h4>Education</h4>
                                <p>B.Tech in Computer Science & Engineering at Guru Nanak Institute of Technology</p>
                            </div>
                        </div>
                    </div>

                    <div class="highlight-card">
                        <div class="highlight-header">
                            <div class="highlight-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <circle cx="12" cy="8" r="7"></circle>
                                    <polyline points="8.21 13.89 7 23 12 20 17 23 15.79 13.88"></polyline>
                                </svg>
                            </div>
                            <div>
                                <h4>Certifications</h4>
                                <p>Microsoft & Google certified in AI, ML, and Generative AI technologies</p>
                            </div>
                        </div>
                    </div>

                    <div class="highlight-card">
                        <div class="highlight-header">
                            <div class="highlight-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <circle cx="12" cy="12" r="10"></circle>
                                    <circle cx="12" cy="12" r="6"></circle>
                                    <circle cx="12" cy="12" r="2"></circle>
                                </svg>
                            </div>
                            <div>
                                <h4>Specialization</h4>
                                <p>AI/ML, Data Science, Prompt Engineering, and Azure AI Services</p>
                            </div>
                        </div>
                    </div>

                    <div class="highlight-card">
                        <div class="highlight-header">
                            <div class="highlight-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <polyline points="16 18 22 12 16 6"></polyline>
                                    <polyline points="8 6 2 12 8 18"></polyline>
                                </svg>
                            </div>
                            <div>
                                <h4>Development</h4>
                                <p>Full-stack web development with focus on AI-powered applications</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="bg-decoration bg-decoration-1"></div>
        <div class="bg-decoration bg-decoration-2"></div>
        
        <div class="container">
            <div class="section-header" style="text-align: center;">
                <h2 class="section-title">Skills & <span style="color: var(--cyan-400);">Technologies</span></h2>
                <div class="title-underline" style="margin: 0 auto 1rem;"></div>
                <p style="color: var(--text-muted); max-width: 42rem; margin: 0 auto;">
                    Comprehensive expertise across AI, Machine Learning, Data Science, and modern web development technologies
                </p>
            </div>

            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-header">
                        <div class="skill-icon">
                            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"></path>
                                <path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"></path>
                            </svg>
                        </div>
                        <h3>Artificial Intelligence & ML</h3>
                    </div>
                    <div class="skill-tags">
                        <span class="skill-tag">Machine Learning</span>
                        <span class="skill-tag">Deep Learning</span>
                        <span class="skill-tag">Generative AI</span>
                        <span class="skill-tag">Natural Language Processing</span>
                        <span class="skill-tag">Computer Vision</span>
                        <span class="skill-tag">Neural Networks</span>
                        <span class="skill-tag">Model Training & Optimization</span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-header">
                        <div class="skill-icon">
                            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <ellipse cx="12" cy="5" rx="9" ry="3"></ellipse>
                                <path d="M21 12c0 1.66-4 3-9 3s-9-1.34-9-3"></path>
                                <path d="M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5"></path>
                            </svg>
                        </div>
                        <h3>Data Science & Analytics</h3>
                    </div>
                    <div class="skill-tags">
                        <span class="skill-tag">Data Analysis</span>
                        <span class="skill-tag">Statistical Modeling</span>
                        <span class="skill-tag">Data Visualization</span>
                        <span class="skill-tag">Predictive Analytics</span>
                        <span class="skill-tag">NumPy & Pandas</span>
                        <span class="skill-tag">Feature Engineering</span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-header">
                        <div class="skill-icon">
                            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <polyline points="16 18 22 12 16 6"></polyline>
                                <polyline points="8 6 2 12 8 18"></polyline>
                            </svg>
                        </div>
                        <h3>Programming & Development</h3>
                    </div>
                    <div class="skill-tags">
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">C Programming</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">HTML & CSS</span>
                        <span class="skill-tag">Git & Version Control</span>
                        <span class="skill-tag">RESTful APIs</span>
                        <span class="skill-tag">Web Development</span>
                        <span class="skill-tag">Algorithm Design</span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-header">
                        <div class="skill-icon">
                            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"></path>
                            </svg>
                        </div>
                        <h3>Cloud & AI Services</h3>
                    </div>
                    <div class="skill-tags">
                        <span class="skill-tag">Azure AI Services</span>
                        <span class="skill-tag">Azure Machine Learning</span>
                        <span class="skill-tag">Speech Recognition</span>
                        <span class="skill-tag">Text Analytics</span>
                        <span class="skill-tag">Information Extraction</span>
                        <span class="skill-tag">Prompt Engineering</span>
                        <span class="skill-tag">LLM Integration</span>
                        <span class="skill-tag">Cloud Computing</span>
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-header">
                        <div class="skill-icon">
                            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path>
                                <circle cx="9" cy="7" r="4"></circle>
                                <path d="M23 21v-2a4 4 0 0 0-3-3.87"></path>
                                <path d="M16 3.13a4 4 0 0 1 0 7.75"></path>
                            </svg>
                        </div>
                        <h3>Professional Skills</h3>
                    </div>
                    <div class="skill-tags">
                        <span class="skill-tag">Problem Solving</span>
                        <span class="skill-tag">Critical Thinking</span>
                        <span class="skill-tag">Research & Development</span>
                        <span class="skill-tag">Technical Documentation</span>
                        <span class="skill-tag">Team Collaboration</span>
                        <span class="skill-tag">Project Management</span>
                        <span class="skill-tag">Presentation Skills</span>
                        <span class="skill-tag">Continuous Learning</span>
                    </div>
                </div>
            </div>

            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-value">35+</div>
                    <div class="stat-label">Technologies</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">11</div>
                    <div class="stat-label">Certifications</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">3+</div>
                    <div class="stat-label">Projects</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">500+</div>
                    <div class="stat-label">Learning Hours</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <div class="bg-decoration bg-decoration-2" style="top: 33%; left: -12rem;"></div>
        <div class="bg-decoration bg-decoration-1" style="bottom: 33%; right: -12rem;"></div>
        
        <div class="container">
            <div class="section-header" style="text-align: center;">
                <h2 class="section-title">Featured <span style="color: var(--cyan-400);">Projects</span></h2>
                <div class="title-underline" style="margin: 0 auto 1rem;"></div>
                <p style="color: var(--text-muted); max-width: 42rem; margin: 0 auto;">
                    Innovative AI-powered applications showcasing expertise in Machine Learning and Data Science
                </p>
            </div>

            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image-wrapper">
                        <img src="https://images.unsplash.com/photo-1566915896913-549d796d2166?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHxkZXZlbG9wZXIlMjBjb2RpbmclMjB3b3Jrc3BhY2V8ZW58MXx8fHwxNzYwNjM5MTMyfDA&ixlib=rb-4.1.0&q=80&w=1080" alt="AI-Powered Autocorrect Tool" class="project-image">
                        <div class="project-overlay"></div>
                    </div>
                    <div class="project-content">
                        <h3>AI-Powered Autocorrect Tool</h3>
                        <p class="project-description">
                            An intelligent autocorrect system leveraging AI to provide context-aware corrections and suggestions for enhanced writing accuracy.
                        </p>
                        <div class="project-tags">
                            <span class="project-tag">Python</span>
                            <span class="project-tag">AI/ML</span>
                            <span class="project-tag">NLP</span>
                        </div>
                        <a href="https://github.com/ankitaaidev/ai-powered-auto-corrector" target="_blank" rel="noopener noreferrer" class="project-link">
                            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path>
                                <path d="M9 18c-4.51 2-5-2-7-2"></path>
                            </svg>
                            <span>View on GitHub</span>
                        </a>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image-wrapper">
                        <img src="https://images.unsplash.com/photo-1660165458059-57cfb6cc87e5?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHxBSSUyMHRlY2hub2xvZ3klMjBhYnN0cmFjdHxlbnwxfHx8fDE3NjA2MTAzODV8MA&ixlib=rb-4.1.0&q=80&w=1080" alt="AI-Powered Voice Assistant" class="project-image">
                        <div class="project-overlay"></div>
                    </div>
                    <div class="project-content">
                        <h3>AI-Powered Voice Assistant</h3>
                        <p class="project-description">
                            A sophisticated voice assistant application utilizing AI and natural language processing to understand and respond to voice commands intelligently.
                        </p>
                        <div class="project-tags">
                            <span class="project-tag">Python</span>
                            <span class="project-tag">AI</span>
                            <span class="project-tag">Speech Recognition</span>
                        </div>
                        <a href="https://github.com/ankitaaidev/ai-powered-voice-assistant" target="_blank" rel="noopener noreferrer" class="project-link">
                            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path>
                                <path d="M9 18c-4.51 2-5-2-7-2"></path>
                            </svg>
                            <span>View on GitHub</span>
                        </a>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image-wrapper">
                        <img src="https://images.unsplash.com/photo-1634638415860-cef1aafb60c4?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHxkYXRhJTIwdmlzdWFsaXphdGlvbiUyMGRpZ2l0YWx8ZW58MXx8fHwxNzYwNjM5MTM0fDA&ixlib=rb-4.1.0&q=80&w=1080" alt="AI-Powered Resume Parser" class="project-image">
                        <div class="project-overlay"></div>
                    </div>
                    <div class="project-content">
                        <h3>AI-Powered Resume Parser</h3>
                        <p class="project-description">
                            An advanced resume parsing tool that uses AI to extract, analyze, and structure information from resumes, streamlining recruitment processes.
                        </p>
                        <div class="project-tags">
                            <span class="project-tag">Python</span>
                            <span class="project-tag">AI/ML</span>
                            <span class="project-tag">Data Processing</span>
                        </div>
                        <a href="https://github.com/ankitaaidev/ai-powered-resume-parser" target="_blank" rel="noopener noreferrer" class="project-link">
                            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path>
                                <path d="M9 18c-4.51 2-5-2-7-2"></path>
                            </svg>
                            <span>View on GitHub</span>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Certifications Section -->
    <section id="certifications">
        <div class="bg-decoration bg-decoration-1" style="top: 50%; right: -12rem;"></div>
        <div class="bg-decoration" style="bottom: 33%; left: -12rem; width: 24rem; height: 24rem; background: rgba(168, 85, 247, 0.1); filter: blur(80px);"></div>
        
        <div class="container">
            <div class="section-header" style="text-align: center;">
                <h2 class="section-title">Professional <span style="color: var(--cyan-400);">Certifications</span></h2>
                <div class="title-underline" style="margin: 0 auto 1rem;"></div>
                <p style="color: var(--text-muted); max-width: 42rem; margin: 0 auto;">
                    Industry-recognized credentials from leading technology companies
                </p>
            </div>

            <div class="certifications-grid">
                <a href="https://www.credly.com/badges/8e7f56c7-c46c-4062-b1b8-41c45266ad7d/public_url" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Python for Data Science and AI</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">IBM</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://cdn.qwiklabs.com/VF6eQ1bV8SfqKBpu8AVD%2F4G93sg9wJQ0wWe9CTc%2FJ%2F4%3D" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Google Certified in Generative AI</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Google Cloud</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://coursera.org/share/82543a0efda799a1689f82710dfb3f19" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Google AI Essentials</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Google</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://www.coursera.org/account/accomplishments/verify/8DKPZPIRKCOZ" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>NVIDIA: Fundamentals of Deep Learning</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">NVIDIA Deep Learning Institute</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://learn.microsoft.com/en-us/users/ankita-roy/achievements/7k6uy7wz" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Machine Learning in Azure</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Microsoft Learn</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://learn.microsoft.com/en-us/users/ankita-roy/achievements/vju8vn4m" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Generative AI in Azure</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Microsoft Learn</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://learn.microsoft.com/api/achievements/share/en-us/Ankita-Roy/9YEBH5CU?sharingId=F4226B06B2754203" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Natural Language Processing in Azure</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Microsoft Learn</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://learn.microsoft.com/en-us/users/ankita-roy/achievements/8zbsxcuw" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Speech Recognition in Azure</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Microsoft Learn</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://learn.microsoft.com/en-us/users/ankita-roy/achievements/9yebywsu" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>AI-Powered Information Extraction</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Microsoft Learn</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://forage-uploads-prod.s3.amazonaws.com/completion-certificates/SKZxezskWgmFjRvj9/gabev3vXhuACr48eb_SKZxezskWgmFjRvj9_EFDYBd6SjGGrjMsHE_1751989729023_completion_certificate.pdf" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>BCG - GenAI Job Simulation</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Forage</p>
                    <p class="cert-date">2025</p>
                </a>

                <a href="https://forage-uploads-prod.s3.amazonaws.com/completion-certificates/9PBTqmSxAf6zZTseP/udmxiyHeqYQLkTPvf_9PBTqmSxAf6zZTseP_EFDYBd6SjGGrjMsHE_1751986514177_completion_certificate.pdf" target="_blank" rel="noopener noreferrer" class="cert-card">
                    <div class="cert-header">
                        <h3>Deloitte Australia - Technology Job Simulation</h3>
                        <svg class="cert-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                            <polyline points="15 3 21 3 21 9"></polyline>
                            <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                    </div>
                    <p class="cert-issuer">Forage</p>
                    <p class="cert-date">2025</p>
                </a>
            </div>

            <div class="cert-summary">
                <h3>Committed to Continuous Learning</h3>
                <p>
                    Continuously investing in professional development through certifications from leading 
                    technology companies including Microsoft, Google, IBM, and NVIDIA, demonstrating commitment 
                    to excellence and staying current with industry standards.
                </p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="bg-decoration bg-decoration-1" style="top: 25%; left: -12rem;"></div>
        <div class="bg-decoration bg-decoration-2" style="bottom: 25%; right: -12rem;"></div>
        
        <div class="container">
            <div class="section-header" style="text-align: center;">
                <h2 class="section-title">Let's <span style="color: var(--cyan-400);">Connect</span></h2>
                <div class="title-underline" style="margin: 0 auto 1rem;"></div>
                <p style="color: var(--text-muted); max-width: 42rem; margin: 0 auto;">
                    Open to collaborations, opportunities, and innovative projects in AI and Data Science
                </p>
            </div>

            <div class="contact-grid">
                <div class="contact-info">
                    <h3>Let's Connect</h3>
                    <p>
                        I'm always open to discussing new opportunities, collaborations, or 
                        innovative projects in AI, Machine Learning, and Data Science. Feel free 
                        to reach out through any of the channels below.
                    </p>

                    <div class="contact-links">
                        <a href="mailto:ankita.ai.dev@gmail.com" class="contact-link">
                            <div class="contact-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <rect x="2" y="4" width="20" height="16" rx="2"></rect>
                                    <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"></path>
                                </svg>
                            </div>
                            <div class="contact-details">
                                <p>Email</p>
                                <p>ankita.ai.dev@gmail.com</p>
                            </div>
                        </a>

                        <a href="https://github.com/ankitaaidev" target="_blank" rel="noopener noreferrer" class="contact-link">
                            <div class="contact-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path>
                                    <path d="M9 18c-4.51 2-5-2-7-2"></path>
                                </svg>
                            </div>
                            <div class="contact-details">
                                <p>GitHub</p>
                                <p>github.com/ankitaaidev</p>
                            </div>
                        </a>

                        <a href="https://www.linkedin.com/in/ankita-ai-dev" target="_blank" rel="noopener noreferrer" class="contact-link">
                            <div class="contact-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
                                    <rect x="2" y="9" width="4" height="12"></rect>
                                    <circle cx="4" cy="4" r="2"></circle>
                                </svg>
                            </div>
                            <div class="contact-details">
                                <p>LinkedIn</p>
                                <p>linkedin.com/in/ankita-ai-dev</p>
                            </div>
                        </a>
                    </div>
                </div>

                <div class="info-cards">
                    <div class="info-card">
                        <div class="info-card-header">
                            <div class="contact-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path d="M22 10v6M2 10l10-5 10 5-10 5z"></path>
                                    <path d="M6 12v5c3 3 9 3 12 0v-5"></path>
                                </svg>
                            </div>
                            <div>
                                <h4>Education</h4>
                                <p>B.Tech in Computer Science & Engineering</p>
                                <p class="info-card-small">Guru Nanak Institute of Technology</p>
                                <p class="info-card-small">Expected Graduation: 2028</p>
                            </div>
                        </div>
                    </div>

                    <div class="info-card">
                        <h4 style="margin-bottom: 1rem;">Areas of Interest</h4>
                        <div class="interest-tags">
                            <span class="interest-tag">AI Research</span>
                            <span class="interest-tag">Machine Learning</span>
                            <span class="interest-tag">Data Science</span>
                            <span class="interest-tag">Generative AI</span>
                            <span class="interest-tag">NLP</span>
                            <span class="interest-tag">Cloud AI</span>
                            <span class="interest-tag">Web Development</span>
                            <span class="interest-tag">Innovation</span>
                        </div>
                    </div>

                    <div class="info-card highlight-card-special">
                        <h4>Currently Seeking</h4>
                        <p>
                            Internship and full-time opportunities in AI/ML, Data Science, and related fields. 
                            Open to research collaborations and innovative projects.
                        </p>
                    </div>
                </div>
            </div>

            <div class="footer">
                <p>© 2025 Ankita Roy. All rights reserved.</p>
            </div>
        </div>
    </section>

    <script>
        // Navigation scroll effect
        window.addEventListener('scroll', function() {
            const nav = document.getElementById('navigation');
            if (window.scrollY > 50) {
                nav.classList.add('scrolled');
            } else {
                nav.classList.remove('scrolled');
            }
        });

        // Mobile menu toggle
        let mobileMenuOpen = false;
        function toggleMobileMenu() {
            const mobileMenu = document.getElementById('mobile-menu');
            const menuIcon = document.getElementById('menu-icon');
            const closeIcon = document.getElementById('close-icon');
            
            mobileMenuOpen = !mobileMenuOpen;
            
            if (mobileMenuOpen) {
                mobileMenu.classList.add('active');
                menuIcon.style.display = 'none';
                closeIcon.style.display = 'block';
            } else {
                mobileMenu.classList.remove('active');
                menuIcon.style.display = 'block';
                closeIcon.style.display = 'none';
            }
        }

        // Smooth scroll to section
        function scrollToSection(href) {
            const element = document.querySelector(href);
            if (element) {
                element.scrollIntoView({ behavior: 'smooth' });
                
                // Close mobile menu if open
                if (mobileMenuOpen) {
                    toggleMobileMenu();
                }
            }
        }

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                }
            });
        }, observerOptions);

        // Observe sections
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('section');
            sections.forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>

