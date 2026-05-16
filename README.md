# wobble
wobble (DO NOT USE IF SENSITIVE TO FLASHING LIGHTS)
[wobble.html](https://github.com/user-attachments/files/27861165/wobble.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MAXIMUM WOBBLE</title>

<style>
html, body {
    margin: 0;
    overflow: hidden;
    background: black;
    width: 100%;
    height: 100%;
}

#wrapper {
    width: 100vw;
    height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    color: white;
    font-family: Arial;
    font-size: 4rem;
    text-align: center;

    animation: crazyShake 0.08s infinite;
    filter: contrast(150%) saturate(180%);
}

.glow {
    text-shadow:
        0 0 10px white,
        0 0 20px red,
        0 0 40px red;
}

@keyframes crazyShake {
    0% { transform: translate(0px, 0px) rotate(0deg) scale(1); }
    10% { transform: translate(-30px, 20px) rotate(-5deg) scale(1.03); }
    20% { transform: translate(25px, -25px) rotate(4deg) scale(0.98); }
    30% { transform: translate(-40px, 10px) rotate(-6deg) scale(1.05); }
    40% { transform: translate(35px, 25px) rotate(5deg) scale(0.95); }
    50% { transform: translate(-20px, -30px) rotate(-4deg) scale(1.02); }
    60% { transform: translate(30px, 15px) rotate(6deg) scale(1.04); }
    70% { transform: translate(-35px, 20px) rotate(-5deg) scale(0.96); }
    80% { transform: translate(40px, -20px) rotate(4deg) scale(1.05); }
    90% { transform: translate(-25px, 30px) rotate(-6deg) scale(0.97); }
    100% { transform: translate(0px, 0px) rotate(0deg) scale(1); }
}

.flash {
    position: fixed;
    inset: 0;
    background: white;
    opacity: 0;
    pointer-events: none;
}
</style>
</head>
<body>

<div id="wrapper">
    <div class="glow">INVINCIBLE WOBBLE</div>
    <div style="font-size:1.5rem;">💀💀💀</div>
</div>

<div class="flash" id="flash"></div>

<script>
const flash = document.getElementById("flash");

function randomFlash() {
    flash.style.opacity = Math.random() * 0.8;

    setTimeout(() => {
        flash.style.opacity = 0;
    }, 50);

    setTimeout(randomFlash, Math.random() * 300 + 100);
}

randomFlash();

// Random zoom punches
setInterval(() => {
    const wrapper = document.getElementById("wrapper");

    wrapper.style.transform += ` scale(${1 + Math.random() * 0.2})`;

    setTimeout(() => {
        wrapper.style.transform = "";
    }, 80);

}, 200);
</script>

</body>
</html>
