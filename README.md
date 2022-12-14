# Python API Template

ð ä¸ä¸ª**å¿«éé«æ§è½**çãPython API æ¨¡æ¿ã

## 1 ç®å½ç®ä»

```
.
âââ README.md             # ç®ä»
âââ server                # é¨ç½²
â   âââ app.py
âââ conf                  # éç½®
â   âââ default.prod.yml
â   âââ default.test.yml
â   âââ default.yml
âââ util                  # è¾å©
â   âââ arg.py
â   âââ conf.py
â   âââ log.py
â   âââ data_model.py
â   âââ db.py
âââ test                  # æµè¯ï¼å¯éï¼
â   âââ api_test.py
âââ doc                   # ææ¡£ï¼å¯éï¼
âââ log                   # æ¥å¿
âââ Dockerfile            # Docker æåéç½®ï¼å¯éï¼
âââ .dockerignore         # Docker å¿½ç¥éç½®ï¼å¯éï¼
âââ .gitignore            # Git å¿½ç¥éç½®
âââ requirements.txt      # ä¾èµï¼å¯éï¼
âââ LICENSE               # è®¸å¯
```

### 1.1 README.mdï¼ææ¡£ï¼

**ä¸ä¸ªè¯¦å°½çææ¡£æ¯ä»ä¹é½éè¦ï¼** ä»»ä½äººé½å¯ä»¥éè¿ææ¡£å¿«éä¸æãä¹è®¸ä½ ä¼è¯´ï¼æçä»£ç å°±æèªå·±çï¼ä¸åææ¡£ä¹ç¥éãå¯æ¯ä½ è½ä¿è¯ä¸ä¸ªæä»¥åï¼ä½ è¿è®°å¾ä½ å½ååçä»ä¹åï¼ï¼

ä¸ä¸ªå¥½çæ·±åº¦å­¦ä¹ é¡¹ç®ææ¡£åºè¯¥æ¯ææ ·çï¼

1. ç¯å¢ä¾èµè¯´æ
2. å¿«éè¿è¡èæ¬
3. ç±»ä¼¼é¡¹ç®æ¯è¾
4. æ§è½æµè¯ç»æ
5. ç»è´çæ¬è®°å½
6. ç¸å³åèèµæ

åèï¼

