---
title: 'サンプル XSD ファイル: リレーションシップ |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60126510-b7dd-4cb4-92d3-9883590b92f2
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 304cc9d25f99071e13fd8cae104b09a0836a3224
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47534542"
---
# <a name="sample-xsd-file-relationships"></a>サンプル XSD ファイル: リレーションシップ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[サンプル XSD ファイル: リレーションシップ](https://docs.microsoft.com/visualstudio/xml-tools/sample-xsd-file-relationships)します。  
  
  
次の XSD ファイルは、XSD スキーマ デザイナーのドキュメントのさまざまな例で使用されます。 このファイルは、注釈とドキュメントを含む購買発注書のスキーマです。  
  
```xml  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
  <xs:element name="pet" type="PetType"/>  
  
  <xs:attributeGroup name="NameAgeAttributes">  
    <xs:attribute name="age" type="xs:integer" use="required"/>  
    <xs:attribute name="name" type="xs:string" use="required"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="PetType">  
    <xs:attributeGroup ref="NameAgeAttributes"/>  
  </xs:complexType>  
  
  <xs:element name="cat" substitutionGroup="pet">  
    <xs:complexType>  
      <xs:complexContent>  
        <xs:extension base="PetType">  
          <xs:sequence>  
            <xs:element name="weight" type="xs:integer"/>  
            <xs:element name="color" type="xs:string"/>  
            <xs:element name="breed" type="xs:integer"/>  
          </xs:sequence>  
        </xs:extension>  
      </xs:complexContent>  
    </xs:complexType>  
  </xs:element>  
  
  <xs:element name="dog" substitutionGroup="pet">  
    <xs:complexType>  
      <xs:complexContent>  
        <xs:extension base="PetType">  
          <xs:sequence>  
            <xs:element name="weight" type="xs:integer"/>  
            <xs:element name="color" type="xs:string"/>  
            <xs:element name="breed" type="xs:integer"/>  
          </xs:sequence>  
        </xs:extension>  
      </xs:complexContent>  
    </xs:complexType>  
  </xs:element>  
  
</xs:schema>  
```



