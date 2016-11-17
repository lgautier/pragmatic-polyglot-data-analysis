# pragmatic-polyglot-data-analysis

Base Docker container to perform data analysis using:
- SQL (able to run locally using SQLite)
- Python
  * accelaration using LLVM
- R
- Spark (able to run a local spark session)

The container is based on rpy2's container: it can run standalone on a single machine, making it well-suited for teaching, learning, or experimenting with the jupyter notebook work off-the-shelf.

To start a Jupyter notebook:

```bash

docker run -p 8888:8888 --rm lgautier/pragmatic-polyglot-analysis

```

**Note:** Our docker container is running with a non-root user `jupyteruser`.


Persistance of the work is highly desirable in many situations, and we can achieve it by mapping the host's user and group IDs with the IDs in the container. The following
will start a jupyter notebook server that has access to the current working directory on the host. **Note:** check the jupyter notebook and docker security models,
as well as where you are running your notebook (for example private or shared machine, private or public network) before deciding on doing this or choosing to use a particular
working directory.

```bash

docker run -p 8888:8888 \
           --rm \
           -u $(id -u):$(id -g) \
	   -v `pwd`:/home/jupyteruser/work
           lgautier/pragmatic-polyglot-analysis

```



