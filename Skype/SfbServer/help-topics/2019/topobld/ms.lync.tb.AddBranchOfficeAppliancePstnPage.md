---
title: 存続可能ブランチ アプライアンスの PSTN を追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: ブランチ サイトでの存続可能ブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次の情報を指定します。
ms.openlocfilehash: cadb307c0b1081e27e319c404bac94c16ad53262
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595911"
---
# <a name="add-survivable-branch-appliance-pstn"></a>存続可能ブランチ アプライアンスの PSTN の追加
 
ブランチ サイトでの存続可能ブランチ アプライアンスの公衆交換電話網 (PSTN) ゲートウェイを定義するには、次の情報を指定します。 
  
- 着信と発信の PSTN 通話のルーティングで、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーが関連付けられているゲートウェイ ピアの完全修飾ドメイン名 (FQDN) または IP アドレス。
    
    > [!IMPORTANT]
    > 存続可能ブランチ アプライアンスを定義すると、このアプライアンスは、PSTN 接続で存続可能ブランチ アプライアンス内部の仲介サーバーが接続するゲートウェイとなります。 
  
- セッション開始プロトコル (SIP) メッセージで使用するリッスン ポート。ゲートウェイ、構内交換機 (PBX)、またはセッション境界コントローラー (SBC) の場合、伝送制御プロトコル (TCP) の既定ポートは 5066、トランスポート層セキュリティ (TLS) の既定ポートは 5067 です。ブランチ サイトの存続可能ブランチ アプライアンスの場合、TCP の既定ポートは 5081、TLS の既定ポートは 5082 です。
    
- セキュリティ上の理由により、TLS を使用することを強くお勧めします。存続可能ブランチ アプライアンスを定義する場合は、存続可能ブランチ アプライアンスのベンダー ドキュメントを参照して、その存続可能ブランチ アプライアンスが TLS プロトコルをサポートすることを確認してください。
    
    > [!IMPORTANT]
    > セキュリティ上の理由により、TLS を使用可能なゲートウェイを展開することを強くお勧めします。 
  
> [!NOTE]
> PSTN ゲートウェイを追加する場合は後でセットアップできますが、PSTN ゲートウェイを定義して構成するまでは使用可能な機能が制限されます。 
  

