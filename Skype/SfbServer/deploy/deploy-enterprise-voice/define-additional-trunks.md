---
title: Skype for Business Server のトポロジ ビルダーで追加のトランクを定義する
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '概要: Skype for Business Server のトポロジ ビルダーで仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義する方法について説明します。'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836997"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Skype for Business Server のトポロジ ビルダーで追加のトランクを定義する
 
**概要:** Skype for Business Server のトポロジ ビルダーで、仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義する方法について説明します。
  
ピアを仲介サーバーに関連付ける追加のトランクを定義するには、次の手順を実行します。 ピアは、公衆交換電話網 (PSTNエンタープライズ VoIP接続できるユーザーを提供します。 ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。
  
トランクは、仲介サーバーとゲートウェイの間の論理接続です。
  
> [!NOTE]
> このトピックでは、「展開」のドキュメントの [「Skype for Business Server](define-a-gateway.md) のトポロジ ビルダーでゲートウェイを定義する」で説明するように、少なくとも 1 つの仲介サーバーまたはスタンドアロンの仲介サーバーまたはプールを使用して PSTN ゲートウェイとルート トランクをセットアップしている必要があります。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義するには

1. トポロジ ビルダーの起動: **[** スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 2015Topology Builder]** をクリックします。
    
2. [Skype for Business Server] の [サイト名] の **[共有** コンポーネント] で、[ **トランク** ] ノードを右クリックし、[新しいトランク] を **クリックします**。
   1. [**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。 2 つのトランクに同じ名前を付けることはできません。
    
      > [!NOTE]
      > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに FQDN を指定する必要があります。 
  
3. [**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。
    5. **[PSTN** ゲートウェイのリッスン ポート] で、ピア (PSTN ゲートウェイ、IP-PBX、または SBC) が、このトランクに関連付けられる仲介サーバーから SIP メッセージを受信するリッスン ポートを入力します。 既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。 既定の存続可能ブランチ アプライアンス ポートは、TCP の場合は 5081、TLS の場合は 5082 です。
    
4. [**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。
    
    > [!NOTE]
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強く推奨します。 
  
5. [ **関連付けられた仲介サーバー**] で、このピアのルート トランクに関連付ける仲介サーバー プールを選択します。
    
6. [ **関連付けられた仲介サーバーのポート**] で、仲介サーバーがピアから SIP メッセージを受信するリッスン ポートを入力します。
    
    > [!NOTE]
    > Skype for Business Server で複数のトランクがサポートされている場合、異なるトランク名を持つ 2 つのトランクを同じ関連付けられた仲介サーバー ポートと IP/PSTN ゲートウェイのリッスン ポートで **構成することはできません。**
  
    > [!NOTE]
    > Skype for Business Server での複数のトランクのサポートにより、仲介サーバーで複数の SIP 信号ポートを定義して、複数のピアと通信できます。 トランクを定義する場合、関連付けられた仲介 **サーバー** のポート番号は、仲介サーバーが許可するプロトコルのリッスン ポートの範囲内にある必要があります。 このポート範囲は、Skype for Business Server プールと仲介サーバー プールで定義されます。 関連する仲介サーバー プールを右クリックし、[プロパティの編集] **を選択します**。 [**リッスン ポート**] フィールドでポート範囲を指定します。
  
7. [**OK**] をクリックします。 
    

