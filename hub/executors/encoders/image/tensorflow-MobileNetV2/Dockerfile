FROM tensorflow/tensorflow:latest

ADD jina .src

RUN pip install .src/.
RUN python -c "import tensorflow.keras.applications as models; models.MobileNetV2(weights='imagenet')"

ENTRYPOINT ["jina", "pod", "--yaml-path", "KerasImageEncoder"]

