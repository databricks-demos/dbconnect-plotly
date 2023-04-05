# Databricks Connect ❤️ Data Applications

This is a sample app on how to show how easy it is to build a new application
using [Databricks Connect](https://docs.databricks.com/dev-tools/databricks-connect.html) 
and [Plotly](https://github.com/plotly/dash). 

From DBR 13 onwards, Databricks Connect is now built on open-source Spark Connect. 
Spark Connect introduces a decoupled client-server architecture for Apache Spark™ 
that allows remote connectivity to Spark clusters using the DataFrame API and 
unresolved logical plans as the protocol. With this new architecture based on 
Spark Connect, Databricks Connect becomes a thin client that is simple and easy 
to use! It can be embedded everywhere to connect to Databricks: in IDEs, Notebooks 
and any application, allowing customers and partners alike to build new (interactive) 
user experiences based on their Databricks Lakehouse!

All you need to get started is a Databricks cluster and this simple Python 
application. The dataset used in this application is the standard Databricks `samples` 
dataset.

To get started, create a new virtual environment and install the reuired
dependencies

```commandline
pip install -r requirements.txt
```

To run the application, make sure that you have created a profile for your
workspace in the `~/.databrickscfg` according to the [documentation](https://docs.databricks.com/dev-tools/auth.html#configuration-profiles)
and crearted a cluster with at least Databricks Runtime 13.0 and above.

In the app.py file configure the values for `PROFILE`, `CLUSTER_ID` accordingly.

```python
from databricks.connect.session import DatabricksSession as SparkSession
from databricks.sdk.core import Config

config = Config(profile="PROFILE", cluster_id="CLUSTER_ID")
spark = SparkSession.builder.sdkConfig(config).getOrCreate()
```

Now, run the plotly app

```shell
python app.py
```

![Screenshot](img/SCR-20230405-et1.png)


## Dependencies

This sample application is meant for illustration purposes only. The
application uses the follwing third-party dependencies:

  * Plotly / Dash - https://github.com/plotly/dash - The MIT License (MIT)
  * Tailwind CSS - https://github.com/tailwindlabs/tailwindcss - - The MIT License (MIT)