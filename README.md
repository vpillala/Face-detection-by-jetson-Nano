# Face Recognition on Jetson Nano

This Python script leverages the face_recognition library for face detection and recognition on the Jetson Nano platform. It provides a user-friendly command-line interface for detecting face locations and recognizing known faces in images.

## Features

- **Face Location Detection:** Detects and prints face locations in images.
- **Face Recognition:** Recognizes known faces in images and prints the results.
- **Multi-threaded Processing:** Utilizes multiple CPU cores for faster image processing.
- **Command-Line Interface:** Simple and intuitive command-line options for customization.

## Requirements

- [face_recognition](https://github.com/ageitgey/face_recognition)
- [click](https://click.palletsprojects.com/)

Ensure that these libraries are installed before running the script.

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/face-recognition-jetson.git
    cd face-recognition-jetson
    ```

2. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

### Face Location Detection

To detect face locations in an image, use the following command:

```bash
python script.py location <path_to_image> --cpus <number_of_cpus> --model <face_detection_model> --upsample <upsample_factor>
```

- `path_to_image`: Path to the image file or folder containing images.
- `number_of_cpus`: Number of CPU cores to use in parallel (use -1 for all cores).
- `face_detection_model`: Face detection model to use ("hog" or "cnn").
- `upsample_factor`: How many times to upsample the image looking for faces (higher numbers find smaller faces).

### Face Recognition

To recognize faces in an image, use the following command:

```bash
python script.py recognition <path_to_known_people_folder> <path_to_image> --cpus <number_of_cpus> --tolerance <face_tolerance> --show-distance
```

- `path_to_known_people_folder`: Path to the folder containing images of known individuals.
- `path_to_image`: Path to the image file or folder containing images to be recognized.
- `number_of_cpus`: Number of CPU cores to use in parallel (use -1 for all cores).
- `face_tolerance`: Tolerance for face comparisons (default is 0.6).
- `--show-distance`: Output face distance for tweaking tolerance setting.

## Examples

### Face Location Detection

```bash
python script.py location images/sample_image.jpg --cpus 2 --model cnn --upsample 1
```

### Face Recognition

```bash
python script.py recognition known_people_folder/ test_images/ --cpus 4 --tolerance 0.5 --show-distance
```

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use and modify it for your needs.

---

Feel free to customize this README based on your specific project details and preferences. Include additional sections, such as "Troubleshooting," "Contributing," or any other relevant information that would be helpful for users and contributors.
