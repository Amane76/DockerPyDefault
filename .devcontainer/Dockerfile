# DockerHubのベースとなるイメージを指定
FROM python:3.9-slim

# gitをインストール->apt-getでインストールしたパッケージのキャッシュを削除
RUN apt-get update && \
    apt-get install -y git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# ローカルPCのファイルをコンテナのカレントディレクトリにコピー
COPY requirements.txt .

# pipのアップデート->requirements.txtに記載されたパッケージをインストール
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# コンテナ起動時に実行するコマンドを指定
CMD ["/bin/bash"]
