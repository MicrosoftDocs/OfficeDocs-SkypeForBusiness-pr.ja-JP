---
title: Skype for Business Server の Topology Builder で追加の trunks を定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '概要: Skype for Business Server のトポロジビルダーで、仲介サーバーとゲートウェイピアの間に追加のトランクを定義する方法について説明します。'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303313"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Skype for Business Server の Topology Builder で追加の trunks を定義する
 
**概要:** Skype for Business Server のトポロジビルダーで、仲介サーバーとゲートウェイピアの間に追加のトランクを定義する方法について説明します。
  
次の手順に従って、ピアを仲介サーバーに関連付けることができる追加のトランクを定義します。 Peer は、公衆交換電話網 (PSTN) に接続して、エンタープライズ Voip を有効にします。 ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。
  
トランクは、仲介サーバーとゲートウェイの間の論理的な接続です。
  
> [!NOTE]
> このトピックでは、展開ドキュメントの「 [Skype For Business Server のトポロジビルダーでのゲートウェイの定義](define-a-gateway.md)」の説明に従って、少なくとも1つの併置またはスタンドアロンの仲介サーバーまたはプールで PSTN ゲートウェイとルートトランクをセットアップしていることを前提としています。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>仲介サーバーとゲートウェイピアの間に追加のトランクを定義するには

1. トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。
    
2. [Skype for Business Server] の [サイト名]、[**共有コンポーネント**] で、[ **Trunks** ] ノードを右クリックし、[**新しいトランク**] をクリックします。
   1. [**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。 2 つのトランクに同じ名前を付けることはできません。
    
      > [!NOTE]
      > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定した場合は、仲介サーバーのピアの IP アドレスではなく、FQDN を指定する必要があります。 
  
3. [**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。
    5. [ **Pstn ゲートウェイのリスニングポート**] で、ピア (pstn ゲートウェイ、IP PBX、または SBC) がこのトランクに関連付けられている仲介サーバーから SIP メッセージを受信するリッスンポートを入力します。 既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。 既定の Survivable Branch Appliance ポートは、TCP と5082の TLS 用の5081です。
    
4. [**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。
    
    > [!NOTE]
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。 
  
5. [**関連付けられた仲介サーバー**] で、このピアのルートトランクに関連付ける仲介サーバープールを選択します。
    
6. [**関連付けられた仲介サーバーのポート**] で、仲介サーバーがピアから SIP メッセージを受信するリスニングポートを入力します。
    
    > [!NOTE]
    > Skype for Business Server で複数のトランクがサポートされている場合、複数のトランク名を持つ2つの trunks を構成することはできません。**関連する仲介サーバーのポート**と**IP/PSTN ゲートウェイのリスニングポート**を設定することはできません。
  
    > [!NOTE]
    > Skype for Business Server で複数のトランクがサポートされていると、複数のピアと通信するために、複数の SIP シグナリングポートを仲介サーバーで定義できます。 トランクを定義する場合、**関連する仲介サーバーのポート**番号は、仲介サーバーで許可されている各プロトコルのリッスンポートの範囲内である必要があります。 このポート範囲は、Skype for Business Server および仲介サーバープールで定義されています。 関連する仲介サーバープールを右クリックし、[**プロパティの編集**] を選択します。 Specify the port range in the **Listening ports** field.
  
7. [**OK**] をクリックします。 
    

