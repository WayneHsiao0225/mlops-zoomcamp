conda env list
conda activate hw2
mlflow --version
python preprocess_data.py --raw_data_path .\data --dest_path ./output
mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./mlruns --host 127.0.0.1 --port 5000