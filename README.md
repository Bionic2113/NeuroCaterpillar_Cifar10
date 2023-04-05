# NeuroCaterpillar_Cifar10

Нейросеть, классифицирующая объекты из датасета cifar10.
Создали с помощью сверточных и полносвязных слоев. Без папки находится ноутбук, в котором увеличено количество нейронов в полносвязных слоях, а в папке в сверточных. 

Настройка нейросети с увеличенным количеством нейронов в сверточных слоях:

Установка слоёв для модели
```python
keras.layers.InputLayer(input_shape=(32, 32, 3)),# указан размер картинки и количество цветов это для Conv2D
keras.layers.Conv2D(32, (3, 3), activation='relu', padding='same'),
keras.layers.Conv2D(64, (3, 3), activation='relu', padding='same'),
keras.layers.MaxPooling2D(2, 2),
keras.layers.Conv2D(128, (3, 3), activation='relu', padding='same'),
keras.layers.Conv2D(128, (3, 3), activation='relu', padding='same'),
keras.layers.MaxPooling2D(2, 2),
keras.layers.Flatten(),# это надо для того, чтобы Dense смогло зайти
keras.layers.Dense(92, activation="relu"),
keras.layers.Dense(46, activation="relu"),
keras.layers.Dense(10, activation="softmax")
```

Компиляция модели
```python
model.compile(optimizer=tf.keras.optimizers.Adam(), loss='sparse_categorical_crossentropy', metrics=['accuracy'])
```

Обучение модели

```python
model.fit(x_train, y_train, epochs=14)
Epoch 1/14
1563/1563 [==============================] - 119s 75ms/step - loss: 1.4005 - accuracy: 0.4905
Epoch 2/14
1563/1563 [==============================] - 116s 74ms/step - loss: 0.9192 - accuracy: 0.6754
Epoch 3/14
1563/1563 [==============================] - 116s 74ms/step - loss: 0.7432 - accuracy: 0.7416
Epoch 4/14
1563/1563 [==============================] - 116s 74ms/step - loss: 0.6274 - accuracy: 0.7805
Epoch 5/14
1563/1563 [==============================] - 117s 75ms/step - loss: 0.5322 - accuracy: 0.8141
Epoch 6/14
1563/1563 [==============================] - 117s 75ms/step - loss: 0.4444 - accuracy: 0.8438
Epoch 7/14
1563/1563 [==============================] - 117s 75ms/step - loss: 0.3671 - accuracy: 0.8699
Epoch 8/14
1563/1563 [==============================] - 116s 74ms/step - loss: 0.3077 - accuracy: 0.8910
Epoch 9/14
1563/1563 [==============================] - 117s 75ms/step - loss: 0.2629 - accuracy: 0.9078
Epoch 10/14
1563/1563 [==============================] - 116s 74ms/step - loss: 0.2169 - accuracy: 0.9234
Epoch 11/14
1563/1563 [==============================] - 118s 75ms/step - loss: 0.1823 - accuracy: 0.9346
Epoch 12/14
1563/1563 [==============================] - 118s 75ms/step - loss: 0.1640 - accuracy: 0.9413
Epoch 13/14
1563/1563 [==============================] - 117s 75ms/step - loss: 0.1476 - accuracy: 0.9480
Epoch 14/14
1563/1563 [==============================] - 116s 74ms/step - loss: 0.1360 - accuracy: 0.9536
```

Итоговый результат
```
Test loss: 1.2749401330947876
Test accuracy: 0.7448999881744385
```
<img src="https://github.com/Bionic2113/NeuroCaterpillar_Cifar10/blob/main/cifar/imaga1.png" width="500">

<img src="https://github.com/Bionic2113/NeuroCaterpillar_Cifar10/blob/main/cifar/imaga2.png" width="500">
