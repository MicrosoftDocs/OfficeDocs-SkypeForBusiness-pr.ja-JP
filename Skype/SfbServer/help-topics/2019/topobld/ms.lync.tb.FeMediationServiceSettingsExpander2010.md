---
title: Lync Server 2010 のフロント エンド仲介サービスの設定の拡張
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: このダイアログ ボックスで、仲介サーバー PSTN ゲートウェイの設定のプロパティを編集するとします。 次の設定を定義します。
ms.openlocfilehash: 7343fb4e2876ffa23fa7d37a8669f9b0c25f428b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979772"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 のフロント エンド仲介サービスの設定の拡張
 
このダイアログ ボックスで **、仲介サーバー PSTN ゲートウェイ**の設定のプロパティを編集するとします。 次の設定を定義します。
  
- このフロント エンド サーバーまたはフロント エンド プールに仲介サーバーを連結する場合は、**仲介サーバーを 1 か所に配置を有効に**するを選択します。
    
- **リッスンするポート**: 仲介サーバーがリッスンするポートを定義します。 **TLS**またはトランスポート層セキュリティ、または**TCP**のポートを定義することができますまたはトランス ポート プロトコルを制御します。 使用する TCP のポートのエントリを**有効にする TCP ポート**のチェック ボックスを選択します。 
    
    > [!IMPORTANT]
    > TLS と TCP のどちらか一方または両方のポートの値を有効にして、定義する必要がある場合を判断するのには公衆交換電話網 (PSTN) ゲートウェイのドキュメントおよび構成の設定] を参照してください。 TLS は、仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化する証明書を使用して、安全なプロトコルです。 すべての PSTN ゲートウェイが TLS をサポートします。 
  
- 現在関連付けられている既存の [**トランク**] (セッション開始プロトコル (SIP) トランク)、[**ゲートウェイ**] (PSTN ゲートウェイまたは IP-PBX)、および [**サイト**] (トランクおよびゲートウェイの構成済みサイト) の一覧。
    
- トランク、ゲートウェイ、およびサイトを選択し、[**既定値にする**] をクリックして、選択したものをこの仲介サービス用の既定値に設定します。現在の既定値を選択し、[**既定値の解除**] をクリックして、現在の既定値として選択している設定を削除します。その後、新しい既定値を選択して、[**既定値にする**] をクリックします。
    
 [**OK**]: ダイアログでの変更を受け入れて確定します。
  
 [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
 [**ヘルプ**]: このヘルプ画面を表示します。
  

