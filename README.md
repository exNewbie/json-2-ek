# json-2-ek
Import JSON files to your local Elastic Search + Kibana

```
:$ cd /tmp/

:/tmp$ git clone https://github.com/exNewbie/json-2-ek.git
Cloning into 'json-2-ek'...
Unpacking objects: 100% done.


:/tmp$ cd json-2-ek/
:/tmp/json-2-ek$ cd 1-ek-es/
:/tmp/json-2-ek/1-ek-es$ ./start-v6 
bf50378fb1cae3f4062661dc6ad219d8baf01ca01b34d00c794e4641f77c1432
:/tmp/json-2-ek/1-ek-es$ docker ps
CONTAINER ID        IMAGE                                                     COMMAND                  CREATED             STATUS                  PORTS                                            NAMES
bf50378fb1ca        docker.elastic.co/elasticsearch/elasticsearch-oss:6.3.0   "/usr/local/bin/dock…"   6 seconds ago       Up Less than a second   0.0.0.0:9200->9200/tcp, 0.0.0.0:9300->9300/tcp   elasticsearch-v6


:/tmp/json-2-ek/1-ek-es$ cd ../2-ek-kibana/
:/tmp/json-2-ek/2-ek-kibana$ ./start-v6 elasticsearch-v6
6119e15c0cfe3da7f1e920ab6df08219bad123961cc52d83be3f264f6340a8c5
:/tmp/json-2-ek/2-ek-kibana$ docker ps
CONTAINER ID        IMAGE                                                     COMMAND                  CREATED             STATUS                  PORTS                                            NAMES
6119e15c0cfe        docker.elastic.co/kibana/kibana-oss:6.3.0                 "/bin/bash -c /usr/l…"   5 seconds ago       Up 3 seconds            0.0.0.0:5601->5601/tcp                           kibana-v6
bf50378fb1ca        docker.elastic.co/elasticsearch/elasticsearch-oss:6.3.0   "/usr/local/bin/dock…"   29 seconds ago      Up Less than a second   0.0.0.0:9200->9200/tcp, 0.0.0.0:9300->9300/tcp   elasticsearch-v6


:/tmp/json-2-ek/2-ek-kibana$ cd ../3-python-import/
:/tmp/json-2-ek/3-python-import$ ./start elasticsearch-v6 /tmp/json-source
f706860bb712629e788be087ca6d46e4234319aa42ab5939a6fe960e7d90e70b
:/tmp/json-2-ek/3-python-import$ docker ps
CONTAINER ID        IMAGE                                                     COMMAND                  CREATED              STATUS                          PORTS                    NAMES
f706860bb712        python:latest                                             "/bin/bash -c 'pip i…"   7 seconds ago        Up 6 seconds                                             json-2-ek
6119e15c0cfe        docker.elastic.co/kibana/kibana-oss:6.3.0                 "/bin/bash -c /usr/l…"   About a minute ago   Up About a minute               0.0.0.0:5601->5601/tcp   kibana-v6
bf50378fb1ca        docker.elastic.co/elasticsearch/elasticsearch-oss:6.3.0   "/usr/local/bin/dock…"   About a minute ago   Restarting (1) 24 seconds ago                            elasticsearch-v6


:/tmp/json-2-ek/3-python-import$ docker logs json-2-ek
Collecting elasticsearch
  Downloading https://files.pythonhosted.org/packages/7a/f9/870969b7479a7d507215ee26c66a246b513145242fe910c1394e0766382d/elasticsearch-6.3.0-py2.py3-none-any.whl (119kB)
Collecting python-dateutil
  Downloading https://files.pythonhosted.org/packages/cf/f5/af2b09c957ace60dcfac112b669c45c8c97e32f94aa8b56da4c6d1682825/python_dateutil-2.7.3-py2.py3-none-any.whl (211kB)
Collecting urllib3>=1.21.1 (from elasticsearch)
  Downloading https://files.pythonhosted.org/packages/bd/c9/6fdd990019071a4a32a5e7cb78a1d92c53851ef4f56f62a3486e6a7d8ffb/urllib3-1.23-py2.py3-none-any.whl (133kB)
Collecting six>=1.5 (from python-dateutil)
  Downloading https://files.pythonhosted.org/packages/67/4b/141a581104b1f6397bfa78ac9d43d8ad29a7ca43ea90a2d863fe3056e86a/six-1.11.0-py2.py3-none-any.whl
Installing collected packages: urllib3, elasticsearch, six, python-dateutil
Successfully installed elasticsearch-6.3.0 python-dateutil-2.7.3 six-1.11.0 urllib3-1.23
Processing filename /mnt/0000370180000_WAFWebACL_20180627082716.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627083024.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627081434.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627081923.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627082838.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627082647.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627082922.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627083422.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627082424.json.gz
Processing filename /mnt/0000370180000_WAFWebACL_20180627082741.json.gz
Work finished
```