1. [å¦ä½åå¥½Githubä¸­çreadmeï¼](https://www.zhihu.com/question/29100816)
2. [å¦ä½ä¸ºä½ çå¼æºé¡¹ç®ç¼åå®ç¨çææ¡£](https://zhuanlan.zhihu.com/p/120399648)

### 1.2 utilï¼è¾å©å·¥å·ï¼

ä¸äºå¸¸è§çè¾å©å½æ°ï¼æ¯å¦ï¼

1. conf éç½®
2. arg åæ°
3. data_model æ°æ®æ¨¡å
4. log æ¥å¿
5. db æ°æ®åº

### 1.3 confï¼éç½®ä¸­å¿ï¼

ææçéç½®é½æ¯ç¨ `YAML`ï¼å®æ¯ `json` æ´å¥½ç¨ï¼å¯ä»¥å¨éç½®ä¸­æ·»å æ³¨éï¼å¹¶ä¸åç°æ¹å¼ä¹æ´ä¸ºç´è§ï¼

éç½®æä»¶çä¸­é´åç§°æ¯ãç¯å¢åéãï¼æ¯å¦ ENV ä¸º `test` æ¶ï¼å°±ä¼è¯»å `default.test.yml` æä»¶ï¼ENV é»è®¤ä¸º `dev`ï¼ä¼è¯»å `default.yml`ï¼ã

å¦ä½ä½¿ç¨ç¯å¢åé ENV å¢ï¼åªéè¦å¨æ§è¡æ¶ï¼æ `-e test` æ·»å å°å½ä»¤çåé¢ã

```shell
python -m server.main -e test
# or
python -m server.main --env test
```

### 1.4 serverï¼é¨ç½²ï¼

ä½¿ç¨ Web æå¡é¨ç½²å°çº¿ä¸ç¯å¢ï¼æ¨èä½¿ç¨ [Sanic](https://sanic.dev/zh/)ã

```shell
python -m server.main
```

### 1.5 testï¼æµè¯ï¼

`api_test.py` æ¯å¯¹ API æ¥å£è¿è¡ååæµè¯ï¼å¾å° QPSï¼æ¯ç§è¯·æ±æ°ï¼ã

`Locust` æ¯ä¸ä¸ªéå¸¸å¥½ç¨çæµè¯å·¥å·ï¼å®éå¸¦ä¸ä¸ª WEB çé¢ï¼éå¸¸æ¹ä¾¿å°å¨æµè§å¨ä¸­è¿è¡åæµã

```shell
locust -f test/api_test.py -u 10 -r 1
```

å¨æµè§å¨ä¸­æå¼ `http://127.0.0.1:8089`ï¼ç¹å» `Start swarming` æé®ï¼å°±å¯ä»¥å¼å§åæµäºï¼

åèï¼
1. [Python unittest: ååæµè¯æ¡æ¶](https://docs.python.org/zh-cn/3/library/unittest.html)
2. [Locust: An open source load testing tool.](https://locust.io)

### 1.6 docï¼ææ¡£ï½å¯éï¼

å¦æé¡¹ç®æ¯è¾å¤æï¼å¯ä»¥å°ææ¡£æ´çå½çº³å°è¿éã

### 1.7 logï¼æ¥å¿ï¼

`util/log.py` ä¼å°æ¥å¿æå¤©è®°å½å°è¿éã

### 1.8 requirements.txt ï¼ä¾èµï¼

é¡¹ç®æéè¦çä¾èµï¼æ¹ä¾¿ä¸é®å®è£ã

```shell
pip install -r requirements.txt -i https://pypi.douban.com/simple
```

åèï¼

1. [æå³ pip çä½¿ç¨](https://www.v2ai.cn/2019/12/20/python/7-pip/)

### 1.9 LICENSEï¼è®¸å¯ï½å¯éï¼

å¦ææ¯å¼æºé¡¹ç®ï¼éè¦æ·»å è®¸å¯è¯ã

åèï¼

1. [ä¸æçæå¼æºè®¸å¯è¯ä¸¨å¼æºç¥è¯ç§æ®](https://pingcap.com/zh/blog/introduction-of-open-source-license)
2. [å¦ä½éæ©å¼æºè®¸å¯è¯ï¼](https://www.ruanyifeng.com/blog/2011/05/how_to_choose_free_software_licenses.html)

## 2 ç¯å¢åå¤

- Ubuntu 18.04 LTS+
- Python 3.7+
- Anaconda 3

> äººçè¦ç­ï¼å¿«ç¨ `*NIX` ï¼

## 3 å®¹å¨åé¨ç½²

```shell
cd python-api-template
# æå
docker build -t python-api:0.1.0 .

# è¿è¡
docker run -d --name python-api -p 9999:9999 \
  -v $PWD/conf/default.test.yaml:/app/conf/default.yaml \
  python-api:0.1.0

# æ¥ç
docker logs -f python-api

# è°ç¨ API
curl --location --request POST 'http://127.0.0.1:9999/test' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "test"
}'
```

## 4 åè

- [Ubuntu ç³»ç»éåä¸è½½](https://cn.ubuntu.com/download)
- [Anaconda ä¸ªäººç](https://www.anaconda.com/products/individual#)
- [TUNA æ¸åå¤§å­¦å¼æºè½¯ä»¶éåç«](https://mirrors.tuna.tsinghua.edu.cn/)

## 5 è®¸å¯è¯

[![](https://award.dovolopor.com?lt=License&rt=MIT&rbc=green)](./LICENSE)
