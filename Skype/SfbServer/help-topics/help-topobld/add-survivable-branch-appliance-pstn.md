---
title: 存続可能ブランチ アプライアンスの PSTN の追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: ブランチ サイトでのリカバリ性に優れたブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次のように指定します。
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a>存続可能ブランチ アプライアンスの PSTN の追加
 
ブランチ サイトでのリカバリ性に優れたブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次のように指定します。 
  
- リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーが受信と送信のルーティングのために関連付けられているゲートウェイ ピアの IP アドレス、完全修飾ドメイン名 (FQDN) PSTN を呼び出します。
    
    > [!IMPORTANT]
    > リカバリ性に優れたブランチ アプライアンスを定義している場合は、リカバリ性に優れたブランチ アプライアンス内部の仲介サーバーの PSTN への接続の接続先のゲートウェイです。 
  
- セッション開始プロトコル (SIP) メッセージで使用するリッスン ポート。ゲートウェイ、構内交換機 (PBX)、またはセッション境界コントローラー (SBC) の場合、伝送制御プロトコル (TCP) の既定ポートは 5066、トランスポート層セキュリティ (TLS) の既定ポートは 5067 です。ブランチ サイトの存続可能ブランチ アプライアンスの場合、TCP の既定ポートは 5081、TLS の既定ポートは 5082 です。
    
- セキュリティ上の理由により、TLS を使用することを強くお勧めします。 リカバリ性に優れたブランチ アプライアンスを定義する場合は、リカバリ性に優れた、ブランチ アプライアンスが TLS プロトコルをサポートしていることを確認するのには、リカバリ性に優れたブランチ アプライアンスのベンダーのマニュアルを参照してください。
    
    > [!IMPORTANT]
    > セキュリティ上の理由により、TLS を使用可能なゲートウェイを展開することを強くお勧めします。 
  
> [!NOTE]
> PSTN ゲートウェイを追加する場合は後でセットアップできますが、PSTN ゲートウェイを定義して構成するまでは使用可能な機能が制限されます。 
  

