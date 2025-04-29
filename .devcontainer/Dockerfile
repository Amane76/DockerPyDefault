# --- DockerHubのベースとなるイメージを指定 ---
FROM python:3.13-slim

# --- 基本ツールのインストール ---
# git, curl, build-essential
# ->apt-getでインストールしたパッケージのキャッシュを削除
RUN apt-get update && \
    apt-get install -y \
    git \
    curl \
    build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# --- Python開発環境の構築 ---
# pipのインストールとアップグレード
RUN pip install --upgrade pip

# Poetryのインストールとパスの設定
ENV POETRY_HOME=/opt/poetry
RUN curl -sSL https://install.python-poetry.org | python - && \
    cd /usr/local/bin && \
    ln -s /opt/poetry/bin/poetry

# Poetryが仮想環境を生成しないようにする
RUN poetry config virtualenvs.create false

# 配布用にする場合は以下を追加 ＋ docker-compose.ymlのvolumes設定を削除
# 現在は開発用なので、コピーではなくバインドマウントしています。

# # 作業ディレクトリを設定
# WORKDIR /workspace
# # ホストのプロジェクトルートの内容をコンテナの /workspace にコピー
# COPY . /workspace
# # Poetry の依存関係をインストール
# RUN poetry install

# --- コンテナの設定 ---
# ポート指定
# EXPOSE 8501

# --- コンテナ起動時の設定 ---
CMD ["/bin/bash"]