[![image](https://sigopt.com/static/img/SigOpt_logo_horiz.png?raw=true)](https://sigopt.com)

# Collaborative Filtering Tuning

Example using SigOpt and Spark / MLLib to tune an alternating least squares algorithm (ALS) for collaborative filtering.

## Setup

1. Log in to your SigOpt account at [https://app.sigopt.com](https://app.sigopt.com)
2. Find your API Token on the [API tokens page](https://app.sigopt.com/tokens) and set it 
  as the `SIGOPT_API_TOKEN` environment variable.
3. `git clone https://github.com/sigopt/sigopt-examples.git`
4. `cd sigopt-examples/spark/recommender_sys`
5. `sudo ./setup_env.sh`   (Note this assumes you are running on master node of spark-ec2 cluster)
6. `sbt assembly`
7. submit job to spark :
```
/root/spark/bin/spark-submit \
   --master spark://<YOUR_SPARK_MASTER_DNS>:7077 \
   --class MovieLensExperiment \
   target/scala-2.10/movie-lens-sigopt-assembly-1.0.jar  # Might be scala-2.11, dep. on your version
```
