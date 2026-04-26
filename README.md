<div id="typewriter"></div>

<style>
#typewriter {
  font-family: monospace;
  font-size: 24px;
  white-space: pre;
}
</style>

<script>
const texts = ["hello world.", "dauduchieu"];
let currentTextIndex = 0;
let currentCharIndex = 0;
let isTyping = true;
const element = document.getElementById('typewriter');

function type() {
  const text = texts[currentTextIndex];
  if (isTyping) {
    element.textContent = text.substring(0, currentCharIndex + 1);
    currentCharIndex++;
    if (currentCharIndex === text.length) {
      isTyping = false;
      setTimeout(type, 1000); // pause after typing
    } else {
      setTimeout(type, 100); // typing speed
    }
  } else {
    element.textContent = text.substring(0, currentCharIndex);
    currentCharIndex--;
    if (currentCharIndex < 0) {
      isTyping = true;
      currentTextIndex = (currentTextIndex + 1) % texts.length;
      setTimeout(type, 500); // pause before next text
    } else {
      setTimeout(type, 50); // erasing speed
    }
  }
}

type();
</script>

![Profile views](https://komarev.com/ghpvc/?username=dauduchieu)
