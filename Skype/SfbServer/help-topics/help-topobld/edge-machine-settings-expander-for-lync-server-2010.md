---
title: Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: エッジ サーバー コンピューターのプロパティを単一のエッジ サーバーまたはエッジ プールのメンバー コンピューターとして編集するには、サーバー名と IP アドレス構成設定を構成します。
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807137"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
 
エッジ サーバー コンピューターのプロパティを単一のエッジ サーバーまたはエッジ プールのメンバー コンピューターとして編集するには、サーバー名と IP アドレス構成設定 **を構成** します。
  
- **内部名または FQDN**: ドメイン ネーム システム (DNS) で参照されているコンピューターの名前を入力します。 
    
- **内部 IPv4 アドレス**: このコンピューターの内部ネットワーク インターフェイス カード (NIC) の IPv4 アドレスを入力します。
    
- このコンピューターに関連 **付けられているアクセス エッジ サービス** の外部 **IPv4** アドレスを構成する
    
    > [!IMPORTANT]
    > エッジ サーバー構成に単一の IP アドレスを使用する場合は、アクセス エッジ サービスの外部 IPv4 アドレスのみを編集できます。 他のエッジ サービスは、アクセス エッジ サービスと同じ IPv4 アドレスを共有します。 
  
- 編集可能な場合は、このコンピューターに関連付けられている **Web 会議** サービスの外部 **IPv4** アドレスを構成します。
    
- 編集可能な場合は、このコンピューターに関連付けられている外部 **IPv4** アドレスを **A/V** エッジ サービスで構成します。
    
- 編集可能な場合は、このコンピューターに関連付けられている NAT 対応パブリック **IPv4 アドレス** を構成します。
    
    > [!IMPORTANT]
    > NAT が有効なパブリック **IPv4** アドレスの構成プロパティは、A/V エッジ サービスにネットワーク アドレス変換 (NAT) を提供することを選択した場合にのみ編集できます。
  
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

