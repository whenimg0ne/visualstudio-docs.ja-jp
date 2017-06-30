---
title: "subarray メソッド (Int32Array) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: deed3bd4-63cb-4ec8-b5d1-ce9ce4a38f54
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# subarray メソッド (Int32Array)
サブ配列の最初と最後のメンバーを指定して、この配列の [ArrayBuffer オブジェクト](../../javascript/reference/arraybuffer-object.md) ストアの新しい Int32Array ビューを取得します。  
  
## 構文  
  
```javascript  
var newInt32Array = int32Array.subarray(begin, end);  
```  
  
## パラメーター  
 `newInt32Array`  
 このメソッドで返されるサブ配列。  
  
 `begin`  
 配列の先頭のインデックス。  
  
 `end`  
 配列の末尾のインデックス。  これは、内包的ではありません。  
  
## 解説  
 `begin` または `end` が負の場合は、配列の先頭からではなく配列の末尾からのインデックスを参照します。  `end` が指定されていない場合、サブ配列には、型指定された配列の `begin` から末尾までのすべての要素が含まれます。  `begin` 値および `end` 値で指定された範囲は、現在の配列の有効なインデックスの範囲に固定されます。  新しい型指定された配列の計算された長さが負の場合は、ゼロに固定されます。  返される配列は、このメソッドが呼び出される配列と同じ型になります。  
  
## 使用例  
 次の例は、配列の先頭の要素から開始して、長さが要素 2 つ分のサブ配列を取得する方法を示しています。  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var intArr = new Int32Array(buffer.byteLength / 4);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## 必要条件  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]