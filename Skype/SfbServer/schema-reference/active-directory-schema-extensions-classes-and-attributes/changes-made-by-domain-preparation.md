---
title: Skype のビジネス サーバー用のドメインの準備によって加えられた変更
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 次の表では、ドメインの準備は、ドメイン ルートを作成するアクセス制御エントリ (Ace) を一覧します。 特に断らない限り、すべての Ace が継承されます。
ms.openlocfilehash: 5cf239e37badafee9980140d08fd20a11e3c233d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877700"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Skype のビジネス サーバー用のドメインの準備によって加えられた変更
 
次の表では、ドメインの準備は、ドメイン ルートを作成するアクセス制御エントリ (Ace) を一覧します。 特に断らない限り、すべての Ace が継承されます。
  
**ドメイン ルートに追加された Ace**

|**ACE**|**RTCUniversal ・ UserReadOnly グループ**|**RTCUniversal ・ ServerReadOnly グループ**|**RTCUniversal UserAdmins**|**RTCHSUniversal サービス**|**Authenticated Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|(継承なし) コンテナーを読み取り  <br/> |**はい** <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー プロパティ設定のユーザー アカウント制限の読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|読み取りユーザー プロパティ設定の個人情報  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー プロパティ設定の一般的な情報の読み取り  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー プロパティ設定の公開情報を読む  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー プロパティ設定の RTCUserSearchProperty のセットを読み取る  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |**はい** <br/> |
|ユーザーのプロパティ設定の RTCPropertySet を読む  <br/> |**はい** <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー プロパティのプロキシ アドレスを作成します。  <br/> |いいえ  <br/> |いいえ  <br/> |**あり** <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザー プロパティ設定の RTCUserSearchProperty のセットを記述します。  <br/> |いいえ  <br/> |いいえ  <br/> |**あり** <br/> |いいえ  <br/> |いいえ  <br/> |
|ユーザーのプロパティ設定の RTCPropertySet を作成します。  <br/> |いいえ  <br/> |いいえ  <br/> |**あり** <br/> |いいえ  <br/> |いいえ  <br/> |
|読み取りプロパティ設定 DS のレプリケーション-取得の変更すべての Active Directory オブジェクトの  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |**あり** <br/> |いいえ  <br/> |
   
次の表に、ドメインの準備が次の 3 つの組み込みコンテナーに作成される Ace: ユーザー、コンピューター、およびドメイン コント ローラーです。 特に断らない限り、すべての Ace が継承されます。
**組み込みコンテナーに追加される Ace**

|**ACE**|**RTCUniversal ・ UserReadOnly グループ**|**RTCUniversal ・ ServerReadOnly グループ**|
|:-----|:-----|:-----|
|(継承なし) コンテナーを読み取り  <br/> |**はい** <br/> |**はい** <br/> |
   

