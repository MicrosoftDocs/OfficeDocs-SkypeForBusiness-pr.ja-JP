---
title: Lync Server 2010 用のフロントエンド仲介サービス設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: このダイアログで、仲介サーバー PSTN ゲートウェイ設定のプロパティを編集します。 次の設定を定義します。
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284390"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のフロントエンド仲介サービス設定の展開
 
このダイアログで、**仲介サーバー PSTN ゲートウェイ**設定のプロパティを編集します。 次の設定を定義します。
  
- このフロントエンドサーバーまたはフロントエンドプールで仲介サーバーを検索する場合は、[併置され**ている仲介サーバー** ] を選択します。
    
- **リスニングポート**: 仲介サーバーがリッスンするポートを定義します。 **TLS**またはトランスポート層のセキュリティ、 **TCP**、またはトランスポート制御プロトコルのポートを定義できます。 TCP 用のポートエントリを利用できるようにするには、[ **tcp ポートを有効**にする] チェックボックスをオンにする必要があります。 
    
    > [!IMPORTANT]
    > ポート値 TLS、TCP、またはその両方を有効にする必要があるかどうかを判断するには、公衆交換電話網 (PSTN) ゲートウェイのドキュメントと構成の設定を参照してください。 TLS はセキュリティで保護されたプロトコルであり、証明書を使って仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化します。 すべての PSTN ゲートウェイで TLS がサポートされるわけではありません。 
  
- 現在関連付けられている既存の [**トランク**] (セッション開始プロトコル (SIP) トランク)、[**ゲートウェイ**] (PSTN ゲートウェイまたは IP-PBX)、および [**サイト**] (トランクおよびゲートウェイの構成済みサイト) の一覧。
    
- トランク、ゲートウェイ、およびサイトを選択し、[**既定値にする**] をクリックして、選択したものをこの仲介サービス用の既定値に設定します。現在の既定値を選択し、[**既定値の解除**] をクリックして、現在の既定値として選択している設定を削除します。その後、新しい既定値を選択して、[**既定値にする**] をクリックします。
    
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

