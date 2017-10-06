# ta23-purdue-columbia
TA2/TA3 integration between Purdue and Columbia teams

## Setup Instructions

1. Pull down the latest columbia TA2 Docker image: `docker pull
   qinshi600/columbiata2ta3`.

2. Clone the Modsquad TA3 repository: `git clone
   https://github.com/d3m-purdue/modsquad -b ta23-columbia`.

3. Follow the build instructions at
   https://github.com/d3m-purdue/modsquad/README.md.

6. Download the seed dataset: `curl -O
   https://datadrivendiscovery.org/data/seed_datasets/o_38.tar.gz && gunzip
o_38.tar.gz`.  You may need to do this step through a web browser to handle D3M
credentials.

7. Copy the seed dataset into a shared directory for TA2 and TA3: `mkdir
   /storage && cp -rv o_38 /storage`.

8. Launch the TA2 Docker container: `docker run -it -v /storage:/storage -p
   50001:8080 qinshi600/columbiata2ta3 ta2_ta3`.

9. Launch the TA3 server: `cd modsquad && PORT=8080
   JSON_CONFIG_PATH=./config.json npm run serve`.

10. Visit http://localhost:8080 to try out the integration.
