# Index.html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Jam Digital</title>

    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">

        <h1>JAM DIGITAL</h1>

        <div id="clock">
            00:00:00
        </div>

        <div id="date">
            Loading...
        </div>

    </div>

    <script src="script.js"></script>

</body>
</html>


*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:Arial, Helvetica, sans-serif;
    background:linear-gradient(
        135deg,
        #0f172a,
        #1e293b
    );

    height:100vh;

    display:flex;
    justify-content:center;
    align-items:center;
}

.container{
    text-align:center;
    background:white;
    padding:40px;
    border-radius:20px;
    box-shadow:0 10px 25px rgba(0,0,0,0.3);
}

h1{
    margin-bottom:20px;
    color:#0f172a;
}

#clock{
    font-size:60px;
    font-weight:bold;
    color:#2563eb;
    margin-bottom:15px;
}

#date{
    font-size:20px;
    color:#555;
}

function updateClock(){

    const now = new Date();

    let hours = now.getHours();
    let minutes = now.getMinutes();
    let seconds = now.getSeconds();

    hours = String(hours).padStart(2, "0");
    minutes = String(minutes).padStart(2, "0");
    seconds = String(seconds).padStart(2, "0");

    document.getElementById("clock").innerHTML =
        `${hours}:${minutes}:${seconds}`;

    const options = {
        weekday: "long",
        year: "numeric",
        month: "long",
        day: "numeric"
    };

    document.getElementById("date").innerHTML =
        now.toLocaleDateString("id-ID", options);
}

updateClock();

setInterval(updateClock, 1000);