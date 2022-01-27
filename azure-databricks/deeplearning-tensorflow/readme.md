# Distributed Training with TensorFlow 2

tensorflow.distribute.Strategy is a TensorFlow API to distribute training across multiple GPUs or multiple machines. The spark-tensorflow-distributor package helps you to launch distributed training tasks using a Spark job in barrier mode. Users only need to provide a train() function that runs the single-node training code on a GPU or worker node and the package will handle all the configurations for you.

This notebook demonstrates how to use MirroredStrategyRunner in spark-tensorflow-distributor package to do distributed training. It will also show how to use your own custom Strategy. The example is adapted from https://www.tensorflow.org/tutorials/distribute/multi_worker_with_keras.

# Setup Requirements

-> Databricks Runtime ML 7.0 and above

-> (Recommended) GPU instances