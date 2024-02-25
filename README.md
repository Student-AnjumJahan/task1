<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resume Builder</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <style>
        /* Custom styles */
        .container {
            max-width: 800px;
            margin: 0 auto;
        }
        .preview-container {
            border: 1px solid #ccc;
            padding: 20px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="text-center">Resume Builder</h1>
        <!-- Resume Form -->
        <form id="resumeForm">
            <div class="form-group">
                <label for="fullName">Full Name</label>
                <input type="text" class="form-control" id="fullName" placeholder="Enter your full name" required>
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" class="form-control" id="email" placeholder="Enter your email" required>
            </div>
            <!-- Other fields: Education, Work Experience, Skills, etc. -->
            <button type="submit" class="btn btn-primary">Preview</button>
        </form>

        <!-- Preview Section -->
        <div id="previewSection" class="preview-container" style="display: none;">
            <h2 class="text-center">Preview</h2>
            <div id="resumePreview"></div>
            <button id="downloadPDF" class="btn btn-success">Download as PDF</button>
        </div>
    </div>

    <script>
        // Preview function
        document.getElementById('resumeForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const fullName = document.getElementById('fullName').value;
            const email = document.getElementById('email').value;
            // Fetch other form fields
            // Construct the resume preview HTML
            const previewHTML = `
                <p><strong>Name:</strong> ${fullName}</p>
                <p><strong>Email:</strong> ${email}</p>
                <!-- Include other fields -->
            `;
            // Update the preview section
            document.getElementById('resumePreview').innerHTML = previewHTML;
            document.getElementById('previewSection').style.display = 'block';
        });

        // Download as PDF function
        document.getElementById('downloadPDF').addEventListener('click', function() {
            // Logic to generate and download PDF
            // You can use libraries like jsPDF for PDF generation
            alert('PDF Downloaded!');
        });
    </script>
</body>
</html>
