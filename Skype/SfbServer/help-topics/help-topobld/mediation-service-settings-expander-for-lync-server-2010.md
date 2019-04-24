---
title: Lync Server 2010 用の仲介サービス設定エキスパンダー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 次のプロパティを定義して、仲介サービスのプロパティを編集します。
ms.openlocfilehash: ea886bc22725103745f9bbb7c97dc6a41081e2ee
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200017"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用の仲介サービス設定エキスパンダー
 
次のプロパティを定義して、仲介サービスのプロパティを編集します。
  
- [**リッスン ポート**]: 仲介サービスがリッスンする **TLS** ポートを定義します。既定では、ポート値はトランスポート層セキュリティ (TLS) 経由の TCP 5067 です。
    
    必要に応じて、**TCP** ポート値を定義します。既定では、この値は TCP 5068 です。
    
    > [!NOTE]
    > TCP ポート値の設定を有効にするには、[**TCP ポートを有効にする**] を選択します。仲介サービスとの通信に必要なポート設定の要件については、公衆交換電話網 (PSTN) ゲートウェイまたはインターネット プロトコル構内交換機 (IP-PBX) のドキュメントを参照する必要があります。 
  
- [**TCP ポートを有効にする**] を選択して、PSTN ゲートウェイまたは IP-PBX からの TCP 通信のポート値を定義します。
    
- 現在関連付けられている既存の [**トランク**] (セッション開始プロトコル (SIP) トランク)、[**ゲートウェイ**] (PSTN ゲートウェイまたは IP-PBX)、および [**サイト**] (トランクおよびゲートウェイの構成済みサイト) の一覧。
    
- トランク、ゲートウェイ、およびサイトを選択し、[**既定値にする**] をクリックして、選択したものをこの仲介サービス用の既定値に設定します。現在の既定値を選択し、[**既定値の解除**] をクリックして、現在の既定値として選択している設定を削除します。その後、新しい既定値を選択して、[**既定値にする**] をクリックします。
    
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

