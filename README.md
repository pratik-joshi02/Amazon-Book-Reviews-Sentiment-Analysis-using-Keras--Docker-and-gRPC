# Amazon-Book-Reviews-Sentiment-Analysis-using-Keras--Docker-and-gRPC
### Data Set
The dataset for this project is available [here](https://drive.google.com/file/d/14v42um2VRAfQPfGnBJ4QzOie4VZOPK_F/view?usp=sharing). 


### Getting Started

```
$ virtualenv -p python3 tf-serving-amazon
$ source tf-serving-amazon/bin/activate
$ pip3 install -r requirements.txt
```

### Start TensorFlow Serving with Docker

```
$ docker pull tensorflow/serving

$ docker run -p 8500:8500 \
             -p 8501:8501 \
             --mount type=bind,\
             source=/path/to/amazon_review,\
             target=/models/amazon_review \
             -e MODEL_NAME=amazon_review
             -t tensorflow/serving
```
### Run the client

```
$ python3 tf_serving_grpc_client.py
```
