<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Tracking Lokasi</title>
</head>
<body>
  <h2>Website Tracking Lokasi</h2>
  <button onclick="getLocation()">Izinkan & Kirim Lokasi</button>
  <p id="lokasi"></p>

  <script>
    function getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(showPosition, showError);
      } else {
        document.getElementById("lokasi").innerHTML = "GPS tidak didukung";
      }
    }

    function showPosition(position) {
      let lat = position.coords.latitude;
      let lon = position.coords.longitude;

      document.getElementById("lokasi").innerHTML =
        "Latitude: " + lat + "<br>Longitude: " + lon +
        `<br><a href="https://www.google.com/maps?q=${lat},${lon}" target="_blank">
        Buka di Google Maps</a>`;
    }

    function showError(error) {
      document.getElementById("lokasi").innerHTML = "Izin lokasi ditolak";
    }
  </script>
</body>
</html>
