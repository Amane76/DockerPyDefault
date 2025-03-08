# DockerHubのベースとなるイメージを指定
FROM python:3.9-slim

# ローカルPCのファイルをコンテナのカレントディレクトリにコピー
COPY requirements.txt .

# pipのアップデート
RUN pip install --upgrade pip

# pythonパッケージをインストール
RUN pip install -r requirements.txt

# コンテナ起動時に実行するコマンドを指定
CMD ["/bin/bash"]
