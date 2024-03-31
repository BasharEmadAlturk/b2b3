<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootcamp Registration</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <style>
        * {
            font-family: 'Montserrat', sans-serif;
        }

        body {
            height: 80vh;
            margin-top: 5rem;
            background-image: url("https://images.unsplash.com/photo-1595675024853-0f3ec9098ac7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Nnx8Y29kaW5nJTIwYm9vdGNhbXB8ZW58MHx8MHx8&auto=format&fit=crop&w=500&q=60");
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
            padding: 10px;
        }

        .form {
            background-color: #fff;
            border-radius: 5px;
            padding: 15px 25px;
            width: 80%;
            margin: 0 auto;
        }

        .results {
            margin-top: 20px;
        }
    </style>
</head>

<body>
    <div class="form">
        <h1 class="text-center">Bootcamp Registration Form</h1>
        <p class="text-center">Complete this form to express your interest in the upcoming web development bootcamp.</p>
        <form id="userForm">
            <!-- Contact Details -->
            <fieldset class="first-section">
                <legend>Contact Details</legend>
                <div class="form-group">
                    <label for="firstName">First Name</label>
                    <input type="text" class="form-control" id="firstName" name="firstName" placeholder="John" required>
                </div>
                <div class="form-group">
                    <label for="lastName">Last Name</label>
                    <input type="text" class="form-control" id="lastName" name="lastName" placeholder="Doe" required>
                </div>
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" class="form-control" id="email" name="email" placeholder="john.doe@example.com" required>
                </div>
                <div class="form-group">
                    <label for="phone">Phone Number</label>
                    <input type="tel" class="form-control" id="phone" name="phone" placeholder="+1234567890" required>
                </div>
                <div class="form-group">
                    <label for="dob">Date of Birth</label>
                    <input type="date" class="form-control" id="dob" name="dob" required>
                </div>
                <div class="form-group">
                    <label for="gender">Gender</label>
                    <select id="gender" class="form-control" name="gender" required>
                        <option value="Male">Male</option>
                        <option value="Female">Female</option>
                        <option value="Other">Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="address">Address</label>
                    <textarea id="address" class="form-control" name="address" rows="3" required></textarea>
                </div>
            </fieldset>
            <!-- Submit Button -->
            <button type="submit" class="btn btn-primary">Submit</button>
            <!-- Reset Button -->
            <button type="reset" class="btn btn-secondary">Reset</button>
        </form>
    </div>
    <!-- Results Display -->
    <div class="results row mt-5"></div>

    <script>
        const form = document.getElementById('userForm');
        const resultsDiv = document.querySelector('.results');

        form.addEventListener('submit', function (event) {
            event.preventDefault();

            const formData = new FormData(form);
            const fullName = formData.get('firstName') + ' ' + formData.get('lastName');
            const email = formData.get('email');
            const phone = formData.get('phone');
            const dob = formData.get('dob');
            const gender = formData.get('gender');
            const address = formData.get('address');

            const card = `
                <div class="col-md-4">
                    <div class="card">
                        <div class="card-body">
                            <h5 class="card-title">${fullName}</h5>
                            <p class="card-text"><strong>Email:</strong> ${email}</p>
                            <p class="card-text"><strong>Phone:</strong> ${phone}</p>
                            <p class="card-text"><strong>Date of Birth:</strong> ${dob}</p>
                            <p class="card-text"><strong>Gender:</strong> ${gender}</p>
                            <p class="card-text"><strong>Address:</strong> ${address}</p>
                        </div>
                    </div>
                </div>
            `;

            resultsDiv.innerHTML = card;
        });

        form.addEventListener('reset', function () {
            resultsDiv.innerHTML = '';
        });
    </script>
</body>

</html>
