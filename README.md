<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>مشاركة الموقع</title>
</head>
<body style="font-family: Arial; text-align:center; margin-top:50px;">

<h2>اضغط لمشاركة موقعك</h2>
<button onclick="getLocation()">مشاركة موقعي</button>

<p id="result"></p>

<script>
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition, showError);
  } else {
    document.getElementById("result").innerHTML = "المتصفح لا يدعم تحديد الموقع";
  }
}

function showPosition(position) {
  document.getElementById("result").innerHTML =
    "خط العرض: " + position.coords.latitude +
    "<br>خط الطول: " + position.coords.longitude;
}

function showError(error) {
  document.getElementById("result").innerHTML = "تم رفض مشاركة الموقع";
}
</script>

</body>
</html>
