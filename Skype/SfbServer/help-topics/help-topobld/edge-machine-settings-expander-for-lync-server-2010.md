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
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: エッジサーバーコンピューターのプロパティを1つのエッジサーバーとして、またはエッジプールのメンバーコンピューターとして編集するには、サーバー名と IP アドレスの構成設定を構成します。
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218928"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
 
エッジサーバーコンピューターのプロパティを1つのエッジサーバーとして、またはエッジプールのメンバーコンピューターとして編集するには、 **サーバー名と IP アドレスの構成** 設定を構成します。
  
- [**内部名または FQDN**]: ドメインネームシステム (DNS) で参照されているコンピューターの名前を入力します。 
    
- [**内部 IPv4 アドレス**]: このコンピューターの内部ネットワークインターフェイスカード (NIC) の ipv4 アドレスを入力します。
    
- このコンピューターに関連付けられている **アクセスエッジサービス**の **外部 IPv4 アドレス** を構成します。
    
    > [!IMPORTANT]
    > エッジサーバー構成に単一の IP アドレスを使用することを選択した場合は、アクセスエッジサービスの外部 IPv4 アドレスのみを編集できます。 他のエッジサービスは、アクセスエッジサービスと同じ IPv4 アドレスを共有します。 
  
- 編集できる場合は、このコンピューターに関連付けられている **Web 会議サービス**の **外部 IPv4 アドレス** を構成します。
    
- 編集可能な場合は、このコンピューターに関連付けられている **音声ビデオエッジサービス**の **外部 IPv4 アドレス** を構成します。
    
- 編集できる場合は、このコンピューターに関連付けられている **NAT が有効なパブリック IPv4 アドレス** を構成します。
    
    > [!IMPORTANT]
    > 音声ビデオエッジサービスにネットワークアドレス変換 (NAT) を提供することを選択した場合にのみ、 **nat が有効なパブリック IPv4 アドレス** の構成プロパティが編集可能になります。
  
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

