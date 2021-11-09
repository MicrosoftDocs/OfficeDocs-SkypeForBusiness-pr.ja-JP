---
title: '[トポロジ ビルダー] でゲートウェイを定義Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '概要: トポロジ ビルダーで PSTN ゲートウェイを定義する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 2e8a69fb1a884597f4e6ecde1a3811a88982d13e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857954"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>[トポロジ ビルダー] でゲートウェイを定義Skype for Business Server
 
**概要:** トポロジ ビルダーで PSTN ゲートウェイを定義する方法については、Skype for Business Server。
  
以下の手順に従って、トポロジ ビルダーを使用して、仲介サーバーを関連付けるピアを定義して、エンタープライズ VoIP で有効になっているユーザーに公衆交換電話網 (PSTN) への接続を提供します。 仲介サーバーへのピアには、SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) の PSTN ゲートウェイ、IP-PBX、またはセッション ボーダー コントローラー (SBC) を指定できます。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>仲介サーバーのピアを定義するには

1. トポロジ ビルダーの開始: [**スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business Server **2015] をクリックし、[2015Topology** **Builder]** Skype for Business Serverクリックします。 
    
2. [Skype for Business Serverサイト名、共有コンポーネント **、PSTN** ゲートウェイ ノードを右クリックし、[新しい PSTN ゲートウェイ]**をクリックします**。
3. [**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。
    
    > [!NOTE]
    > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスではなく FQDN を指定する必要があります。 
  
4. 新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。

5. PSTN ゲートウェイのルート トランクを定義します。 トランクは、仲介サーバーとタプルによって一意に識別されるゲートウェイとの間の論理的な接続です。
    
    {仲介サーバー FQDN, 仲介サーバーリスニング ポート (TLS または TCP) : ゲートウェイ IP と FQDN, ゲートウェイ リスニング ポート}
    
     - トポロジ ビルダーで PSTN ゲートウェイを定義する場合、PSTN ゲートウェイをトポロジに正常に追加するには、ルート トランクを定義する必要があります。
    
     - ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。
    
6. **[IP/PSTN** ゲートウェイのリッスン ポート] で、PSTN ゲートウェイのルート トランクに関連付けられる仲介サーバーからの SIP メッセージにゲートウェイ、PBX、または SBC が使用するリッスン ポートを入力します。 (既定では、ポートは、PSTN ゲートウェイ、PBX、または SBC の伝送制御プロトコル (TCP) の場合は 5066、トランスポート層セキュリティ (TLS) の場合は 5067 です。 ブランチ サイトの存続可能ブランチ アプライアンスでは、既定のポートは TCP の場合は 5081、TLS の場合は 5082 です)。
    
7. [**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。
    
    > [!NOTE]
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強く推奨します。 
  
8. [ **関連付けられた仲介サーバー]** で、この PSTN ゲートウェイのルート トランクに関連付ける仲介サーバー プールを選択します。
    
9. [ **関連付けられた仲介サーバーのポート**] に、仲介サーバーがゲートウェイからの SIP メッセージに使用するリッスン ポートを入力します。
    
    > [!NOTE]
    > 複数のトランク サポートがSkype for Business Server PSTN ゲートウェイとの通信のために仲介サーバーで複数の SIP シグナリング ポートを定義できます。 トランクを定義する場合、関連する仲介 **サーバー** ポートは、仲介サーバーによって許可されるそれぞれのプロトコルのリッスン ポートの範囲内にある必要があります。 このポート範囲は、[仲介プール] Skype for Business Serverで定義されます。 目的の仲介サーバー プールを右クリックし、[プロパティの編集] **を選択します**。 [**リッスン ポート**] フィールドでポート範囲を指定します。
  
10. 定義したピアが実行され、指定した FQDN または IP アドレスを使用している必要があります。 次に、[**完了**] をクリックします。
    
11. [トポロジ] ノードを **Skype for Business Server** し、[トポロジの公開]**をクリックします**。
    

