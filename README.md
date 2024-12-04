<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dashboard</title>
  <style>
      /* General Styling */
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  background-color: #D44136 ; #0000;
  color: #fff;
}

/* Dashboard Layout */
.dashboard {
  width: 90%;
  max-width: 1200px;
  margin: 20px auto;
}

.profile {
  text-align: center;
  padding: 20px;
  background: #1f2937;
  border-radius: 10px;
  margin-bottom: 20px;
}

.profile-img {
  border-radius: 50%;
  width: 80px;
  margin-bottom: 10px;
}

.tabs {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 10px;
}

.tab {
  background: #1f2937;
  color: #fff;
  border: 1px solid #374151;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
}

.tab.active {
  background: #6366f1;
  border-color: #6366f1;
}

/* Cards */
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  Margin-top: 500px;
}

.card {
  background: #1f2937;
  border-radius: 10px;
  padding: 15px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.card h3 {
  margin: 0 0 10px;
}

.card span {
  color: #9ca3af;
}

.card.work {
  border-left: 5px solid #f87171;
}

.card.play {
  border-left: 5px solid #60a5fa;
}

.card.study {
  border-left: 5px solid #f472b6;
}

.card.exercise {
  border-left: 5px solid #34d399;
} 

Footer {
  font-family: 'Arial', sans-serif;
  margin: 0 0 10px;
  background-color:; 
  color: #fff;
  Padding : 2px
  
  
}
 
  </style>
</head>
<body>
  <div class="dashboard">
    <div class="profile">
      <img src="running man.jpg" alt="profile Picture" class="profile-img">
      <h1>Report for</h1>
      <h2>Jeremy Robson</h2>
      <div class="tabs">
        <button class="tab active">Daily</button>
        <button class="tab">Weekly</button>
        <button class="tab">Monthly</button>
      </div>
    </d) 
    <div class="cards">
       <div class="card work">
        <h3>Work</h3>
        <p>32hrs</p>
        <span>Last Week - 36hrs</span>
      </div>
      <div class="card play">
        <h3>Play</h3>
        <p>10hrs</p>
        <span>Last Week - 8hrs</span>
      </div>
      <div class="card study">
        <h3>Study</h3>
        <p>4hrs</p>
        <span>Last Week - 7hrs</span>
      </div>
      <div class="card exercise">
        <h3>Exercise</h3>
        <p>4hrs</p>
        <span>Last Week - 5hrs</span>
      </div>
    </div>
  </div>
</body>
<script>
    // Sample data for different timeframes
const data = {
  daily: {
    work: { current: "5hrs", previous: "7hrs" },
    play: { current: "2hrs", previous: "3hrs" },
    study: { current: "1hr", previous: "2hrs" },
    exercise: { current: "1hr", previous: "1hr" },
  },
  weekly: {
    work: { current: "32hrs", previous: "36hrs" },
    play: { current: "10hrs", previous: "8hrs" },
    study: { current: "4hrs", previous: "7hrs" },
    exercise: { current: "4hrs", previous: "5hrs" },
  },
  monthly: {
    work: { current: "128hrs", previous: "140hrs" },
    play: { current: "40hrs", previous: "32hrs" },
    study: { current: "16hrs", previous: "28hrs" },
    exercise: { current: "16hrs", previous: "20hrs" },
  },
};

// Select DOM elements
const tabs = document.querySelectorAll(".tab");
const cards = document.querySelectorAll(".card");

// Function to update the cards based on the selected timeframe
function updateCards(timeframe) {
  cards.forEach((card) => {
    const activity = card.classList[1]; // Get activity type (work, play, etc.)
    const { current, previous } = data[timeframe][activity];
    card.querySelector("p").textContent = current;
    card.querySelector("span").textContent = `Last Week - ${previous}`;
  });
}

// Add event listeners to tabs
tabs.forEach((tab) => {
  tab.addEventListener("click", () => {
    // Remove active class from all tabs and add to the clicked tab
    tabs.forEach((t) => t.classList.remove("active"));
    tab.classList.add("active");

    // Update cards based on the selected tab
    const timeframe = tab.textContent.toLowerCase(); // daily, weekly, monthly
    updateCards(timeframe);
  });
});

// Default to weekly data on page load
updateCards("weekly"); 
</script>
<footer>
  <div>
      <p><i>Frontend mentor: Olafisoye Gabriel</i></p>
  </div>
</footer>
</html>
