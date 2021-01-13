---
title: Skype for Business Server のトポロジ ビルダーでゲートウェイを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '概要: Skype for Business Server のトポロジ ビルダーで PSTN ゲートウェイを定義する方法について説明します。'
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837027"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Skype for Business Server のトポロジ ビルダーでゲートウェイを定義する
 
**概要:** Skype for Business Server のトポロジ ビルダーで PSTN ゲートウェイを定義する方法について説明します。
  
トポロジ ビルダーを使用して、仲介サーバーを関連付け、エンタープライズ VoIP が有効なユーザーに公衆交換電話網 (PSTN) への接続を提供できるピアを定義するには、次の手順を実行します。 仲介サーバーへのピアは、SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) の PSTN ゲートウェイ、IP-PBX、またはセッション ボーダー コントローラー (SBC) です。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>仲介サーバーのピアを定義するには

1. トポロジ ビルダーを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 2015Topology Builder]** をクリックします。
    
2. [Skype for Business Server] の [サイト名] の [共有コンポーネント] で **、[PSTN** ゲートウェイ] ノードを右クリックし、[新しい PSTN ゲートウェイ] **をクリックします**。
3. [**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。
    
    > [!NOTE]
    > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに FQDN を指定する必要があります。 
  
4. 新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。

5. PSTN ゲートウェイのルート トランクを定義します。 トランクとは、仲介サーバーと、組によって一意に識別されるゲートウェイとの間の論理接続です。
    
    {仲介サーバーの FQDN、 仲介サーバーのリッスン ポート (TLS または TCP) : ゲートウェイ IP と FQDN、ゲートウェイ リッスン ポート}
    
     - トポロジ ビルダーで PSTN ゲートウェイを定義する場合は、PSTN ゲートウェイをトポロジに正常に追加するためのルート トランクを定義する必要があります。
    
     - ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。
    
6. **[IP/PSTN** ゲートウェイのリッスン ポート] で、PSTN ゲートウェイのルート トランクに関連付けられる仲介サーバーからの SIP メッセージにゲートウェイ、PBX、または SBC が使用するリッスン ポートを入力します。 (既定では、伝送制御プロトコル (TCP) のポートは 5066、PSTN ゲートウェイ、PBX、または SBC のトランスポート層セキュリティ (TLS) のポートは 5067 です。 ブランチ サイトの存続可能ブランチ アプライアンスの既定のポートは、TCP の場合は 5081、TLS の場合は 5082 です)。
    
7. [**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。
    
    > [!NOTE]
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強く推奨します。 
  
8. [ **関連付けられた仲介サーバー**] で、この PSTN ゲートウェイのルート トランクに関連付ける仲介サーバー プールを選択します。
    
9. [ **関連付けられた仲介サーバー] ポート** で、仲介サーバーがゲートウェイからの SIP メッセージに使用するリッスン ポートを入力します。
    
    > [!NOTE]
    > Skype for Business Server での複数トランクのサポートにより、仲介サーバー上で複数の PSTN ゲートウェイとの通信用に複数の SIP 信号ポートを定義できます。 トランクを定義する場合、関連付けられた仲介 **サーバー** ポートは、仲介サーバーが許可するプロトコルのリッスン ポートの範囲内に含む必要があります。 このポート範囲は、Skype for Business Server および仲介プールで定義されます。 目的の仲介サーバー プールを右クリックし、[プロパティの編集] **を選択します**。 [**リッスン ポート**] フィールドでポート範囲を指定します。
  
10. 定義したピアが実行中で、指定した FQDN または IP アドレスを使用している必要があります。 次に、[**完了**] をクリックします。
    
11. Skype for **Business Server ノードを右クリックし** 、[トポロジの公開] **をクリックします**。
    

