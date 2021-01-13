---
title: Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '[外部設定] の下でプロパティを定義するには、次のものを構成します。'
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807097"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
 
[**外部設定**] の下でプロパティを定義するには、次のものを構成します。
  
Web 会議と音声ビデオに対して別々のプールの FQDN と IP アドレスを定義する場合は、[**Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化**] を選択します。
  
> [!NOTE]
> 別々の FQDN と IP アドレスのチェック ボックスをオンにしない場合は、エッジ サーバーによって提供される 3 つのサービスごとに個別のポートを指定する必要があります。 構成する完全修飾ドメイン名は、アクセス エッジ サービスに関連付けられている FQDN のみです。 
  
ネットワーク アドレス **変換** (NAT) IP アドレスと構成を使用する場合は、A/V エッジ サービスで NAT が有効なチェック ボックスをオンにします。
  
有効なエッジ サービスに対して、**プールの FQDN** とポートを [**ポート**] の下に入力します。
  
- **アクセス エッジ サービス** のプール FQDN とそのサービスを一意に識別するポートを定義します。
    
- **Web 会議エッジ サービス** のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。
    
- **音声ビデオ エッジ サービス** のプール FQDN ([Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化] を選択していない場合) とそのサービスを一意に識別するポートを定義します。
    
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

