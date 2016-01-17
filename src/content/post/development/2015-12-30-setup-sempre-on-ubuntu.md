+++
date = "2015-12-30T13:05:23+08:00"
draft = true
title = "Setup SEMPRE on ubuntu"

+++
git clone https://github.com/percyliang/sempre

cd sempre

./pull-dependencies core corenlp freebase

cd fig && ./tomcat && cd -

cd fig && make clean && make && cd -

ant core
