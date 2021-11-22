NAME - ANMOL SALUJA
COLLEGE - IIT (BHU) , Varanasi

Project - Love is Love Hackathon on HackerEarth

Max Score Achieved - 44.16/100

WORK DONE ON JUPYTER NOTEBOOK USING PYTHON 3.8.

LIBRARIES USED - pandas,numpy,tensorflow,keras,pytesseract,OpenCV

APPROACH AND TECHNIQUES USED - 

1. Text from the given image dataset was extracted using OpenCV and Google-Tesseract. Image Processing techniques like grayscaling, dialation using a rectangular kernel (18,18)
, Otsu thresholding and contour detection was done using OpenCV. Image portions enclosed in the list of contours were fed into to the OCR using pytesseract and the text obtained was sotred.

2. Preprocessing of the text obtained was done and non-dictionary words and noises were removed. Varying combination of training and validation data was used (test and train size ranging from 400,000 to 800,000)
3. Sentiment140 dataset(https://www.kaggle.com/kazanova/sentiment140?select=training.1600000.processed.noemoticon.csv) was used for training deep learning model.
4. The data was loaded and preprocessed and converted into vector sequences using tensorflow's Tokenizer. It was subsequently padded as well. Following hyper-parameters were chosen -

     vocabulary size = 250000
     embedding dimension = 32
     maximum length = 100
     truncation type='post'
     unknown word = "<OOV>"

3. Several combinations of Word Embeddings, Bidirectional LSTMs (of 64 units), 1D Convolutional Layers(of 128 and 256 units) and Dense Layers were used. In the end a sigmoid Dense layer was used as the output layer. Models were trained on 5 epochs with Adam optimizers and Cross Entropy loss function.
4. The output was processed in such a way that :
             i) Any predictions > 0.5 will be Positive.
             ii) Any predictions < 0.5 will be Negative
             iii) Any predictions = 0.5 will be Random
5. Furthermore, any image devoid of text will be considered as Random.
6. Finally, the result was exported to a csv file.