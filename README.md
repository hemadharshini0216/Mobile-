<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Movie Ticket Booking</title>

<style>
body {
  margin: 0;
  font-family: Arial;
  background: #f2f2f2;
}

header {
  background: #111;
  color: white;
  padding: 15px;
  text-align: center;
  font-size: 22px;
}

.container {
  padding: 15px;
}

.movie {
  background: white;
  border-radius: 10px;
  margin-bottom: 15px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  overflow: hidden;
}

.movie img {
  width: 100%;
  height: 220px;
  object-fit: cover;
}

.movie-content {
  padding: 15px;
}

select, input {
  width: 100%;
  padding: 8px;
  margin: 8px 0;
  border-radius: 5px;
  border: 1px solid #ccc;
}

button {
  width: 100%;
  padding: 10px;
  background: #ff3d00;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  background: #e63600;
}
</style>

<script>
function bookTicket(movieName, price, ticketId, showId) {
    let tickets = document.getElementById(ticketId).value;
    let show = document.getElementById(showId).value;

    if (show === "Select Show Time") {
        alert("Please select show time");
        return;
    }

    if (tickets <= 0) {
        alert("Enter valid number of tickets");
        return;
    }

    let total = tickets * price;

    alert(
      "Movie: " + movieName +
      "\nShow: " + show +
      "\nTickets: " + tickets +
      "\nTotal Price: ₹" + total +
      "\n\nBooked Successfully 🎟️"
    );
}
</script>

</head>

<body>

<header>🎬 Movie Ticket Booking</header>

<div class="container">

<!-- Movie 1 -->
<div class="movie">
  <img src="https://images.unsplash.com/photo-1489599849927-2ee91cede3ba">
  <div class="movie-content">
    <h3>Avengers</h3>
    <p>Action | English | ₹150</p>

    <select id="show1">
      <option>Select Show Time</option>
      <option>10:00 AM</option>
      <option>2:00 PM</option>
      <option>6:00 PM</option>
      <option>9:30 PM</option>
    </select>

    <input type="number" id="ticket1" placeholder="Number of Tickets">

    <button onclick="bookTicket('Avengers',150,'ticket1','show1')">
      Book Ticket
    </button>
  </div>
</div>

<!-- Movie 2 -->
<div class="movie">
  <img src="https://images.unsplash.com/photo-1524985069026-dd778a71c7b4">
  <div class="movie-content">
    <h3>Jailer</h3>
    <p>Action | Tamil | ₹120</p>

    <select id="show2">
      <option>Select Show Time</option>
      <option>11:00 AM</option>
      <option>3:00 PM</option>
      <option>7:00 PM</option>
      <option>10:00 PM</option>
    </select>

    <input type="number" id="ticket2" placeholder="Number of Tickets">

    <button onclick="bookTicket('Jailer',120,'ticket2','show2')">
      Book Ticket
    </button>
  </div>
</div>

</div>

</body>
</html>
