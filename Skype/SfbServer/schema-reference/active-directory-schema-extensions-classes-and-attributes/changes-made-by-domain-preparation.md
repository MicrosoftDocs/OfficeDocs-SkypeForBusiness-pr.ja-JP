---
title: Skype のビジネス サーバー用のドメインの準備によって加えられた変更
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
ms.openlocfilehash: 3602e04082dbf4af9a2ab40fc3318761ebc08c21
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Skype のビジネス サーバー用のドメインの準備によって加えられた変更
 
次の表では、ドメインの準備は、ドメイン ルートを作成するアクセス制御エントリ (Ace) を一覧します。 特に断らない限り、すべての Ace が継承されます。
  
**ドメイン ルートに追加された Ace**

|**ACE**|**RTCUniversal ・ UserReadOnly グループ**|**RTCUniversal ・ ServerReadOnly グループ**|**RTCUniversal UserAdmins**|**RTCHSUniversal サービス**|**Authenticated Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|(継承なし) コンテナーを読み取り  <br/> |**うん** <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |なし  <br/> |
|ユーザー プロパティ設定のユーザー アカウント制限の読み取り  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |なし  <br/> |なし  <br/> |
|読み取りユーザー プロパティ設定の個人情報  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |なし  <br/> |なし  <br/> |
|ユーザー プロパティ設定の一般的な情報の読み取り  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |なし  <br/> |なし  <br/> |
|ユーザー プロパティ設定の公開情報を読む  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |なし  <br/> |なし  <br/> |
|ユーザー プロパティ設定の RTCUserSearchProperty のセットを読み取る  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |なし  <br/> |**うん** <br/> |
|ユーザーのプロパティ設定の RTCPropertySet を読む  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |なし  <br/> |なし  <br/> |
|ユーザー プロパティのプロキシ アドレスを作成します。  <br/> |なし  <br/> |なし  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |
|ユーザー プロパティ設定の RTCUserSearchProperty のセットを記述します。  <br/> |なし  <br/> |なし  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |
|ユーザーのプロパティ設定の RTCPropertySet を作成します。  <br/> |なし  <br/> |なし  <br/> |**うん** <br/> |なし  <br/> |なし  <br/> |
|読み取りプロパティ設定 DS のレプリケーション-取得の変更すべての Active Directory オブジェクトの  <br/> |なし  <br/> |なし  <br/> |なし  <br/> |**うん** <br/> |なし  <br/> |
   
次の表に、ドメインの準備が次の 3 つの組み込みコンテナーに作成される Ace: ユーザー、コンピューター、およびドメイン コント ローラーです。 特に断らない限り、すべての Ace が継承されます。
**組み込みコンテナーに追加される Ace**

|**ACE**|**RTCUniversal ・ UserReadOnly グループ**|**RTCUniversal ・ ServerReadOnly グループ**|
|:-----|:-----|:-----|
|(継承なし) コンテナーを読み取り  <br/> |**うん** <br/> |**うん** <br/> |
   

