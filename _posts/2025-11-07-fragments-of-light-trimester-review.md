---
layout: post
title: "Fragments of Light: Trimester 1 Final Review"
author: Cyrus
permalink: /final-review
categories: [CSP, Reflection, Trimester Review]
---

<style>
/* Fragments of Light Theme */
body {
    background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 50%, #0f1428 100%);
    color: #e0e6ed;
}

.fragments-container {
    max-width: 1200px;
    margin: 40px auto;
    padding: 20px;
    position: relative;
}

.fragments-header {
    text-align: center;
    margin-bottom: 60px;
    animation: fadeInDown 1s ease-out;
}

.fragments-header h1 {
    font-size: 3.5em;
    background: linear-gradient(135deg, #64b3f4, #c2e9fb, #a1c4fd);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-weight: 700;
    letter-spacing: 2px;
    text-shadow: 0 0 30px rgba(100, 179, 244, 0.3);
    margin-bottom: 20px;
}

.fragments-header p {
    font-size: 1.2em;
    color: #a0aec0;
    font-style: italic;
    opacity: 0.8;
}

/* Memory Shard Cards */
.memory-shard {
    background: rgba(26, 32, 58, 0.6);
    backdrop-filter: blur(10px);
    border: 2px solid rgba(100, 179, 244, 0.3);
    border-radius: 20px;
    padding: 40px;
    margin: 40px 0;
    position: relative;
    overflow: hidden;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3),
                0 0 20px rgba(100, 179, 244, 0.1);
    animation: float 6s ease-in-out infinite, borderPulse 4s ease-in-out infinite;
}

.memory-shard:nth-child(even) {
    animation-delay: -3s, -2s;
}

.memory-shard:hover {
    transform: translateY(-8px) scale(1.02);
    box-shadow: 0 16px 48px rgba(0, 0, 0, 0.4),
                0 0 40px rgba(100, 179, 244, 0.3);
}

