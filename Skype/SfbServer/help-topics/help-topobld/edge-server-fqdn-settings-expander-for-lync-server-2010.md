---
title: Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '[外部設定] の下でプロパティを定義するには、次のものを構成します。'
ms.openlocfilehash: 505a4607029ccef38bb937cbb44891f9baaf3eb4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772233"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
 
[**外部設定**] の下でプロパティを定義するには、次のものを構成します。
  
Web 会議と音声ビデオに対して別々のプールの FQDN と IP アドレスを定義する場合は、[**Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化**] を選択します。
  
> [!NOTE]
> 個別の FQDN アドレスと IP アドレスのチェック ボックスをオンにしない場合は、エッジ サーバーが提供する 3 つのサービスごとに個別のポートを指定する必要があります。 構成する完全修飾ドメイン名は、Access Edge サービスに関連付けられている FQDN のみです。 
  
**A/V エッジ** サービスでネットワーク アドレス変換 (NAT) IP アドレスと構成を使用する場合は、[A/V エッジ サービスが NAT が有効] チェック ボックスをオンにします。
  
有効なエッジ サービスに対して、**プールの FQDN** とポートを [**ポート**] の下に入力します。
  
- **アクセス エッジ サービス** のプール FQDN とそのサービスを一意に識別するポートを定義します。
    
- **Web 会議エッジ サービス** のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。
    
- **音声ビデオ エッジ サービス** のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。
    
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

