# Face & Object Detection API

A real-time image processing system that combines traditional computer vision techniques with modern AI capabilities to detect faces and objects in images or video streams. This project provides both local face detection using OpenCV's Haar Cascade Classifier and AI-powered image analysis using Google's Gemini model.

## Project Overview

This project is a comprehensive image analysis system that can:
- **Detect faces** in images or video streams using OpenCV's Haar Cascade Classifier
- **Analyze images** using Google's Gemini AI model for enhanced insights
- **Process data** via API endpoints, allowing you to send images for detection and receive structured results
- **Log detection results** with detailed coordinates, processing times, and analysis data
- **Provide real-time feedback** with visual bounding boxes around detected objects

The system is designed to be modular, allowing for easy integration into larger applications or standalone use for image analysis tasks.

## Folder Descriptions

### `face_detection/` - Core Detection Module
**Purpose**: Contains the main face detection and AI analysis functionality.

**Technologies Used**:
- **OpenCV (cv2)**: For image processing and face detection using Haar Cascade Classifier
- **Google Gemini AI**: For advanced image analysis and insights
- **LangChain**: For AI model integration and prompt management
- **Python**: Core programming language

**Key Features**:
- Real-time face detection with configurable parameters
- AI-powered image quality assessment
- Automated parameter optimization suggestions
- Comprehensive logging system

### `face_detection/logs/` - Detection Logs
**Purpose**: Stores detailed logs of all detection operations and results.

**Contents**:
- Date-stamped log files (e.g., `2025-06-30_detection_log.txt`)
- Processing time measurements
- Detection coordinates and statistics
- Error handling and debugging information

**Key Features**:
- Automatic log file generation with timestamps
- Detailed performance metrics
- Error tracking and debugging support
- Historical detection data preservation

### `venv/` - Python Virtual Environment
**Purpose**: Isolated Python environment containing all project dependencies.

**Technologies**:
- Python virtual environment
- All required packages and dependencies
- Isolated development environment

## Key Features

### Face Detection Module (`face_detection.py`)
- **Haar Cascade Classifier**: Uses pre-trained models for reliable face detection
- **Real-time Processing**: Optimized for speed with grayscale conversion
- **Configurable Parameters**: Adjustable `scaleFactor`, `minNeighbors`, and `minSize`
- **Visual Feedback**: Draws bounding boxes around detected faces
- **Performance Monitoring**: Tracks processing time and detection accuracy
- **Error Handling**: Robust error management for image loading and processing

### AI Analysis Module (`gimimi.py`)
- **Google Gemini Integration**: Leverages state-of-the-art AI for image analysis
- **Base64 Encoding**: Secure image transmission to AI services
- **Intelligent Insights**: Provides image quality assessment and detection parameter suggestions
- **Structured Output**: Saves AI responses in organized text files
- **Environment Management**: Secure API key handling with `.env` files

### Logging System
- **Automatic Logging**: Creates timestamped log files for each detection session
- **Comprehensive Data**: Records image details, processing times, and detection results
- **Coordinate Tracking**: Stores precise locations of detected faces
- **Performance Metrics**: Monitors system efficiency and accuracy

## Setup Instructions

### Prerequisites
- Python 3.7 or higher
- OpenCV (cv2)
- Google Gemini API key
- LangChain library

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd face-object-detection-api
   ```

2. **Create Virtual Environment**
   ```bash
   python -m venv venv
   ```

3. **Activate Virtual Environment**
   ```bash
   # Windows
   venv\Scripts\activate
   
   # macOS/Linux
   source venv/bin/activate
   ```

4. **Install Dependencies**
   ```bash
   pip install opencv-python
   pip install langchain
   pip install langchain-community
   pip install python-dotenv
   pip install google-generativeai
   ```

5. **Environment Configuration**
   Create a `.env` file in the project root:
   ```env
   GOOGLE_API_KEY=your_google_gemini_api_key_here
   ```

6. **Verify Installation**
   ```bash
   python face_detection/face_detection.py
   ```

## Usage

### Basic Face Detection
```python
# Run the face detection script
python face_detection/face_detection.py
```

The script will:
1. Load the test image (`test1-img.jpg`)
2. Process it using the Haar Cascade Classifier
3. Display the image with bounding boxes around detected faces
4. Save detailed logs to the `logs/` directory

### AI-Powered Image Analysis
```python
# Run the Gemini AI analysis
python face_detection/gimimi.py
```

This will:
1. Encode the image in Base64 format
2. Send it to Google Gemini for analysis
3. Receive insights about image quality and detection parameters
4. Save the AI response to a timestamped file

### Custom Image Processing
To process your own images:
1. Replace `test1-img.jpg` with your image file
2. Update the `image_path` variable in both scripts
3. Run the detection scripts as needed

## File Structure

```
face-object-detection-api/
├── README.md                    # Project documentation
├── face_detection/             # Main detection module
│   ├── face_detection.py       # OpenCV face detection script
│   ├── gimimi.py              # Google Gemini AI integration
│   ├── test1-img.jpg          # Sample test image
│   └── logs/                  # Detection logs directory
│       └── 2025-06-30_detection_log.txt  # Sample log file
└── venv/                      # Python virtual environment
    └── [virtual environment files]
```

### Key Files Explained

- **`face_detection.py`**: Main face detection script using OpenCV
- **`gimimi.py`**: AI-powered image analysis using Google Gemini
- **`test1-img.jpg`**: Sample image for testing (612x408 pixels)
- **`logs/`**: Directory containing all detection logs and results

## Additional Information

### Performance Characteristics
- **Processing Speed**: Typically 0.4-0.6 seconds per image
- **Detection Accuracy**: High accuracy with Haar Cascade Classifier
- **Memory Usage**: Efficient processing with grayscale conversion
- **Scalability**: Modular design allows for easy scaling

### Supported Image Formats
- JPEG (.jpg, .jpeg)
- PNG (.png)
- BMP (.bmp)
- TIFF (.tiff)

### API Integration
The system is designed to be easily integrated into larger applications:
- RESTful API endpoints can be added
- Batch processing capabilities
- Real-time video stream processing
- Custom detection parameters

### Error Handling
- Robust image loading validation
- API key verification
- Graceful error logging
- User-friendly error messages

### Future Enhancements
- Object detection beyond faces
- Real-time video processing
- Web interface for image upload
- Database integration for result storage
- Machine learning model training capabilities

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For questions or issues, please open an issue in the GitHub repository or contact the development team.
