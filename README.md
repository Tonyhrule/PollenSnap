# PollenSnap

PollenSnap is a mobile application designed to help individuals manage seasonal allergies by identifying and analyzing allergenic trees in their surroundings. Using advanced image recognition and machine learning algorithms, PollenSnap detects tree species from images and provides users with information about pollen levels, allowing them to avoid high-allergen areas.

## Features

- **Tree Identification**: Snap a photo of trees in your environment, and PollenSnap will identify the species.
- **Pollen Level Analysis**: The app retrieves pollen data for each tree species identified using OpenAI's API, giving users information on the amount of pollen released by each tree.
- **Interactive Allergen Map**: Users can mark allergenic trees on a map to keep track of areas they should avoid.
- **Detailed Tree Information**: Users can fetch additional information on tree species and view preset images for better understanding.

## How it Works

1. **Image Input**: Users upload an image of trees through the app.
2. **Tree Recognition**: The app uses a YOLOv8 model trained with data collected and labeled via Roboflow. This model runs on a Python program, which identifies the tree species in the uploaded image.
3. **Pollen Information**: Once the tree species are identified, the NodeJS server uses OpenAI's API to retrieve information on the pollen levels each species produces.
4. **Results Display**: The app displays the processed image with tree labels and pollen data to the user, along with a map to help them track allergenic trees.

## Model Training

The model is a Convolutional Neural Network (CNN) based on YOLOv8, trained using a custom dataset created with Roboflow. The dataset consists of images of trees from nearby areas, labeled by type to help the model recognize them from new inputs.

## Tech Stack

- **Backend**: NodeJS with ExpressJS to handle API requests.
- **Machine Learning**: Python with YOLOv8 for tree recognition.
- **API Integration**: OpenAI's GPT-3.5 Model API for pollen data and tree information.
- **Mobile Application**: Built using MIT App Inventor for seamless app development and deployment. Below is the APK file compiled using MIT App Inventor.

[Download the PollenSnap APK File](https://drive.google.com/file/d/1JpKKoUbmnOR68rccOzasmxWZHF3y9LzX/view?usp=sharing) for Android devices.

## Directory Structure

```bash
POLLENSNAP/
├── python/
│   ├── best.pt                 # Trained YOLOv8 model
│   ├── main.py                 # Python script for running the tree recognition model
├── src/
│   ├── controllers/
│   │   ├── index.ts            # NodeJS controllers handling API requests and model execution
│   ├── routes/
│   │   ├── index.ts            # API routes
│   ├── index.ts                # Server setup and configurations
│   ├── types.ts                # TypeScript type definitions
├── .gitignore                  # Files and directories to ignore in version control
├── docker-compose.yml          # Docker configuration for multi-container setup
├── Dockerfile                  # Docker setup for the project
├── package.json                # NodeJS dependencies and scripts
├── README.md                   # Project documentation (this file)
├── tsconfig.json               # TypeScript configuration
├── yarn.lock                   # Yarn dependency lock file
```

