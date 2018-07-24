---
title: Lync Server 2010 エッジ サーバー FQDN 設定の展開
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '[外部設定] でプロパティを定義するには、次のように構成します。'
ms.openlocfilehash: 27bc29afd26ac280eaeb7469af530862c94b03a6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20999731"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 エッジ サーバー FQDN 設定の展開
 
[**外部設定**] でプロパティを定義するには、次のように構成します。
  
選択、**を有効にする別の FQDN と IP アドレスの web 会議および A/V** web 会議、オーディオとビデオのアドレスを個別のプールの FQDN と IP を定義したい場合はチェック ボックスです。
  
> [!NOTE]
> 別の FQDN と IP アドレスのチェック ボックスをオンにする場合は、エッジ サーバーによって提供される 3 つのサービスごとに個別のポートを入力します。 設定する必要がある唯一の完全修飾ドメイン名は、アクセス エッジ サービスに関連付けられた FQDN です。 
  
選択、 **A/V エッジ サービスは、NAT が有効な**チェック ボックスをオンする場合は、A/ネットワークを使用する音声ビデオ エッジ サービスはアドレス変換 (NAT) IP アドレスと構成。
  
**プールの FQDN**および**ポート**] の下のポートを入力する有効なエッジ サービスは、
  
- **アクセス エッジ サービス**のプールの FQDN と、サービスを一意に識別するポートを定義します。
    
- **Web 会議エッジ サービス**プールの FQDN を定義する (web 会議および A の FQDN と IP アドレスを分割する場合に有効にする V が選択されていないと) と、サービスを一意に識別するポート。
    
- 定義、 **A/音声ビデオ エッジ サービス**プールの FQDN (web 会議および A の FQDN と IP アドレスを分割する場合に有効にする V が選択されていないと) と、サービスを一意に識別するポート。
    
 [**OK**]: ダイアログでの変更を受け入れて確定します。
  
 [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
 [**ヘルプ**]: このヘルプ画面を表示します。
  

