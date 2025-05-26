:root {
    --bg-color: #f7f5f0; /* Light beige similar to image */
    --wall-color: #f9f7f2; /* Slightly brighter for walls */
    --wall-side-color: #e0ddd7; /* Darker for wall sides */
    --room-color: #ffffff; /* White for rooms */
    --central-color: #fce2bd; /* Orange border for central square */
    --text-color: #4a4a4a;
    --shadow-color: rgba(0, 0, 0, 0.15); /* Slightly stronger shadows */
    --light-shadow-color: rgba(0, 0, 0, 0.08); /* Slightly stronger light shadows */
    --wall-thickness: 20px; /* Increased for better frontal visibility */
    --element-lift: 25px; /* Increased for better frontal visibility */
}

body {
    margin: 0;
    overflow: hidden;
    background-color: var(--bg-color);
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    font-family: 'Helvetica Neue', Arial, sans-serif;
    color: var(--text-color);
}

/* Scene Setup for 3D Perspective */
.scene {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    perspective: 1000px; /* Perspective can be adjusted */
    perspective-origin: center center;
}

.office-layout {
    position: relative;
    width: 600px; /* Adjust overall size */
    height: 600px; /* Adjust overall size */
    transform-style: preserve-3d;
    /* --- MODIFIED FOR FRONT LOOK --- */
    /* Rotate slightly on X to show the top depth, Z is nearly 0 for front view */
    transform: rotateX(15deg) rotateZ(0deg) scale(0.9);
    box-shadow: 0 50px 100px var(--shadow-color); /* Overall scene shadow */
}

/* Base style for 3D elements */
.room, .central-square, .wall {
    position: absolute;
    transform-style: preserve-3d;
    box-shadow: 0 5px 15px var(--light-shadow-color),
                0 2px 5px var(--light-shadow-color);
}

/* Central Square */
.central-square {
    width: 180px;
    height: 180px;
    background-color: var(--room-color);
    border: 4px solid var(--central-color);
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) translateZ(calc(var(--element-lift) + 10px));
    box-shadow: 0 8px 25px var(--shadow-color),
                0 4px 10px var(--light-shadow-color); /* Stronger shadow */
}

/* Rooms styling */
.room {
    background-color: var(--room-color);
    padding: 15px;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-size: 1.1em;
    font-weight: bold;
    color: var(--text-color);
    min-width: 150px; /* Ensure consistent width */
    min-height: 90px; /* Ensure consistent height */
    text-align: center;
    transform: translateZ(var(--element-lift)); /* Pop out from the base */
}

.room .room-text {
    margin-bottom: 5px;
}

.avatars {
    display: flex;
    gap: 3px;
    margin-top: 5px;
}

.avatar {
    width: 18px;
    height: 18px;
    background-color: #b8b8b8; /* Placeholder for avatar color */
    border-radius: 50%;
    border: 1px solid #777;
}

/* Room specific positioning (relative to office-layout) */
/* These positions might need slight tweaks based on the new perspective */
.meeting-room {
    top: 40px;
    left: 40px;
}

.design-weekly.top {
    top: 250px;
    left: 40px;
}

.design-weekly.bottom {
    bottom: 40px;
    left: 40px;
}

.lounge {
    top: 100px;
    right: 40px;
}

.all-hands {
    bottom: 100px;
    right: 40px;
}

/* Creating the 3D 'wall' effect for rooms using pseudo-elements */
.room::before,
.room::after {
    content: '';
    position: absolute;
    background-color: var(--wall-side-color); /* Side color */
    box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2); /* Inner shadow for depth */
}

/* Top side (visible from front-top view) */
.room::before {
    top: 0;
    left: 0;
    width: 100%;
    height: var(--wall-thickness);
    transform: translateY(calc(-1 * var(--wall-thickness))) rotateX(90deg) translateZ(calc(var(--wall-thickness) / 2));
    transform-origin: bottom;
}

/* Right side (visible from front-right view, if any slight Y rotation) */
.room::after {
    top: 0;
    right: 0;
    height: 100%;
    width: var(--wall-thickness);
    /* No rotateY needed for perfect front, but slight allows small side reveal */
    transform: translateX(var(--wall-thickness)) rotateY(0deg) translateZ(calc(var(--wall-thickness) / 2));
    transform-origin: left;
}

/* Wall Segments (highly specific for the grid) */
.wall {
    background-color: var(--wall-color);
    box-shadow: 0 2px 5px var(--light-shadow-color);
    transform: translateZ(calc(var(--element-lift) - 5px)); /* Slightly lower than rooms */
}

/* Pseudo-elements for wall thickness */
.wall::before,
.wall::after {
    content: '';
    position: absolute;
    background-color: var(--wall-side-color);
    box-shadow: inset 0 0 3px rgba(0, 0, 0, 0.1);
}

