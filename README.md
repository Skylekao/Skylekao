- 👋 Hi, I’m @Skylekao
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Skylekao/Skylekao is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
let brushSize = 10;
let hue = 0;

function setup() {
    // Create canvas and place it in the HTML container
    const canvas = createCanvas(600, 400);
    canvas.parent('canvas-container');
    colorMode(HSB, 360, 100, 100); // Use HSB color mode for dynamic color changes
    noStroke();
    background(255);
}

function draw() {
    if (mouseIsPressed) {
        fill(hue, 80, 90, 0.5); // Semi-transparent fill for blending
        ellipse(mouseX, mouseY, brushSize, brushSize);
        hue = (hue + 1) % 360; // Cycle through hues
        brushSize = map(mouseX, 0, width, 5, 20); // Brush size changes with X position
    }
}

function keyPressed() {
    if (key === 'C' || key === 'c') {
        background(255); // Clear the canvas when 'C' is pressed
    }
}
