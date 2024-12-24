<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rekonise-like Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
            text-align: center;
        }
        .container {
            margin: 30px auto;
            padding: 20px;
            max-width: 800px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            margin: 10px 0;
        }
        .form-group {
            margin: 15px 0;
        }
        .form-group label {
            display: block;
            font-size: 14px;
            margin-bottom: 5px;
        }
        .form-group input, .form-group select {
            padding: 10px;
            width: 100%;
            font-size: 14px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            margin-top: 15px;
            padding: 10px 20px;
            background-color: #0078D7;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 14px;
        }
        button:hover {
            background-color: #005BB5;
        }
        .output {
            margin-top: 20px;
        }
        .output input {
            width: 80%;
            padding: 10px;
            margin-right: 5px;
        }
        .output button {
            padding: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .output button:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Link Creator</h1>
        <p>Create links with custom actions (follow, subscribe, custom links, etc.)</p>

        <!-- Form for creating links -->
        <div class="form-group">
            <label for="action-type">Select Action Type</label>
            <select id="action-type">
                <option value="follow">Follow on Social Media</option>
                <option value="subscribe">Subscribe to Channel</option>
                <option value="custom">Custom Link</option>
            </select>
        </div>

        <div class="form-group">
            <label for="custom-text">Enter Action Detail (e.g., social link, subscription link)</label>
            <input type="text" id="custom-text" placeholder="Enter action detail...">
        </div>

        <div class="form-group">
            <label for="link-path">Custom Link Path (e.g., yourname)</label>
            <input type="text" id="link-path" placeholder="Path for your link (optional)">
        </div>

        <button id="create-link">Create Link</button>

        <!-- Output generated link -->
        <div class="output" id="output" style="display: none;">
            <h2>Your Generated Link</h2>
            <input type="text" id="generated-link" readonly>
            <button id="copy-link">Copy</button>
        </div>
    </div>

    <script>
        document.getElementById('create-link').addEventListener('click', function() {
            const actionType = document.getElementById('action-type').value;
            const customText = document.getElementById('custom-text').value.trim();
            const linkPath = document.getElementById('link-path').value.trim();

            if (!customText) {
                alert('Please enter the action detail.');
                return;
            }

            // Create base URL
            let linkBase = 'https://alexcirer.github.io/';
            let fullPath = linkPath ? `${linkBase}${linkPath}` : `${linkBase}?action=${actionType}&detail=${encodeURIComponent(customText)}`;

            // Display generated link
            const generatedLink = document.getElementById('generated-link');
            generatedLink.value = fullPath;

            // Show output
            document.getElementById('output').style.display = 'block';
        });

        document.getElementById('copy-link').addEventListener('click', function() {
            const generatedLink = document.getElementById('generated-link');
            generatedLink.select();
            document.execCommand('copy');
            alert('Link copied to clipboard!');
        });
    </script>
</body>
</html>