/* Horizontal wall segments - positioning remains same as structure is fixed */
.wall.h-top-left { width: 100px; height: 30px; top: 125px; left: 190px; }
.wall.h-top-right { width: 150px; height: 30px; top: 125px; right: 190px; }
.wall.h-middle-left { width: 100px; height: 30px; top: 335px; left: 190px; }
.wall.h-middle-right { width: 150px; height: 30px; top: 335px; right: 190px; }
.wall.h-bottom-left { width: 100px; height: 30px; top: 545px; left: 190px; }
.wall.h-bottom-right { width: 150px; height: 30px; top: 545px; right: 190px; }


/* Vertical wall segments - positioning remains same as structure is fixed */
.wall.v-left-top { width: 30px; height: 100px; top: 125px; left: 190px; }
.wall.v-left-bottom { width: 30px; height: 100px; top: 445px; left: 190px; }
.wall.v-right-top { width: 30px; height: 100px; top: 125px; right: 190px; }
.wall.v-right-bottom { width: 30px; height: 100px; top: 445px; right: 190px; }


/* Generic pseudo for horizontal walls - now more prominent */
.wall[class*="h-"]::before { /* Top surface for thickness */
    top: 0;
    left: 0;
    width: 100%;
    height: var(--wall-thickness);
    transform: translateY(calc(-1 * var(--wall-thickness))) rotateX(90deg) translateZ(calc(var(--wall-thickness) / 2));
    transform-origin: bottom;
}
.wall[class*="h-"]::after { /* Side surface for thickness (right side) */
    top: 0;
    right: 0;
    width: var(--wall-thickness);
    height: 100%;
    /* No rotateY needed for perfect front, but slight allows small side reveal */
    transform: translateX(var(--wall-thickness)) rotateY(0deg) translateZ(calc(var(--wall-thickness) / 2));
    transform-origin: left;
}

/* Generic pseudo for vertical walls - now more prominent */
.wall[class*="v-"]::before { /* Top surface for thickness */
    top: 0;
    left: 0;
    width: 100%;
    height: var(--wall-thickness);
    transform: translateY(calc(-1 * var(--wall-thickness))) rotateX(90deg) translateZ(calc(var(--wall-thickness) / 2));
    transform-origin: bottom;
}
.wall[class*="v-"]::after { /* Side surface for thickness (right side) */
    top: 0;
    right: 0;
    width: var(--wall-thickness);
    height: 100%;
    /* No rotateY needed for perfect front, but slight allows small side reveal */
    transform: translateX(var(--wall-thickness)) rotateY(0deg) translateZ(calc(var(--wall-thickness) / 2));
    transform-origin: left;
}

/* Smaller connecting wall segments - positioning remains same as structure is fixed */
.wall.small-h-1 { width: 80px; height: 20px; top: 140px; left: 140px; }
.wall.small-v-1 { width: 20px; height: 80px; top: 140px; left: 140px; }

.wall.small-h-2 { width: 80px; height: 20px; top: 350px; left: 140px; }
.wall.small-v-2 { width: 20px; height: 80px; top: 350px; left: 140px; }

.wall.small-h-3 { width: 80px; height: 20px; bottom: 100px; left: 140px; }
.wall.small-v-3 { width: 20px; height: 80px; bottom: 100px; left: 140px; }

.wall.small-h-4 { width: 80px; height: 20px; top: 100px; right: 140px; }
.wall.small-v-4 { width: 20px; height: 80px; top: 100px; right: 140px; }

.wall.small-h-5 { width: 80px; height: 20px; top: 300px; right: 140px; }
.wall.small-v-5 { width: 20px; height: 80px; top: 300px; right: 140px; }

.wall.small-h-6 { width: 80px; height: 20px; bottom: 100px; right: 140px; }
.wall.small-v-6 { width: 20px; height: 80px; bottom: 100px; right: 140px; }

/* Adjusted small connections to central area if needed for new perspective */
.wall.small-h-7 { width: 20px; height: 80px; top: 100px; right: 100px; transform: rotate(90deg) translateZ(calc(var(--element-lift) - 5px));} /* Connects lounge to central */
.wall.small-v-7 { width: 80px; height: 20px; top: 250px; right: 100px; transform: rotate(90deg) translateZ(calc(var(--element-lift) - 5px));} /* Connects lounge to central */

.wall.small-h-8 { width: 80px; height: 20px; bottom: 200px; right: 140px; }
.wall.small-v-8 { width: 20px; height: 80px; bottom: 200px; right: 140px; }


/* Specific pseudo for small walls (adjust as needed for accurate 3D) */
/* The general `::before` and `::after` rules for .wall[class*="h-"] and .wall[class*="v-"] should cover these too. */
/* If specific small segments need different side angles, you'd add overrides here. */

