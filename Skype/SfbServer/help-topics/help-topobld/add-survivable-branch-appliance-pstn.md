---
title: 存続可能ブランチ アプライアンスの PSTN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: ブランチサイトで Survivable Branch Appliance の公衆交換電話網 (PSTN) ゲートウェイを定義するには、次のように指定します。
ms.openlocfilehash: 3a146a5bf9b879681b0d490a1d03198853c72305
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303667"
---
# <a name="add-survivable-branch-appliance-pstn"></a>存続可能ブランチ アプライアンスの PSTN の追加
 
ブランチサイトで Survivable Branch Appliance の公衆交換電話網 (PSTN) ゲートウェイを定義するには、次のように指定します。 
  
- 着信と発信の PSTN 通話をルーティングするために、Survivable Branch Appliance または Survivable Branch Server が関連付けられているゲートウェイピアの完全修飾ドメイン名 (FQDN) または IP アドレス。
    
    > [!IMPORTANT]
    > Survivable Branch Appliance を定義している場合、これは、Survivable Branch アプライアンス内の仲介サーバーが PSTN 接続用に接続するゲートウェイです。 
  
- セッション開始プロトコル (SIP) メッセージで使用するリッスン ポート。ゲートウェイ、構内交換機 (PBX)、またはセッション境界コントローラー (SBC) の場合、伝送制御プロトコル (TCP) の既定ポートは 5066、トランスポート層セキュリティ (TLS) の既定ポートは 5067 です。ブランチ サイトの存続可能ブランチ アプライアンスの場合、TCP の既定ポートは 5081、TLS の既定ポートは 5082 です。
    
- セキュリティ上の理由により、TLS を使用することを強くお勧めします。 Survivable Branch appliance を定義する場合は、Survivable Branch Appliance のベンダーのドキュメントを参照して、Survivable Branch Appliance が TLS プロトコルをサポートしていることを確認してください。
    
    > [!IMPORTANT]
    > セキュリティ上の理由により、TLS を使用可能なゲートウェイを展開することを強くお勧めします。 
  
> [!NOTE]
> PSTN ゲートウェイを追加する場合は後でセットアップできますが、PSTN ゲートウェイを定義して構成するまでは使用可能な機能が制限されます。 
  

