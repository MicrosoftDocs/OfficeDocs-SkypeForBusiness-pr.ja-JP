---
title: Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 単一のエッジ サーバーまたはエッジ プール内のメンバー コンピューターとは、エッジ サーバーのコンピューターのプロパティを編集するには、サーバー名と IP アドレスの構成の設定を構成します。
ms.openlocfilehash: f0125ba8d9c7ff181aff0a29f69a5077b1ad0818
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891541"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
 
単一のエッジ サーバーまたはエッジ プール内のメンバー コンピューターとは、エッジ サーバーのコンピューターのプロパティを編集するには、**サーバー名と IP アドレスの構成**の設定を構成します。
  
- **内部名または FQDN**: ドメイン ネーム システム (DNS) で参照されているコンピューターの名前を入力します。 
    
- **内部の IPv4 アドレス**: このコンピューターの内部ネットワーク インターフェイス カード (NIC) の IPv4 アドレスを入力します。
    
- このコンピューターに関連付けられている**アクセス エッジ サービス**の**外部 IPv4 アドレス**を構成します。
    
    > [!IMPORTANT]
    > エッジ サーバーの構成の 1 つの IP アドレスを使用することを選択した場合は、アクセス エッジ サービスの外部 IPv4 アドレスを編集することは必ず。 他のエッジ サービスは、アクセス エッジ サービスと同じ IPv4 アドレスを共有します。 
  
- このコンピューターに関連付けられている**Web 会議サービス**の**外部 IPv4 アドレス**を構成する場合は編集するのには、
    
- かどうかは編集に使用可能な構成する、 **A/V エッジ サービス****外部 IPv4 アドレス**がこのコンピューターに関連付けられています。
    
- 編集可能であれば、このコンピューターに関連付けられている**パブリック IPv4 アドレスの NAT が有効な**を構成します。
    
    > [!IMPORTANT]
    > **NAT が有効なパブリックな IPv4 アドレス**の構成のプロパティのみを使用できます、A のネットワーク アドレス変換 (NAT) を提供するよう選択した場合は、編集すると音声ビデオ エッジ サービス
  
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

