<template>
  <div class="page">
    <div class="container">
      <!-- Gradient top bar -->
      <div class="top-bar"></div>

      <!-- HEADER -->
      <header class="site-header">
        <img src="./assets/36.png" alt="Logo" class="logo" />
        <h1 class="site-name">Alge<span class="highlight">Nova</span></h1>
      </header>

      <!-- INPUT -->
      <textarea
        v-model="input"
        placeholder="Enter a problem to solve..."
        class="input-box"
        @keydown.enter.exact.prevent="solve"
        @keydown.enter.shift.exact
      ></textarea>

      <!-- BUTTON -->
      <button class="solve-btn" @click="solve">Solve</button>

      <!-- OUTPUT -->
      <div class="output-box">
        <span v-if="!output" class="placeholder"> The solution will appear here. </span>
        <span v-else>{{ output }}</span>
      </div>

      <!-- DESCRIPTION -->
      <div class="description">
        AlgeNova is a tool where students can input equations or algorithmic problems and get
        step-by-step solutions powered by AI. Just type and hit Enter!
      </div>

      <!-- FOOTER -->
      <footer class="footer">© 2025 AlgeNova. All rights reserved.</footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: '',
      output: '',
    }
  },
  methods: {
    solve() {
      if (!this.input.trim()) {
        this.output = 'Please enter something.'
        return
      }

      this.output = `🔍 Solving: "${this.input}"\n\n(This is just frontend. Backend will process the real solution.)`
    },
  },
}
</script>

<style scoped>
body {
  font-family: 'Poppins', sans-serif;
}
/* 🌐 PAGE BACKGROUND */
.page {
  min-height: 100vh;
  background: linear-gradient(135deg, #f8f9ff, #eef2ff);
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 2rem 1rem;
}

/* 📦 MAIN CONTAINER */
.container {
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 10px 35px rgba(0, 0, 0, 0.08);
  padding: 2rem;
  width: 100%;
  max-width: 720px;
}

/* 🔹 TOP GRADIENT BAR */
.top-bar {
  height: 6px;
  width: 100%;
  background: linear-gradient(90deg, #5a40f7, #a26cf7);
  border-radius: 6px;
  margin-bottom: 1.5rem;
}

/* HEADER */
.site-header {
  display: flex;
  align-items: center;
  gap: 14px;
  margin-bottom: 1.5rem;
}

.logo {
  width: 65px;
  height: 65px;
  border-radius: 12px;
  object-fit: contain;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.site-name {
  font-size: 2rem;
  font-weight: 700;
  color: #1a1a1a;
}

.highlight {
  color: #5a40f7;
}

/* INPUT */
.input-box {
  width: 100%;
  max-width: 100%;
  box-sizing: border-box;
  min-height: 100px;
  padding: 0.85rem;
  font-size: 1rem;
  border-radius: 12px;
  border: 1px solid #ddd;
  margin-bottom: 1rem;
  resize: vertical;
  background: #fafafa;
}

/* BUTTON */
.solve-btn {
  width: 100%;
  padding: 0.85rem;
  background: #4b6cff;
  color: #fff;
  border: none;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  margin-bottom: 1.5rem;
  transition: background 0.2s ease;
}
.solve-btn:hover {
  background: #3a56d4;
}

/* OUTPUT */
.output-box {
  background: #f9f9ff;
  padding: 1rem;
  border-radius: 12px;
  min-height: 80px;
  font-size: 1rem;
  white-space: pre-line;
  margin-bottom: 1.5rem;
}

.placeholder {
  color: #aaa;
}

/* DESCRIPTION */
.description {
  font-size: 1rem;
  color: #333;
  background: #f9f9ff;
  padding: 1rem 1.2rem;
  border-left: 4px solid #5a40f7;
  border-radius: 12px;
  margin-bottom: 1.8rem;
  line-height: 1.4;
}

/* FOOTER */
.footer {
  text-align: center;
  font-size: 0.9rem;
  color: #888;
}

/* 📱 MOBILE FIXES */
@media (max-width: 480px) {
  .site-name {
    font-size: 1.5rem;
  }
  .logo {
    width: 55px;
    height: 55px;
  }
  .container {
    padding: 1.5rem;
  }
}
</style>
