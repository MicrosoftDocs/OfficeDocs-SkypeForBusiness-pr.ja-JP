---
title: Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: エッジサーバーコンピューターのプロパティを1つのエッジサーバーまたはエッジプールのメンバーコンピューターとして編集するには、サーバー名と IP アドレス構成設定を構成します。
ms.openlocfilehash: 411e870a874366754d17d0601ed1f216ce18899a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684780"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
 
エッジサーバーコンピューターのプロパティを1つのエッジサーバーまたはエッジプールのメンバーコンピューターとして編集するには、**サーバー名と IP アドレス構成**設定を構成します。
  
- [ **Internal name OR FQDN**]: ドメインネームシステム (DNS) で参照されているコンピューターの名前を入力します。 
    
- [**内部 IPv4 アドレス**]: このコンピューターの内部ネットワークインターフェイスカード (NIC) の IPv4 アドレスを入力します。
    
- このコンピューターに関連付けられている**アクセスエッジサービス**の**外部 IPv4 アドレス**を構成します
    
    > [!IMPORTANT]
    > エッジサーバー構成に単一の IP アドレスを使用するように選択した場合は、アクセスエッジサービスの外部 IPv4 アドレスのみを編集できます。 他のエッジサービスは、アクセスエッジサービスと同じ IPv4 アドレスを共有します。 
  
- 編集できる場合は、このコンピューターに関連付けられている**Web 会議サービス**の**外部 IPv4 アドレス**を構成します。
    
- 編集できる場合は、このコンピューターに関連付けられている**A/V Edge サービス**の**外部 IPv4 アドレス**を構成します。
    
- 編集できる場合は、このコンピューターに関連付けられている**NAT 対応パブリック IPv4 アドレス**を構成します。
    
    > [!IMPORTANT]
    > **Nat 対応パブリック IPv4 アドレス**の構成プロパティは、A/V Edge サービスのネットワークアドレス変換 (NAT) を提供するように選択した場合にのみ編集可能になります。
  
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

