---
title: ドメインの準備によって行われた変更は、Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 4bf190e0b74e082cf187cde94b3a3062906f0c53
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389919"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>ドメインの準備によって行われた変更は、Skype for Business Server
 
次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。
  
**ドメイン ルートに追加された ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**認証済みユーザー**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|コンテナーの読み取り (継承されない)  <br/> |**○** <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |不要  <br/> |
|User-Account-Restrictions ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |不要  <br/> |不要  <br/> |
|Personal-Information ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |不要  <br/> |不要  <br/> |
|General-Information ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |不要  <br/> |不要  <br/> |
|Public-Information ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |不要  <br/> |不要  <br/> |
|RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |不要  <br/> |**はい** <br/> |
|RTCPropertySet ユーザー プロパティ セットの読み取り  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |不要  <br/> |不要  <br/> |
|Proxy-Addresses ユーザー プロパティの書き込み  <br/> |不要  <br/> |不要  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |
|RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み  <br/> |不要  <br/> |不要  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |
|RTCPropertySet ユーザー プロパティ セットの書き込み  <br/> |不要  <br/> |不要  <br/> |**はい** <br/> |いいえ  <br/> |不要  <br/> |
|すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り  <br/> |不要  <br/> |不要  <br/> |不要  <br/> |**はい** <br/> |いいえ  <br/> |
   
次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。 特に注記のない限り、これらの ACE はすべて継承されます。
**組み込みコンテナーに追加された ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|コンテナーの読み取り (継承されない)  <br/> |**○** <br/> |**○** <br/> |
   