/* Shard Number Badge */
.shard-number {
    position: absolute;
    top: 20px;
    right: 20px;
    width: 50px;
    height: 50px;
    background: linear-gradient(135deg, #64b3f4, #a1c4fd);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.3em;
    color: #0a0e27;
    box-shadow: 0 4px 12px rgba(100, 179, 244, 0.4);
    animation: glow 2s ease-in-out infinite;
}

/* Shard Title */
.shard-title {
    font-size: 2em;
    color: #64b3f4;
    margin-bottom: 20px;
    font-weight: 600;
    letter-spacing: 1px;
    padding-right: 70px;
}

/* Content Area */
.shard-content {
    color: #cbd5e0;
    font-size: 1.1em;
    line-height: 1.8;
    min-height: 150px;
    padding: 20px 0;
    counter-reset: section-counter;
}

.shard-content h3 {
    color: #a1c4fd;
    font-size: 1.4em;
    margin-top: 20px;
    margin-bottom: 15px;
    counter-increment: section-counter;
}

.shard-content h3::before {
    content: counter(section-counter, lower-alpha) ". ";
    color: #64b3f4;
    font-weight: 700;
    margin-right: 8px;
}

.shard-content ul {
    list-style: none;
    padding-left: 0;
}

.shard-content li {
    padding: 8px 0;
    padding-left: 30px;
    position: relative;
}

.shard-content li::before {
    content: '•';
    position: absolute;
    left: 0;
    color: #64b3f4;
    font-size: 1.2em;
}

/* Placeholder Text */
.placeholder {
    color: #718096;
    font-style: italic;
    padding: 20px;
    background: rgba(0, 0, 0, 0.2);
    border-radius: 10px;
    border-left: 3px solid #64b3f4;
}

/* Animations */
@keyframes float {
    0%, 100% {
        transform: translateY(0px);
    }
    50% {
        transform: translateY(-10px);
    }
}

@keyframes borderPulse {
    0%, 100% {
        border-color: rgba(100, 179, 244, 0.3);
    }
    50% {
        border-color: rgba(100, 179, 244, 0.7);
    }
}

@keyframes glow {
    0%, 100% {
        box-shadow: 0 4px 12px rgba(100, 179, 244, 0.4);
    }
    50% {
        box-shadow: 0 4px 20px rgba(100, 179, 244, 0.8);
    }
}

@keyframes fadeInDown {
    from {
        opacity: 0;
        transform: translateY(-30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Responsive Design */
@media (max-width: 768px) {
    .fragments-header h1 {
        font-size: 2.5em;
    }
    
    .memory-shard {
        padding: 30px 20px;
    }
    
    .shard-title {
        font-size: 1.5em;
    }
    
    .shard-number {
        width: 40px;
        height: 40px;
        font-size: 1.1em;
    }
}

/* Dark theme override */
.post-content {
    background: transparent !important;
}

/* Shooting Star Animation */
.shooting-star {
    position: fixed;
    width: 2px;
    height: 2px;
    background: #fff;
    border-radius: 50%;
    box-shadow: 0 0 6px 2px rgba(100, 179, 244, 0.8),
                0 0 10px 4px rgba(194, 233, 251, 0.6);
    pointer-events: none;
    z-index: 1000;
    animation: shootStar linear;
}

@keyframes shootStar {
    0% {
        opacity: 0;
        transform: translate(0, 0) scale(0);
    }
    10% {
        opacity: 1;
        transform: translate(0, 0) scale(1);
    }
    90% {
        opacity: 1;
    }
    100% {
        opacity: 0;
        transform: translate(var(--end-x), var(--end-y)) scale(0.5);
    }
}

/* Fragments of Light on Sides */
.fragments-container::before,
.fragments-container::after {
    content: '';
    position: fixed;
    width: 100px;
    height: 100%;
    top: 0;
    pointer-events: none;
    z-index: 1;
    opacity: 0.3;
}

.fragments-container::before {
    left: 0;
    background: radial-gradient(ellipse at left center, 
        rgba(100, 179, 244, 0.2) 0%,
        rgba(100, 179, 244, 0.1) 30%,
        transparent 70%);
    animation: fragmentGlow 8s ease-in-out infinite;
}

.fragments-container::after {
    right: 0;
    background: radial-gradient(ellipse at right center, 
        rgba(194, 233, 251, 0.2) 0%,
        rgba(194, 233, 251, 0.1) 30%,
        transparent 70%);
    animation: fragmentGlow 8s ease-in-out infinite 4s;
}

@keyframes fragmentGlow {
    0%, 100% {
        opacity: 0.2;
    }
    50% {
        opacity: 0.4;
    }
}

/* Floating Light Particles */
.light-particle {
    position: fixed;
    width: 4px;
    height: 4px;
    background: rgba(100, 179, 244, 0.6);
    border-radius: 50%;
    pointer-events: none;
    z-index: 1;
    box-shadow: 0 0 8px 2px rgba(100, 179, 244, 0.4);
    animation: floatParticle 15s ease-in-out infinite;
}

@keyframes floatParticle {
    0%, 100% {
        transform: translate(0, 0) scale(0.8);
        opacity: 0.3;
    }
    50% {
        transform: translate(var(--drift-x), var(--drift-y)) scale(1.2);
        opacity: 0.7;
    }
}
</style>

<div class="fragments-container">
    <div class="fragments-header">
        <h1>Fragments of Light</h1>
        <p>A journey through Trimester 1 — reflections illuminated</p>
    </div>

    <!-- Memory Shard 1: Beginning of the Year -->
    <div class="memory-shard">
        <div class="shard-number">1</div>
        <h2 class="shard-title">
            Reflecting on the Beginning
        </h2>
        <div class="shard-content">
            <h3>The First Spark</h3>
            <p>
                I was first introduced to coding when I was around ten, and I was immediately drawn in by how <em>limitless</em> it felt — how a few lines of code could turn imagination into something alive. I've always loved playing video games, so the idea of creating my own has always been my dream. But before taking CSP, I didn't have the time, structure, or resources to learn more about coding. I self-learned a little bit of Python, made a few small experiments, and then drifted away from coding.
            </p>
            
            <h3>Building Confidence</h3>
            <p>
                That changed in this class. Over the past three months, I've built not just programs but <strong>confidence</strong>. I learned how to set up professional tools, document my work, and debug with patience and logic. Working independently taught me to think critically, to trace errors like footprints, and to build solutions from small, deliberate steps.
            </p>
            
            <h3>The Power of Collaboration</h3>
            <p>
                Collaboration made that even stronger — from pair-coding hacks like <strong>Pong</strong> and <strong>Rock-Paper-Scissors</strong> to large-scale teamwork in <strong>Digital Famine</strong>, where every student had a role yet our work connected into one shared vision. Through this, I began to understand what real software creation feels like: a blend of creativity, communication, and persistence.
            </p>
            
            <h3>Code Coming to Life</h3>
            <p>
                The Night at the Museum event tied it all together — seeing real people interact with my project, asking questions, and giving feedback was like watching the code come to life. Looking back, I can see how much I've grown — not just as a coder, but as someone who can take an idea, nurture it, and share it.
            </p>
            
            <p style="text-align: center; margin-top: 30px; font-size: 1.2em; color: #64b3f4; font-weight: 500;">
                <em>CSP showed me what it means to build worlds with others.</em>
            </p>
        </div>
    </div>

    <!-- Memory Shard 2: Three Sprints -->
    <div class="memory-shard">
        <div class="shard-number">2</div>
        <h2 class="shard-title">
            Sprint Journey
        </h2>
        <div class="shard-content">
            <h3>Tools & Onboarding</h3>
            <p>
                Setting up the tools in our <a href="{{ site.baseurl }}/about/">Navigation Console</a> sprint was the best introduction I could have asked for. At first I barely spoke up — I didn’t know my teammates yet and the terminal felt intimidating. Each shell error made me feel alone. But step by step, the process taught me how collaboration works in practice. Asking for help turned into pair-debugging, and the team slowly pulled me out of my comfort zone. By the end of the sprint I was far more outgoing, ready to walk someone else through the same setup checklist.
            </p>

            <h3>Teaching the Fundamentals</h3>
            <p>
                During the fundamentals sprint I helped design and teach lessons like our <a href="{{ site.baseurl }}/pong-learning/">Pong OOP workshop</a> and the <a href="{{ site.baseurl }}/hacks/rock-paper-scissor/">Rock-Paper-Scissors hack</a>. Writing lesson plans, assigning homework, and presenting demos transformed me from a learner into a learning-designer. Translating loops, conditionals, and objects into activities forced me to understand the concepts deeply enough to explain them — which ended up being the fastest way to master them myself.
            </p>

            <h3>Systems Thinking in Digital Famine</h3>
            <p>
                Our <strong>Digital Famine</strong> sprint showed me how many disciplines it takes to ship a meaningful project. Research, design, gameplay, analytics — every sector mattered. Seeing the entire class connect their deliverables into one coherent world made it clear: a great project is really a coordination challenge. That sprint crystallized why teamwork isn’t optional in software — it’s the engine that keeps ambitious ideas alive.
            </p>
        </div>
    </div>

    <!-- Memory Shard 3: N@tM Experience -->
    <div class="memory-shard">
        <div class="shard-number">3</div>
        <h2 class="shard-title">
            Night at the Museum
        </h2>
        <div class="shard-content">
            <h3>Feedback that Fueled Us</h3>
            <p>
                Night at the Museum was the first time strangers walked through our lessons. People told us the <strong>progress bar</strong> made them feel accomplished with every module they finished, like they were leveling up in real time. Others said the idea of turning setup into an interactive lesson was "one of the most fun" approaches they had seen — equal parts launchpad and game.
            </p>

            <h3>Seeing the Impact</h3>
            <p>
                Hearing those reactions made me fall in love with coding all over again. The hours we spent debugging suddenly felt worth it because we watched learners light up while using something we built. Those conversations reminded me that software isn’t just lines of code — it’s the feeling people get when they interact with it.
            </p>
        </div>
    </div>

    <!-- Memory Shard 4: Future Project Plans -->
    <div class="memory-shard">
        <div class="shard-number">4</div>
        <h2 class="shard-title">
            Next Steps for the Project
        </h2>
        <div class="shard-content">
            <h3>Five Upgrades on Deck</h3>
            <ul>
                <li><strong>Docking Consoles Everywhere:</strong> Embed a mini HUD on each planet so players see their status and can jump back into missions without feeling stranded.</li>
                <li><strong>Hyperspace Transitions:</strong> Swap instant teleports for short animated jumps that show the ship charging, traveling, and arriving.</li>
                <li><strong>Unified Rewards:</strong> Link planet unlocks with end-module trophies so clearing a mission lights up the galaxy and adds collectibles.</li>
                <li><strong>Galaxy Routes:</strong> Draw animated routes between completed planets so progress looks and feels like charting the stars.</li>
                <li><strong>Homebound Button:</strong> Add a clear back button on every planet that warps players to the main map, keeping the world connected.</li>
            </ul>
        </div>
    </div>

    <!-- Memory Shard 5: Future Learning -->
    <div class="memory-shard">
        <div class="shard-number">5</div>
        <h2 class="shard-title">
            Future Learning Goals
        </h2>
        <div class="shard-content">
            <h3>What’s Next in CSP</h3>
            <p>
                Trimester 2 feels like the perfect time to dive into <strong>APIs and data services</strong>. I want to learn how to pull live information into our galaxy, log player progress in a shared database, and wire up dashboards that react in real time. Crafting these bridges between our front end and the wider web would make the world feel truly connected.
            </p>
            <p>
                By Trimester 3, I’m itching to experiment with <strong>machine learning</strong>. Whether it’s a recommender that suggests missions based on playstyle or a simple model that adapts difficulty on the fly, applying AI concepts would push our project into sci-fi territory — and teach me how to design systems that learn alongside the players.
            </p>
        </div>
    </div>

    <!-- Memory Shard 6: MCQ Review -->
    <div class="memory-shard">
        <div class="shard-number">6</div>
        <h2 class="shard-title">
            MCQ Performance & Approach
        </h2>
        <div class="shard-content">
            <h3>How I Tackled the MCQ Set</h3>
            <p>
                I worked each question to the best of my ability, marked the ones that felt shaky, and did targeted research afterward. If I understood the stem but blanked on the answer, I dug into notes, reference sheets, or similar College Board explanations until the correct choice made sense. If a problem felt completely foreign, I skipped it, finished the rest, then came back with fresh eyes. After submitting, I reviewed every miss, wrote why my reasoning failed, and captured the rule or pattern that would help me nail a similar item next time.
            </p>

            <h3>Corrections Log</h3>
            <ul>
                <li>
                    <strong>Mobile app release data table</strong><br>
                    <em>My answer:</em> Option A (no impact on daily messages). I focused only on the "messages per user" column and missed the sharp drop in average characters right after the mobile app launched. <br>
                    <em>Correct insight:</em> Option D is right because message length plummeted from ~360 characters to under 200, then below 100. The mobile UI clearly nudged users toward shorter messages.
                </li>
                <li>
                    <strong>Repeat-until loop comparison</strong><br>
                    <em>My answer:</em> Option D (different number of outputs). I assumed the loops stopped at different times. <br>
                    <em>Correct insight:</em> Option C is right: both programs output 10 values, but Program A shows 1–10 while Program B increments before displaying, so it shows 2–11. Order matches, values shift by one.
                </li>
                <li>
                    <strong>Network redundancy diagram</strong> (left unanswered)<br>
                    <em>Correct insight:</em> Option B is correct because that layout is a tree. There is only one simple path between P and S, so no alternate route exists if a link fails. <br>
                    <em>Point of confusion:</em> I wasn’t sure whether the diagonal edge created a second route; sketching the graph revealed it still collapses into a single chain.
                </li>
                <li>
                    <strong>Robot navigation pseudocode</strong><br>
                    <em>My answer:</em> Option C (move forward when possible, then rotate). That logic keeps the robot marching straight until blocked, which turns it the wrong way in this maze. <br>
                    <em>Correct insight:</em> Option A hugs the wall on the robot’s right: it checks the right side first, turns when space opens, and otherwise moves forward. That consistent right-hand rule eventually reaches the gray square.
                </li>
                <li>
                    <strong>Binary codes for 200 characters</strong> (left unanswered)<br>
                    <em>Correct insight:</em> Option D (8 bits). A 7-bit code tops out at 128 patterns; 8 bits provide 256, enough to label all 200 characters.
                </li>
                <li>
                    <strong>Streaming analytics runtime</strong> (left unanswered)<br>
                    <em>Correct insight:</em> Option D (5 hours). The first call to <code>Analysis("science fiction")</code> is 1 hour. The loop runs four more analyses—one per genre—adding 4 more hours. Everything else is instantaneous.
                </li>
                <li>
                    <strong>Reading vs. smartphone usage scatterplot</strong><br>
                    <em>My answer:</em> Option B (more reading → less interest). I misread the symbols and thought the circles showed the same trend. <br>
                    <em>Correct insight:</em> Option A matches the plot: the X’s (interested participants) cluster higher on the reading axis than the O’s, indicating heavier readers were more interested.
                </li>
                <li>
                    <strong>Mouse and predator simulation</strong> (left unanswered)<br>
                    <em>Correct insight:</em> Option D. The loop never updates <code>numPredators</code>, so the simulation assumes predator counts stay fixed during the year. <br>
                    <em>Point of confusion:</em> I expected <code>NextDayPopulation()</code> to change both numbers; re-reading clarified that only the mice population is updated.
                </li>
                <li>
                    <strong>Open Internet standards</strong> (left unanswered)<br>
                    <em>Correct insight:</em> Option A. Open protocols let hardware/software from different vendors interoperate across the Internet. It’s not about eliminating latency or blocking buggy releases.
                </li>
            </ul>
        </div>
    </div>

    <!-- Memory Shard 7: Something Cool -->
    <div class="memory-shard">
        <div class="shard-number">7</div>
        <h2 class="shard-title">
            Something Cool to Share
        </h2>
        <div class="shard-content">
            <div class="placeholder">
                <p><strong>Prompt:</strong> Something cool you'd like to share</p>
                <p>Content to be added: A feature, achievement, discovery, or insight</p>
            </div>
        </div>
    </div>

</div>

<script>
// Add subtle interactive effects
document.addEventListener('DOMContentLoaded', function() {
    const shards = document.querySelectorAll('.memory-shard');
    
    shards.forEach((shard, index) => {
        // Stagger animation delays
        shard.style.animationDelay = `${index * 0.1}s`;
        
        // Add intersection observer for scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, {
            threshold: 0.1
        });
        
        shard.style.opacity = '0';
        shard.style.transform = 'translateY(30px)';
        shard.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
        
        observer.observe(shard);
    });

    // Create shooting stars
    function createShootingStar() {
        const star = document.createElement('div');
        star.className = 'shooting-star';
        
        // Random start position (top of screen)
        const startX = Math.random() * window.innerWidth;
        const startY = -10;
        
        // Random end position (diagonal down)
        const angle = Math.random() * 60 + 15; // 15-75 degrees
        const distance = Math.random() * 400 + 300; // 300-700px
        const endX = startX + Math.cos(angle * Math.PI / 180) * distance;
        const endY = startY + Math.sin(angle * Math.PI / 180) * distance;
        
        star.style.left = startX + 'px';
        star.style.top = startY + 'px';
        star.style.setProperty('--end-x', (endX - startX) + 'px');
        star.style.setProperty('--end-y', (endY - startY) + 'px');
        star.style.animationDuration = (Math.random() * 1 + 0.8) + 's';
        
        document.body.appendChild(star);
        
        setTimeout(() => {
            star.remove();
        }, 2000);
    }

    // Create shooting stars periodically
    setInterval(createShootingStar, 3000);

    // Create floating light particles on sides
    function createLightParticle(side) {
        const particle = document.createElement('div');
        particle.className = 'light-particle';
        
        const x = side === 'left' ? 
            Math.random() * 150 : 
            window.innerWidth - Math.random() * 150;
        const y = Math.random() * window.innerHeight;
        
        particle.style.left = x + 'px';
        particle.style.top = y + 'px';
        
        const driftX = (Math.random() - 0.5) * 100;
        const driftY = (Math.random() - 0.5) * 200;
        particle.style.setProperty('--drift-x', driftX + 'px');
        particle.style.setProperty('--drift-y', driftY + 'px');
        particle.style.animationDelay = Math.random() * 5 + 's';
        
        document.body.appendChild(particle);
        
        setTimeout(() => {
            particle.remove();
        }, 20000);
    }

    // Create light particles on both sides
    for (let i = 0; i < 8; i++) {
        setTimeout(() => {
            createLightParticle('left');
            createLightParticle('right');
        }, i * 2000);
    }

    // Continuously add new particles
    setInterval(() => {
        createLightParticle('left');
        createLightParticle('right');
    }, 4000);
});
</script>

