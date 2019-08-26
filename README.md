# Automated Literature Analysis 
This repository shows an example of how to perform an automated analysis of peer-reviewed scholar literature using Jupyter notebooks and Scopus' citation database. This analysis detects the number of publications over time, popular authors, popular venues, popular affiliations, and popular "topics" that appear within the documents' abstracts (detected using natural language processing).


## Requirements
The notebook requires access to Scopus: A citation database of peer-reviewed literature from scientific journals, books, and conference proceedings. To utilize the Scopus API, you (or your institute) needs a Scopus subscription and you must request an Elsevier Developer API key (see [Elsevier Developers](https://dev.elsevier.com/sc_apis.html) and [Scopus Python API](https://scopus.readthedocs.io/en/latest/) for more information). 

The required Python packages can be found in `requirements.txt`. Creating a virtual Python environment is recommended (for example, `virtualenv` or `conda`). The notebook has been tested using Python 2.7 and Python 3.6. 


# Running using virtualenv
Installation using `virtualenv` is can be using the following commands:

Create virtualenv environment named myenv:
```
virtualenv myenv --python=`which python3`
```

Activate virtual environment
```
source ./myenv/bin/activate
```

Install requirement dependencies.
```
pip3 install -r requirements.txt
```

Install new Jupyther kernel.
```
ipython kernel install --user --name=myenv
```

Run Jupyther and select `myenv` as kernel. Remaining instructions can be found within the notebook itself.
```
jupyther notebook literature_analysis.ipynb --MappingKernelManager.default_kernel_name=myenv
```



## Examples
Below are examples of the notebook's output for the query `title-abs-key("predictive maintenance")`.


![Publications per year](img/years.png)

*Publications per year.*


![Top 50 authors](img/authors.png)

*Top 50 authors.*


![Top 50 publication venues](img/venues.png)

*Top 50 publication venues.*


![Detected topics visualized as word clouds.](img/cloud.png)

*Detected topics visualized as word clouds.*


![Publications embedded into 2D space based on text similarity. Each publication is labeled with its dominant topic.](img/embedding.png)

*Publications embedded into 2D space based on text similarity. Each publication is labeled with its dominant topic.*