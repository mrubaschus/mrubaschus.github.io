layout: page
title: "Home"
permalink: /home

<!DOCTYPE html>
<html>
<head>
    <title>Load Information Entry</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <link href="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/css/select2.min.css" rel="stylesheet" />
    <style>
        body {
            background-color: #f8f9fa;
            font-family: 'Helvetica Neue', Arial, sans-serif;
        }
        .container {
            max-width: 600px;
            margin: auto;
            padding-top: 50px;
            padding-bottom: 50px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.1);
        }
        h1 {
            margin-bottom: 40px;
            color: #003d6f; /* Schuster's blue color */
        }
        label {
            color: #003d6f; /* Schuster's blue color */
            font-weight: bold;
        }
        .form-control {
            border-radius: 0;
            border: none;
            border-bottom: 1px solid #ccc;
            box-shadow: none;
        }
        .form-control:focus {
            border-color: #003d6f; /* Schuster's blue color */
            box-shadow: none;
        }
        button {
            background-color: #003d6f; /* Schuster's blue color */
            border-color: #003d6f; /* Schuster's blue color */
            color: white;
            width: 100%;
            border-radius: 0;
            padding: 15px;
            font-size: 18px;
        }
        #addStop {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <img src="https://schusterco.com/wp-content/uploads/2019/12/Schuster-114.png" alt="Schuster Logo" class="mx-auto d-block">
        <h1 class="text-center">Enter Load Information</h1>
        <form action="/submit_load_info" method="post">
            <div class="form-group">
                <label for="trailerNumber">Trailer Number:</label>
                <input type="text" class="form-control" id="trailerNumber" name="trailerNumber" maxlength="10" required>
            </div>
            <div id="stops">
                <!-- Stop 1 will be added here by default -->
            </div>
            <button type="button" class="btn btn-secondary" id="addStop">Add Stop</button>
            <div class="form-group">
                <label for="pickupDate">Pickup Date:</label>
                <input type="date" class="form-control" id="pickupDate" name="pickupDate" min="2024-06-25" required>
            </div>
            <button type="submit" class="btn btn-primary">Submit</button>
        </form>
    </div>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/js/select2.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
    <script>
        function addStop() {
            var stopsDiv = document.getElementById('stops');
            var stopCount = stopsDiv.childElementCount + 1;
            var stopDiv = document.createElement('div');
            stopDiv.className = 'form-group';
            stopDiv.innerHTML = `
                <label for="stop${stopCount}">Stop ${stopCount}:</label>
                <select class="form-control" id="stop${stopCount}" name="stop${stopCount}">
                    <option value="">Select a stop</option>
                    <option value="stopA">Stop A</option>
                    <option value="stopB">Stop B</option>
                    <!-- Add more options as needed -->
                </select>
                <label for="pieces${stopCount}">Pieces for Stop ${stopCount}:</label>
                <input type="number" class="form-control" id="pieces${stopCount}" name="pieces${stopCount}" min="0">
            `;
            stopsDiv.appendChild(stopDiv);
            $('#stop' + stopCount).select2(); // Initialize Select2 on the new select element
        }

        document.getElementById('addStop').addEventListener('click', addStop);

        // Add the first stop by default
        addStop();
    </script>
</body>
</html>


