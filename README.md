Image Forgery Detector
Overview
This project is an Image Forgery Detector application that leverages various image processing and hashing techniques to determine whether two images are similar or if one is a forged version of the other. The application is built using Flask for the backend and employs OpenCV and scikit-image for image processing.

Features
Image Upload: Users can upload two images for comparison.
Similarity Calculation: The application checks the structural similarity index between the two images.
Hash Comparison: The application calculates the MD5 hash of both images to check if they are identical.
Forgery Detection: Based on the similarity and hash comparison, the application determines if one of the images is a forgery.
Technologies Used
Flask: Web framework for Python.
OpenCV: Library for image processing.
scikit-image: Library for image processing in Python.
Jinja2: Template engine for rendering HTML templates.
JavaScript: For handling frontend operations and AJAX requests.
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/ImageForgeryDetector.git
cd ImageForgeryDetector
Create and activate a virtual environment:

bash
Copy code
python -m venv venv
source venv/bin/activate   # On Windows use `venv\Scripts\activate`
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Set the Flask environment variable:

bash
Copy code
export FLASK_APP=app.py  # On Windows use `set FLASK_APP=app.py`
Run the application:

bash
Copy code
flask run --host=0.0.0.0 --port=5000
Usage
Access the Application: Open your web browser and go to http://localhost:5000.
Upload Images: Use the upload form to select and upload two images for comparison.
View Results: The application will display whether the images are similar, identical, or if one is a forgery.
Project Structure
app.py: Main Flask application file that contains routes and business logic.
templates/: Directory containing HTML templates.
static/: Directory containing static files like CSS and JavaScript.
uploads/: Directory where uploaded images are stored.
Implementation Details
Similarity Calculation
The similarity between the images is calculated using the Structural Similarity Index (SSIM) from skimage.metrics. A threshold value is set to determine if the images are similar.

Hash Comparison
MD5 hashing is used to compare the two images. If the hashes are identical, the images are considered the same.

Core Functions
calculate_hash(file_path):

Reads the file in chunks and updates the MD5 hash object.
Returns the hexadecimal hash value of the file.
calculate_md5():

Calculates the hash for both images.
Returns True if the hashes match, otherwise False.
calculate_similarity():

Reads the images in grayscale.
Computes the SSIM between the two images.
Returns True if the SSIM exceeds the threshold, otherwise False.
upload():

Handles the image upload and comparison logic.
Calls calculate_similarity() and calculate_md5() to determine forgery.
Returns the result in JSON format.
Future Enhancements
Enhanced Forgery Detection: Implement more sophisticated algorithms for forgery detection.
User Interface Improvements: Enhance the frontend for a better user experience.
Additional Image Formats: Support more image formats for upload and comparison.
Conclusion
The Image Forgery Detector is a robust application for detecting image forgery using state-of-the-art image processing techniques. It provides a user-friendly interface and accurate results, making it a valuable tool for various applications
