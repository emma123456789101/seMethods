# seMethods
name: A workflow for my Hello World App
on: push

jobs:
  build:
    name: Hello world action
    runs-on: ubuntu-20.04
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Set up JDK 11
        uses: actions/setup-java@v2
        with:
          java-version: '11'
          distribution: 'adopt'
      - name: Compile with Maven
        run: mvn compile
      - name: Build Docker Image
        run: docker build -t semimage .
      - name: Run image
        run: docker run --name semcontainer -d semimage
      - name: view logs
        run: docker logs semcontainer
        
[![workflow](https://github.com/<emma123456789101>/<seMethods>/actions/workflows/main.yml/badge.svg)]

[![LICENSE](https://img.shields.io/github/license/<github-username>/sem.svg?style=flat-square)](https://github.com/<github-username>/sem/blob/master/LICENSE)
