---
title: Skype for Business Server でのドメインの準備によって行われた変更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。
ms.openlocfilehash: 46eaedb25ca245a5426314a8118be7443fb612e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831907"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Skype for Business Server でのドメインの準備によって行われた変更
 
次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。
  
**ドメイン ルートに追加された ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authenticated-Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|コンテナーの読み取り (継承されない)  <br/> |**○** <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|User-Account-Restrictions ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|Personal-Information ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|General-Information ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|Public-Information ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |
|RTCPropertySet ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|Proxy-Addresses ユーザー プロパティの書き込み  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |
|RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |
|RTCPropertySet ユーザー プロパティ セットの書き込み  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |
|すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |
   
次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。 特に注記のない限り、これらの ACE はすべて継承されます。
**組み込みコンテナーに追加された ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|コンテナーの読み取り (継承されない)  <br/> |**○** <br/> |**○** <br/> |
   

