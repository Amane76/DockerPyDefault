# DockerHubのベースとなるイメージを指定
FROM python:3.9-slim

# gitをインストール->apt-getでインストールしたパッケージのキャッシュを削除
RUN apt-get update && \
    apt-get install -y git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# ローカルPCのファイルをコンテナのカレントディレクトリにコピー
# COPY requirements.txt .

# curlをインストール->apt-getでインストールしたパッケージのキャッシュを削除
RUN apt-get update && \
    apt-get install -y git curl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# pipのアップデート->requirements.txtに記載されたパッケージをインストール
RUN pip install --upgrade pip
    # && \ pip install -r requirements.txt

# ... existing code ...

# Poetryのインストールとパスの設定
ENV POETRY_HOME=/opt/poetry
RUN curl -sSL https://install.python-poetry.org | python - && \
    cd /usr/local/bin && \
    ln -s /opt/poetry/bin/poetry

# Poetryが仮想環境を生成しないようにする
RUN poetry config virtualenvs.create false

# ... existing code ...

# コンテナ起動時に実行するコマンドを指定
CMD ["/bin/bash"]
