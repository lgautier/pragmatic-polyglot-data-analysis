# pragmatic-polyglot-data-analysis

Base Docker container to perform data analysis using:
- SQL (able to run locally using SQLite)
- Python
  * accelaration using LLVM
- R
- Spark (able to run a local spark session)

The container is based on rpy2's container: it can run standalone on a single machine, making it well-suited for teaching, learning, or experimenting with the jupyter notebook work off-the-shelf.

To start a Jupyter notebook:
```
docker run -p 8888:8888 --rm lgautier/pragmatic-polyglot-analysis
```
