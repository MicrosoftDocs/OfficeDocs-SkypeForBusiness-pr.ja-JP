---
title: Skype for Business Server のトポロジビルダーでゲートウェイを定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '概要: Skype for Business Server のトポロジビルダーで PSTN ゲートウェイを定義する方法について説明します。'
ms.openlocfilehash: 322c526c87c3a354f11fd0c906256b36e6df526e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233219"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Skype for Business Server のトポロジビルダーでゲートウェイを定義する
 
**概要:** Skype for Business Server のトポロジビルダーで PSTN ゲートウェイを定義する方法について説明します。
  
次の手順に従って、トポロジビルダーを使用して、エンタープライズ Voip を有効にしているユーザー向けに、仲介サーバーを関連付け、PSTN (公衆交換電話網) への接続を提供できるピアを定義します。 仲介サーバーへのピアは、SIP トランクを構成することによって、接続先のインターネットテレフォニーサービスプロバイダー (ITSP) の PSTN ゲートウェイ、IP PBX、またはセッション境界コントローラー (SBC) にすることができます。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>仲介サーバーのピアを定義するには

1. トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。
    
2. [Skype for Business Server] の [サイト名]、[共有コンポーネント] の順にクリックし、[ **Pstn ゲートウェイ**] ノードを右クリックして、[**新しい pstn ゲートウェイ**] をクリックします。
3. [**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。
    
    > [!NOTE]
    > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定した場合は、仲介サーバーのピアの IP アドレスではなく、FQDN を指定する必要があります。 
  
4. 新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。

5. PSTN ゲートウェイのルート トランクを定義します。 トランクは、仲介サーバーと、組で一意に識別されたゲートウェイの間の論理的な接続です。
    
    {仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP と FQDN、ゲートウェイリッスンポート}
    
     - トポロジビルダーで PSTN ゲートウェイを定義する場合は、トポロジに PSTN ゲートウェイを正常に追加するためにルートトランクを定義する必要があります。
    
     - ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。
    
6. [ **IP/PSTN ゲートウェイのリスニングポート**] に、PSTN ゲートウェイのルートトランクと関連付けられる仲介サーバーからの SIP メッセージについて、ゲートウェイ、PBX、または SBC が使用するリスニングポートを入力します。 (既定では、ポートは、PSTN ゲートウェイ、PBX、または SBC 上のトランスポート層セキュリティ (TLS) 用の伝送制御プロトコル (TCP) および5067用の5066です。 ブランチサイトの Survivable Branch Appliance では、既定のポートは TCP 用の5081で、TLS の場合は5082です。)
    
7. [**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。
    
    > [!NOTE]
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。 
  
8. [**関連付けられた仲介サーバー**] で、この PSTN ゲートウェイのルートトランクに関連付ける仲介サーバープールを選択します。
    
9. [**関連付けられた仲介サーバーポート**] に、仲介サーバーがゲートウェイからの SIP メッセージに使用するリスニングポートを入力します。
    
    > [!NOTE]
    > Skype for Business Server で複数のトランクがサポートされている場合は、複数の PSTN ゲートウェイと通信するために、仲介サーバー上で複数の SIP シグナリングポートを定義できます。 トランクを定義する場合、**関連する仲介サーバーポート**は、仲介サーバーで許可されている各プロトコルのリスニングポートの範囲内にある必要があります。 このポート範囲は、「Skype for Business Server」と「仲介プール」で定義されています。 対象の仲介サーバープールを右クリックし、[**プロパティの編集**] を選択します。 Specify the port range in the **Listening ports** field.
  
10. 定義されたピアが実行中で、指定した FQDN または IP アドレスを使用していることを確認します。 次に、[**完了**] をクリックします。
    
11. [**Skype for Business Server**] ノードを右クリックし、[**トポロジの公開**] をクリックします。
    

