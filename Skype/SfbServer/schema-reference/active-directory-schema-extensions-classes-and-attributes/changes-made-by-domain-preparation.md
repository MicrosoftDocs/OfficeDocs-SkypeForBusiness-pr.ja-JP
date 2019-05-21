---
title: Skype for Business Server のドメイン準備によって行われた変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 次の表に、ドメインの準備でドメインルート上に作成されるアクセス制御エントリ (Ace) を示します。 特に注記がない限り、すべての Ace が継承されます。
ms.openlocfilehash: afd6747590e09b0b86b42119ad34eb26eaf9d8db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296715"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Skype for Business Server のドメイン準備によって行われた変更
 
次の表に、ドメインの準備でドメインルート上に作成されるアクセス制御エントリ (Ace) を示します。 特に注記がない限り、すべての Ace が継承されます。
  
**ドメインルートに追加された Ace**

|**AS**|**RTCUniversal-UserReadOnly-グループ**|**RTCUniversal-ServerReadOnly-グループ**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-サービス**|**認証済み-ユーザー**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|読み取りコンテナー (継承されません)  <br/> |**うん** <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー PropertySet の読み取りユーザーアカウントの制限  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー PropertySet の個人情報を読む  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー PropertySet の読み取りの概要-情報  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー PropertySet パブリック情報を読む  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー PropertySet RTCUserSearchProperty セットを読み取ります。  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |
|ユーザー PropertySet RTCPropertySet を読む  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザープロパティプロキシアドレスの書き込み  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |
|User PropertySet RTCUserSearchProperty セットの書き込み  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー PropertySet の書き込み RTCPropertySet  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |
|PropertySet の DS-レプリケーション-すべての Active Directory オブジェクトの変更内容を確認する  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |いいえ  <br/> |
   
次の表は、3つの組み込みコンテナー (ユーザー、コンピューター、ドメインコントローラー) で、ドメインの準備によって作成される Ace を示しています。 特に注記がない限り、すべての Ace が継承されます。
**組み込みのコンテナーに追加された Ace**

|**AS**|**RTCUniversal-UserReadOnly-グループ**|**RTCUniversal-ServerReadOnly-グループ**|
|:-----|:-----|:-----|
|読み取りコンテナー (継承されません)  <br/> |**うん** <br/> |**はい** <br/> |
   

