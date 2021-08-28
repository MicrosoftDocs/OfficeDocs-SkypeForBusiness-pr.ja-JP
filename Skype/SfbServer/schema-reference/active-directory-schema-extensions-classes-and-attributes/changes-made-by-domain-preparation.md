---
title: ドメインの準備によって行われた変更は、Skype for Business Server
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
ms.localizationpriority: medium
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。
ms.openlocfilehash: af84828aac349f4b09627d96d3a84cc97ff49a79
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630391"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>ドメインの準備によって行われた変更は、Skype for Business Server
 
次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。
  
**ドメイン ルートに追加された ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**認証済みユーザー**|
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
   

