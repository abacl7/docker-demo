# docker-demo
Docker demo containers.

- httpd
  - Expose port 80.
  - Apache2 sample include test cgi.
  - http://[Container Host IP]:[Specified Port]/ show apache default html
  - http://[Container Host IP]:[Specified Port]/cgi-bin/test.cgi show hello world by python

- library-search
  - Expose port 80.
  - Apache2 sample include demo web app.
  - demo app clone from https://github.com/abacl7/library-search.git
  - http://[Container Host IP]:[Specified Port]/ show app index.html
  - when build this container, please specify App Key. api key will inject to app code.
    - please take care about your api key. it will inject to python code.everyone can read it!
  - ex. #docker build --build-arg api_key=[your api key from https://calil.jp/doc/api.html ]
