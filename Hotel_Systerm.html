<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Punleu.Mini-Hotel</title>
<style>
:root {
  --primary: #0a4d92;
  --accent: #f4b400;
  --light: #f9fafc;
  --dark: #1e1e1e;
  --radius: 12px;
  --shadow: 0 4px 20px rgba(0,0,0,0.08);
}

body {
  font-family: "Segoe UI", Roboto, sans-serif;
  background: var(--light);
  margin: 0;
  padding: 0;
  color: var(--dark);
}

/* HEADER */
header {
  background: linear-gradient(135deg, var(--primary), #083b73);
  color: white;
  text-align: center;
  padding: 40px 20px;
  font-size: 32px;
  font-weight: bold;
  letter-spacing: 1px;
  box-shadow: var(--shadow);
}

/* NAVBAR */
nav {
  background: white;
  display: flex;
  justify-content: center;
  gap: 40px;
  padding: 14px;
  border-bottom: 1px solid #e6e6e6;
  position: sticky;
  top: 0;
  z-index: 10;
}
nav a {
  color: var(--primary);
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}
nav a:hover {
  color: var(--accent);
}
nav a.active {
  border-bottom: 3px solid var(--accent);
  padding-bottom: 6px;
}

/* MAIN */
main {
  padding: 30px;
  max-width: 1100px;
  margin: auto;
  animation: fadeIn 0.5s ease;
}
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

/* CARD */
.card {
  background: white;
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  padding: 20px 24px;
  margin-bottom: 24px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.card:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 24px rgba(0,0,0,0.1);
}

/* FORM ELEMENTS */
label {
  display: block;
  margin-top: 12px;
  color: #333;
  font-weight: 500;
}
input, select, textarea {
  width: 100%;
  padding: 10px;
  margin-top: 6px;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 15px;
}
button {
  padding: 10px 18px;
  background: var(--primary);
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 15px;
  margin-top: 14px;
  transition: background 0.3s ease, transform 0.2s ease;
}
button:hover {
  background: #083b73;
  transform: scale(1.03);
}

/* TABLE */
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 14px;
  background: white;
  border-radius: var(--radius);
  overflow: hidden;
  box-shadow: var(--shadow);
}
th, td {
  padding: 14px;
  text-align: left;
}
th {
  background: var(--primary);
  color: white;
}
tr:nth-child(even) {
  background: #f6f8fc;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  nav { flex-wrap: wrap; gap: 16px; }
  header { font-size: 26px; }
  main { padding: 20px; }
}
</style>
</head>
<body>

<header>Punleu.Mini-Hotel</header>
<nav>
  <a href="#home" class="active">Home</a>
  <a href="#rooms">Rooms</a>
  <a href="#book">Book</a>
  <a href="#admin">Admin</a>
</nav>

<main id="view"></main>

<script>
// ===== DATA =====
const ROOMS = [
  {id:'101', name:'Single Room', type:'Single', price:30},
  {id:'102', name:'Double Room', type:'Double', price:50},
  {id:'201', name:'Suite', type:'Suite', price:120}
];

const STORAGE_KEY = 'punleu_mini_hotel_bookings';
let bookings = JSON.parse(localStorage.getItem(STORAGE_KEY)) || [];

// ===== ROUTER =====
function navigate() {
  const hash = location.hash.replace('#','') || 'home';
  document.querySelectorAll('nav a').forEach(a =>
    a.classList.toggle('active', a.getAttribute('href') === '#' + hash)
  );
  if(hash==='rooms') renderRooms();
  else if(hash==='book') renderBooking();
  else if(hash==='admin') renderAdmin();
  else renderHome();
}
window.addEventListener('hashchange', navigate);

// ===== VIEWS =====
function renderHome(){
  document.getElementById('view').innerHTML = `
    <div class="card">
      <h2>Welcome to Punleu.Mini-Hotel</h2>
      <p>Experience comfort and elegance at Punleu.Mini-Hotel. Whether you're here for business or leisure, our modern rooms and friendly service will make your stay memorable.</p>
      <p><a href="#rooms"><button>Explore Rooms</button></a></p>
    </div>
  `;
}

function renderRooms(){
  document.getElementById('view').innerHTML = `
    <h2>Available Rooms</h2>
    <label>Check-in: <input type="date" id="filterCheckIn"></label>
    <label>Check-out: <input type="date" id="filterCheckOut"></label>
    <input type="text" id="roomSearch" placeholder="Search rooms by name or type..." style="margin-top:10px;">
    <div id="roomsList"></div>
  `;

  const roomsList = document.getElementById('roomsList');
  const ci = document.getElementById('filterCheckIn');
  const co = document.getElementById('filterCheckOut');
  const search = document.getElementById('roomSearch');

  function displayRooms(){
    roomsList.innerHTML = '';
    const term = search.value.toLowerCase();
    ROOMS.forEach(r=>{
      if(!(`${r.name} ${r.type}`.toLowerCase().includes(term))) return;
      let unavailable = false;
      if(ci.value && co.value){
        unavailable = bookings.some(b=>b.roomId===r.id && !(co.value <= b.checkIn || ci.value >= b.checkOut));
      }
      const card = document.createElement('div');
      card.className = 'card';
      card.style.opacity = unavailable ? 0.6 : 1;
      card.innerHTML = `
        <h3>${r.name} — $${r.price}/night</h3>
        <p>Type: ${r.type}</p>
        <p>Status: ${unavailable ? '<span style="color:red;font-weight:bold;">Booked</span>' : '<span style="color:green;font-weight:bold;">Available</span>'}</p>
        <a href="#book?room=${r.id}&ci=${ci.value}&co=${co.value}">
          <button ${unavailable ? 'disabled' : ''}>Book Now</button>
        </a>
      `;
      roomsList.appendChild(card);
    });
  }

  [ci, co, search].forEach(el => el.addEventListener('input', displayRooms));
  displayRooms();
}

