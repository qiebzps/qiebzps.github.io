---
layout: post
title:  "JavaScript Promise"
date:   2020-11-13 19:49:00 +0800
tags:   JavaScript Promise
---

# Table of Contents

1.  [ִ��f1,f2,f3,���f3,f2,f1](#org7744cf5)
2.  [�������f1,f2,f3,��д��������](#org979d146)
3.  [��Promise�����д��������](#org384164c)



<a id="org7744cf5"></a>

# ִ��f1,f2,f3,���f3,f2,f1

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

# �������f1,f2,f3,��д��������

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

# ��Promise�����д��������

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

��ôû������Promise�����������?
��������д�ĸ�����?զ����,�����֪���������,��л!

