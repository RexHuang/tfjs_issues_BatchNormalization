# tfjs_issues_BatchNormalization
</br>
tensorflowjs_converter --input_format keras model1.h5 model </br>
tensorflowjs_converter --input_format keras model2.h5 model_not_working
</br>
</br>
</br>
# Model_ok<br>
</br>
model = Sequential()</br>
model.add(Conv2D(filters = 32, kernel_size = (5,5),padding = 'Same', 
                 activation ='relu', input_shape = (28,28,1)))</br>
model.add(Conv2D(filters = 32, kernel_size = (5,5),padding = 'Same', 
                 activation ='relu'))</br>
model.add(MaxPool2D(pool_size=(2,2)))</br>
model.add(Dropout(0.25))</br>
model.add(Conv2D(filters = 64, kernel_size = (3,3),padding = 'Same', 
                 activation ='relu'))</br>
model.add(Conv2D(filters = 64, kernel_size = (3,3),padding = 'Same', 
                 activation ='relu'))</br>
model.add(MaxPool2D(pool_size=(2,2), strides=(2,2)))</br>
model.add(Dropout(0.25))</br>
model.add(Flatten())</br>
model.add(Dense(256, activation = "relu"))</br>
model.add(Dropout(0.5))</br>
model.add(Dense(10, activation = "softmax"))
</br>
</br>
# Model_not_working:<br>
</br>
model = Sequential()</br>
model.add(Conv2D(filters = 32, kernel_size = (5,5),padding = 'Same', 
                 activation ='relu', input_shape = (28,28,1)))</br>
model.add(BatchNormalization())</br>
model.add(Conv2D(filters = 32, kernel_size = (5,5),padding = 'Same', 
                 activation ='relu'))</br>
model.add(BatchNormalization())</br>
model.add(MaxPool2D(pool_size=(2,2)))</br>
model.add(Dropout(0.25))</br>
model.add(Conv2D(filters = 64, kernel_size = (3,3),padding = 'Same', 
                 activation ='relu'))</br>
model.add(BatchNormalization())</br>
model.add(Conv2D(filters = 64, kernel_size = (3,3),padding = 'Same', 
                 activation ='relu'))</br>
model.add(BatchNormalization())</br>
model.add(MaxPool2D(pool_size=(2,2), strides=(2,2)))</br>
model.add(Dropout(0.25))</br>
model.add(Flatten())</br>
model.add(Dense(256, activation = "relu"))</br>
model.add(Dropout(0.5))</br>
model.add(Dense(10, activation = "softmax"))
<br>
<br>
# Output
![structure](https://github.com/RexHuang/tfjs_issues_BatchNormalization/edit/master/output.jpg)
