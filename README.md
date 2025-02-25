# my_aicte_stego_project

Overview
This repository provides two implementations of image steganography for securely embedding and retrieving secret messages within digital images:
1.	Without GUI (Basic LSB Steganography) – A straightforward implementation that embeds data sequentially in pixel values.
2.	With GUI (Enhanced Stealth Mode) – A more advanced method that randomizes pixel selection based on password hashing, making detection significantly harder.
By comparing the pixel logs generated in both methods, we can analyze the effectiveness of Stealth Mode in reducing detectability.

Features
Without GUI (Basic LSB Steganography)
•	Sequential LSB Embedding – Modifies the least significant bits (LSBs) of pixel values in a fixed order.
•	Easier to Detect – Since pixels are modified sequentially, it is susceptible to statistical steganalysis.
•	Password Protection for Retrieval – A hashed password ensures only authorized users can extract the message.
With GUI (Advanced Stealth Mode)
•	Randomized Pixel Selection – Embeds data non-sequentially based on a password-derived seed.
•	Difficult to Detect – Pixel modifications appear randomized, reducing statistical anomalies.
•	Password-Based Security – Only the correct password regenerates the same pixel order, making unauthorized extraction impossible.
•	Graphical Interface for Usability – Users can select an image, enter a password, and encrypt/decrypt with ease.

File Descriptions
Jupyter Notebooks
•	Encryption_stego_without_gui&stealthmode.ipynb – Implements sequential LSB encoding without stealth mode.
•	Decryption_stego_without_gui&stealthmode.ipynb – Implements decryption for basic LSB encoding, extracting the message in order.
•	stego_with_gui&stealthmode.ipynb – GUI-based implementation that uses randomized pixel selection for enhanced security.
Images
•	Sunflower.webp – Original cover image.
•	encryptedImage__without_gui&stealthMode.png – Output stego-image generated using basic LSB embedding.
•	encryptedImage_with_gui&stealthmode.png – Output stego-image generated using stealth mode (randomized LSB embedding).
Text Files
•	message.txt – Contains the secret message to be embedded in the image.
•	password_hash.txt – Stores the hashed password for authentication.
•	pixel_log_without_gui&stealthMode.txt – Stores the sequential pixel modifications from the basic LSB method.
•	pixel_log_stego_with_gui&stealthmode.txt – Stores the randomized pixel modifications from stealth mode encryption.

Installation
1. Clone the Repository: 
   git clone  
   cd 
   
3. Set Up a Virtual Environment (Optional):
   python3 -m venv venv
   source venv\Scripts\activate  # On Windows
4. Install Dependencies: 
   pip install -r requirements.txt

Usage:
Without GUI
Encryption
1.	Open Encryption_stego_without_gui&stealthmode.ipynb in Jupyter Notebook.
2.	Run all cells to: 
   -Load the cover image.
   -Embed the secret message sequentially in the LSBs.
   -Save the stego-image as encryptedImage__without_gui&stealthMode.png.
Decryption
1.	Open Decryption_stego_without_gui&stealthmode.ipynb in Jupyter Notebook.
2.	Run all cells to: 
   -Verify the password.
   -Extract the hidden message using sequential LSB extraction.

With GUI (Stealth Mode Enabled)
1.	Run stego_with_gui&stealthmode.ipynb.
2.	Select the cover image and text file.
3.	Enter a password for encryption.
4.	Click "Encrypt Image" to generate encryptedImage_with_gui&stealthmode.png.
5.	To retrieve the hidden message, enter the correct password and select the stego-image.
6.	Click "Decrypt Message" to reveal the secret message.

Comparing Stealth Mode and Sequential LSB Embedding

Why Compare the Pixel Log Files?
The pixel log files provide a detailed record of which pixels were modified during encryption. Analyzing these logs highlights the differences between Stealth Mode (randomized embedding) and Sequential LSB embedding (basic method).

Pixel Selection:
1. Without Stealth Mode (Sequential LSB): Pixels are modified sequentially, moving row by row across the image.
2. With Stealth Mode (Randomized LSB): Pixels are modified randomly, determined by a password-derived seed.

Predictability:
1. Without Stealth Mode: The pixel modifications follow a highly predictable pattern, making them easy to detect using statistical steganalysis.
2. With Stealth Mode: The selection pattern changes every time a different password is used, making it unpredictable and much harder to analyze.

Detection Risk:
1. Without Stealth Mode: The fixed modification order increases the risk of detection, as analysis tools can recognize structured changes.
2. With Stealth Mode: Since modifications appear randomly distributed, detection becomes significantly more difficult.
   
Security Strength:
1. Without Stealth Mode: If an attacker knows the sequential embedding order, they can extract the hidden message without needing the password.
2. With Stealth Mode: Message extraction is impossible without the correct password, as the pixel mapping is unique for each encryption.

How to Compare the Pixel Log Files
1.	Open the log files side by side
   -pixel_log_without_gui&stealthMode.txt (Sequential LSB method)
   -pixel_log_stego_with_gui&stealthmode.txt (Stealth Mode method)
2.	Analyze the modification patterns
   -Sequential LSB: Pixels are modified in order, creating a pattern.
   -Stealth Mode: Modifications are randomized, reducing detectability.

Key Findings from Pixel Log Analysis
•	Sequential LSB is easier to detect due to structured modifications.
•	Stealth Mode reduces detection risk by making modifications appear as random noise.
•	Stealth Mode makes unauthorized extraction impossible without the correct password.

This confirms that Stealth Mode significantly enhances the security of the embedded message by introducing unpredictability.


