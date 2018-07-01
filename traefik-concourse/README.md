



What I get:

```
> fly -t ci login -c http://bot.deltashim.com
logging in to team 'main'

WARNING:

fly version (3.14.1) is out of sync with the target (3.14.0). to sync up, run the following:

    fly -t ci sync

target saved

> fly -t ci sync
.... stuff... worked...


> fly -t ci execute -c sample_task.yml  --verbose
2018/07/01 22:25:16 GET /api/v1/info HTTP/1.1
Host: bot.deltashim.com
User-Agent: Go-http-client/1.1
Accept-Encoding: gzip


2018/07/01 22:25:16 HTTP/1.1 200 OK
Content-Length: 44
Content-Type: application/json
Date: Sun, 01 Jul 2018 21:25:16 GMT
X-Concourse-Version: 3.14.0
X-Content-Type-Options: nosniff
X-Download-Options: noopen
X-Xss-Protection: 1; mode=block

{"version":"3.14.0","worker_version":"2.1"}

2018/07/01 22:25:16 POST /api/v1/teams/main/builds HTTP/1.1
Host: bot.deltashim.com
User-Agent: Go-http-client/1.1
Content-Length: 310
Content-Type: application/json
Accept-Encoding: gzip

{"id":"5b3946c0","do":[{"id":"5b3946bf","aggregate":[],"on_abort":null},{"id":"5b3946be","task":{"name":"one-off","privileged":false,"config":{"platform":"linux","image_resource":{"type":"docker-image","source":{"repository":"ubuntu"}},"run":{"path":"uname","args":["-a"]}}},"on_abort":null}],"on_abort":null}

2018/07/01 22:25:16 HTTP/1.1 200 OK
Content-Length: 3
Content-Type: application/json
Date: Sun, 01 Jul 2018 21:25:16 GMT
X-Concourse-Version: 3.14.0
X-Content-Type-Options: nosniff
X-Download-Options: noopen
X-Xss-Protection: 1; mode=block

[]

error: json: cannot unmarshal array into Go value of type atc.Build
```
