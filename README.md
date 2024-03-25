# AestheticAI-Generative-Artwork-for-Interior-Design
AestheticAI uses generative AI and stable diffusion to create unique, customized artwork that complements the style and color scheme of a user's interior design.
import os
from PIL import Image
import numpy as np

def simulate_image_generation(style, color_scheme):
    """
    Simulates image generation based on style and color scheme.
    This is a placeholder function where you'd integrate generative AI logic.
    
    Args:
    - style (str): The style of the artwork.
    - color_scheme (str): The primary color scheme of the artwork.
    
    Returns:
    - Image object: Simulated generated artwork.
    """
    # For demo purposes, generate a simple image with random colors
    # In a real application, you'd replace this with calls to a generative AI model.
    np.random.seed(hash(style) ^ hash(color_scheme))
    image_data = np.random.rand(256, 256, 3) * 255
    generated_image = Image.fromarray(image_data.astype('uint8')).convert('RGBA')
    return generated_image

def save_image(image, file_path):
    """
    Saves the generated image to a file.
    
    Args:
    - image (Image object): The image to save.
    - file_path (str): The path to save the image to.
    """
    image.save(file_path)
    print(f"Image saved to {file_path}")

def main():
    # Example user input; in a real application, you might collect this via a GUI or web form
    style = input("Enter the desired style of the artwork: ")
    color_scheme = input("Enter the primary color scheme (e.g., 'warm', 'cool', 'monochrome'): ")
    
    # Generate the artwork based on the input
    generated_artwork = simulate_image_generation(style, color_scheme)
    
    # Save the generated artwork to a file
    file_path = "generated_artwork.png"
    save_image(generated_artwork, file_path)

if __name__ == "__main__":
    main()
