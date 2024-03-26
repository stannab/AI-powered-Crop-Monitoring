# AI-powered-Crop-Monitoring
Leverage ML and satellite imagery to monitor crop health, predict yields, and optimize resource allocation for farmers.
import numpy as np
import matplotlib.pyplot as plt

# Mock function to simulate satellite image analysis
# Returns a random mask indicating areas of poor health
def analyze_satellite_image(image):
    # For demo, we return a random mask
    health_mask = np.random.random(image.shape[:2]) > 0.8
    return health_mask

# Mock function to simulate loading a satellite image
# Returns a random image (in a real scenario, you would load actual satellite imagery)
def load_satellite_image(filepath):
    return np.random.rand(100, 100, 3)

# Main function to process an image and display results
def process_image(filepath):
    # Load the image
    image = load_satellite_image(filepath)
    
    # Analyze the image to find areas of poor crop health
    health_mask = analyze_satellite_image(image)
    
    # Highlight areas of concern
    highlighted_image = image.copy()
    highlighted_image[health_mask] = [1, 0, 0]  # Highlight in red
    
    # Display original and processed images
    plt.figure(figsize=(10, 5))
    plt.subplot(1, 2, 1)
    plt.imshow(image)
    plt.title('Original Image')
    plt.axis('off')
    
    plt.subplot(1, 2, 2)
    plt.imshow(highlighted_image)
    plt.title('Areas of Concern')
    plt.axis('off')
    
    plt.show()

# Assuming the image is located at a certain path (in a real scenario, you would provide the actual path)
image_path = 'path/to/satellite/image.jpg'
process_image(image_path)
