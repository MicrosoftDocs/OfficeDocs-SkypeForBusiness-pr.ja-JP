---
title: Lync Server 2010 用のフロントエンド仲介サービス設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: このダイアログでは、[仲介サーバーの PSTN ゲートウェイ] 設定のプロパティを編集します。次の設定を定義します。
ms.openlocfilehash: a4220a9134917ded867b639bb019594be5e21b9191e636503ae8883a5be39d77
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344816"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のフロント エンド仲介サービス設定mエキスパンダー
 
このダイアログでは、[**仲介サーバーの PSTN ゲートウェイ**] 設定のプロパティを編集します。次の設定を定義します。
  
- 仲介サーバー **をこの** フロント エンド サーバーまたはフロント エンド プールと照合する場合は、有効になっている仲介サーバーを選択します。
    
- **リッスン ポート**: 仲介サーバーがリッスンするポートを定義します。 **TLS** (トランスポート層セキュリティ) または **TCP** (伝送制御プロトコル) 用のポートを定義できます。 TCP 用のポート エントリを利用できるようにするには、[**TCP ポートを有効にする**] チェック ボックスをオンにする必要があります。 
    
    > [!IMPORTANT]
    > ご使用の公衆交換電話網 (PSTN) ゲートウェイのドキュメントおよび構成設定を参照し、ポート値 TLS、TCP、またはその両方の有効化および定義が必要かどうかを判断します。 TLS は、仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化するために証明書を使用して、より安全なプロトコルです。 すべての PSTN ゲートウェイが TLS をサポートするわけではありません。 
  
- 現在関連付けられている既存の [**トランク**] (セッション開始プロトコル (SIP) トランク)、[**ゲートウェイ**] (PSTN ゲートウェイまたは IP-PBX)、および [**サイト**] (トランクおよびゲートウェイの構成済みサイト) の一覧。
    
- トランク、ゲートウェイ、およびサイトを選択し、[**既定値にする**] をクリックして、選択したものをこの仲介サービス用の既定値に設定します。現在の既定値を選択し、[**既定値の解除**] をクリックして、現在の既定値として選択している設定を削除します。その後、新しい既定値を選択して、[**既定値にする**] をクリックします。
    
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

