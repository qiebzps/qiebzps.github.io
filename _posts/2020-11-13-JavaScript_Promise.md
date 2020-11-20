---
layout: post
title:  "LinuxLinux"
date:   2020-11-13 22:08:00 +0800
tags:   Linux cron crontab
---

# Table of Contents

1.  [执行f1,f2,f3,输出f3,f2,f1](#org7744cf5)
2.  [期望输出f1,f2,f3,改写三个函数](#org979d146)
3.  [用Promise对象改写三个函数](#org384164c)



<a id="org7744cf5"></a>

# 执行f1,f2,f3,输出f3,f2,f1

    f1();
    f2();
    f3();
    
    function f1(){
        setTimeout(() => {
            console.log("f1");
        }, 1500);
    }
    function f2(){
        setTimeout(() => {
            console.log("f2");
        }, 1000);
    }
    function f3(){
        setTimeout(() => {
            console.log("f3");
        }, 500);
    }


<a id="org979d146"></a>

# 期望输出f1,f2,f3,改写三个函数

    f1();
    // f2();
    // f3();
    
    function f1(){
        setTimeout(() => {
            console.log("f1");
            f2();
        }, 1500);
    }
    function f2(){
        setTimeout(() => {
            console.log("f2");
            f3();
        }, 1000);
    }
    function f3(){
        setTimeout(() => {
            console.log("f3");
        }, 500);
    }


<a id="org384164c"></a>

# 用Promise对象改写三个函数

    var promiseF1 = new Promise(function(resolve,reject){
        setTimeout(() => {
            console.log("f1");
            resolve(true);
        }, 1500);
    });
    
    
    promiseF1
    .then(function(value){
        return new Promise(function(resolve,reject){
            setTimeout(() => {
                console.log("f2");
                resolve(true);
            }, 1000);
        })
    })
    .then(function(value){
            setTimeout(() => {
                console.log("f3");
            }, 500);
    })

怎么没看出来Promise对象好用在哪?
反而代码写的更多了?咋回事,如果你知道请告诉我,多谢!

