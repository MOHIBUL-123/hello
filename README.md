batch_size=64
 
num_classes=10
 
epochs=10
 
def build_model(optimizer):
 
model=Sequential()
 
model.add(Conv2D(32,kernel_size=(3,3),activation='relu',input_shape=input_shape))
 
model.add(MaxPooling2D(pool_size=(2,2)))
 
model.add(Dropout(0.25))
 
model.add(Flatten())
 
model.add(Dense(256, activation='relu'))
 
model.add(Dropout(0.5))
 
model.add(Dense(num_classes, activation='softmax'))
 
model.compile(loss=keras.losses.categorical_crossentropy, optimizer= optimizer, metrics=['accuracy'])
 
return model
 
TRAIN MODELadelta', 'Adagrad', 'Adam', 'RMSprop', 'SGD']
 
for i in optimizers:
 
model = build_model(i)
 
hist=model.fit(x_train, y_train, batch_size=batch_size, epochs=epochs, verbose=1, validation_data=(x_test,y_test)
