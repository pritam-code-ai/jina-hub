FROM pytorch/pytorch:1.4-cuda10.1-cudnn7-runtime

RUN pip install transformers --no-cache-dir --compile && \
    python -c "from transformers import *; x='bert-base-uncased'; BertModel.from_pretrained(x); BertTokenizer.from_pretrained(x)"

# jina is not public yet, so we add from the local host and install it
ADD jina .src

RUN pip install .src/.

ENTRYPOINT ["jina", "pod", "--yaml-path", "TransformerTorchEncoder"]