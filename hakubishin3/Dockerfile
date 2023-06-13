# kaggleのpython環境をベースにする
FROM gcr.io/kaggle-gpu-images/python:v126

# ライブラリの追加インストール
RUN conda install -y nodejs

RUN jupyter nbextension enable --py --sys-prefix widgetsnbextension \
 && jupyter labextension install @jupyter-widgets/jupyterlab-manager