function renderBooking(){
  const params = new URLSearchParams(location.hash.split('?')[1]);
  const preRoom = params.get('room') || '';
  const preCI = params.get('ci') || '';
  const preCO = params.get('co') || '';
  document.getElementById('view').innerHTML = `
    <div class="card">
      <h2>Book Your Stay</h2>
      <form id="bookForm">
        <label>Full Name</label>
        <input id="b_name" required>
        <label>Email</label>
        <input id="b_email" type="email" required>
        <label>Phone</label>
        <input id="b_phone" required>
        <label>Room</label>
        <select id="b_room">${ROOMS.map(r=>`<option value="${r.id}">${r.name}</option>`).join('')}</select>
        <label>Check-in</label>
        <input id="b_ci" type="date" required>
        <label>Check-out</label>
        <input id="b_co" type="date" required>
        <label>Notes</label>
        <textarea id="b_notes" rows="3"></textarea>
        <label><input id="b_consent" type="checkbox" required> I agree to the terms & policy</label>
        <button>Confirm Booking</button>
      </form>
    </div>
  `;
  if(preRoom) document.getElementById('b_room').value = preRoom;
  if(preCI) document.getElementById('b_ci').value = preCI;
  if(preCO) document.getElementById('b_co').value = preCO;

  document.getElementById('bookForm').addEventListener('submit', e=>{
    e.preventDefault();
    const booking = {
      id: Date.now().toString(),
      name: b_name.value.trim(),
      email: b_email.value.trim(),
      phone: b_phone.value.trim(),
      roomId: b_room.value,
      checkIn: b_ci.value,
      checkOut: b_co.value,
      notes: b_notes.value.trim(),
      consent: b_consent.checked,
      status: 'confirmed',
      created: new Date().toISOString()
    };
    if(!booking.name||!booking.email||!booking.phone||!booking.consent) return alert('Fill all required fields.');
    const conflict = bookings.some(b=>b.roomId===booking.roomId && !(booking.checkOut <= b.checkIn || booking.checkIn >= b.checkOut));
    if(conflict) return alert('Room not available for selected dates.');
    bookings.push(booking);
    localStorage.setItem(STORAGE_KEY, JSON.stringify(bookings));
    alert('Booking confirmed!');
    location.hash = '#admin';
  });
}

function renderAdmin(){
  document.getElementById('view').innerHTML = `
    <h2>Admin Dashboard</h2>
    <input type="text" id="searchInput" placeholder="Search by name, email, or room...">
    <table>
      <thead>
        <tr>
          <th>Name</th><th>Email</th><th>Phone</th><th>Room</th><th>Check-in</th><th>Check-out</th><th>Status</th><th>Action</th>
        </tr>
      </thead>
      <tbody id="bookingTableBody"></tbody>
    </table>
  `;
  const tbody = document.getElementById('bookingTableBody');

  function displayBookings(filter=''){
    tbody.innerHTML = '';
    const filtered = bookings.filter(b=>{
      const room = ROOMS.find(r=>r.id===b.roomId) || {name:b.roomId};
      const text = `${b.name} ${b.email} ${b.phone} ${room.name}`.toLowerCase();
      return text.includes(filter.toLowerCase());
    });
    filtered.forEach(b=>{
      const room = ROOMS.find(r=>r.id===b.roomId) || {name:b.roomId};
      const tr = document.createElement('tr');
      tr.innerHTML = `
        <td>${b.name}</td>
        <td>${b.email}</td>
        <td>${b.phone}</td>
        <td>${room.name}</td>
        <td>${b.checkIn}</td>
        <td>${b.checkOut}</td>
        <td>${b.status}</td>
        <td><button data-id="${b.id}" style="background:#c62828;">Cancel</button></td>
      `;
      tbody.appendChild(tr);
    });

    document.querySelectorAll('button[data-id]').forEach(btn=>{
      btn.addEventListener('click', ()=>{
        if(confirm('Cancel this booking?')){
          bookings = bookings.filter(b=>b.id !== btn.dataset.id);
          localStorage.setItem(STORAGE_KEY, JSON.stringify(bookings));
          displayBookings(document.getElementById('searchInput').value);
        }
      });
    });
  }

  displayBookings();
  document.getElementById('searchInput').addEventListener('input', e=>displayBookings(e.target.value));
}

// INIT
navigate();
</script>

</body>
</html>
