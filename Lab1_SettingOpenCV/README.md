# Setting up OpenCV in PyCharm

Click on "Files" on the top-right corner of your screen

Click on "Settings" and then to Project: "Name of Your Project"

Click on "Python Interpreter"

Then expand on the box that’s next to "Python Interpreter" and click "Show All"

Click on Python 3.10 so it is highlighted then click "OK"

Click on the "+" sign that is right above "Package"

Search "opencv-python" and then install the package

# Setting up OpenCV in Visual Studio Code

In the instructions provided:
```
python –m venv myvenv

.\myvenv\Scripts\activate

pip install opencv-python
```
I use conda to control the virtual environment(CS5330).
```
conda activate CS5330

pip install opencv-python
```
# Setting up OpenCV in Command Line
Open terminal on Mac

Create virtual environment

Install OpenCV
```
pip install opencv-python
```
Test
```
python -c "import cv2; print(cv2.__version__)"
```
