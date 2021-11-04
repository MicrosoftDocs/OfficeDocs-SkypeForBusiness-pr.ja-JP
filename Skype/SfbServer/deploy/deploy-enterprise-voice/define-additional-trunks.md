---
title: トポロジ ビルダーで追加のトランクを定義Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '概要: 仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義する方法については、Skype for Business Server のトポロジ ビルダーで説明します。'
ms.openlocfilehash: a3a1094bdc9d0f92eba5cfa1ace87f14db0011de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748873"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>トポロジ ビルダーで追加のトランクを定義Skype for Business Server
 
**概要:** 仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義する方法については、Skype for Business Server のトポロジ ビルダーで説明します。
  
ピアを仲介サーバーに関連付ける追加のトランクを定義するには、次の手順に従います。 ピアは、公衆交換電話網 (PSTN) エンタープライズ VoIP接続を有効にしたユーザーを提供します。 ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。
  
トランクは、仲介サーバーとゲートウェイの間の論理的な接続です。
  
> [!NOTE]
> このトピックでは、「展開」のドキュメントの「Skype for Business Server のトポロジ ビルダーでゲートウェイを定義する」の説明に従って、少なくとも[1](define-a-gateway.md)つの接続またはスタンドアロンの仲介サーバーまたはプールを持つ PSTN ゲートウェイとルート トランクをセットアップする必要があります。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義するには

1. トポロジ ビルダーの開始: [**スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business Server **2015] をクリックし、[2015Topology** **Builder]** Skype for Business Serverクリックします。 
    
2. [Skype for Business Server] の下にあるサイト名 **の [共有** コンポーネント] で、[**トランク**] ノードを右クリックし、[新しいトランク]**をクリックします**。
   1. [**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。2 つのトランクに同じ名前を付けることはできません。
    
      > [!NOTE]
      > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスではなく FQDN を指定する必要があります。 
  
3. [**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。
    5. [PSTN **ゲートウェイの** リッスン ポート] で、ピア (PSTN ゲートウェイ、IP-PBX、または SBC) が仲介サーバーからこのトランクに関連付ける SIP メッセージを受信するリッスン ポートを入力します。 既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。 既定の存続可能ブランチ アプライアンス ポートは、TCP の場合は 5081、TLS の場合は 5082 です。
    
4. [**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。
    
    > [!NOTE]
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強く推奨します。 
  
5. [ **関連付けられた仲介サーバー]** で、このピアのルート トランクに関連付ける仲介サーバー プールを選択します。
    
6. [ **関連付けられた仲介サーバーのポート**] に、仲介サーバーがピアから SIP メッセージを受信するリッスン ポートを入力します。
    
    > [!NOTE]
    > 複数のトランクサポートがSkype for Business Server、異なるトランク名を持つ 2 つのトランクを、同じ関連する仲介サーバー ポートと IP/PSTN ゲートウェイのリッスン ポートで **構成することはできません。**
  
    > [!NOTE]
    > 複数のトランク サポートを使用Skype for Business Server複数の SIP シグナリング ポートを仲介サーバーで定義して、複数のピアとの通信を行います。 トランクを定義する場合、関連する仲介 **サーバー** のポート番号は、仲介サーバーが許可するそれぞれのプロトコルのリッスン ポートの範囲内にある必要があります。 このポート範囲は、サーバー プールSkype for Business Server仲介サーバー プールで定義されます。 関連する仲介サーバー プールを右クリックし、[プロパティの編集] **を選択します**。 [**リッスン ポート**] フィールドでポート範囲を指定します。
  
7. [**OK**] をクリックします。 
    

