---
title: "Skype 会議メディアのネットワークをセットアップします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: "For Business Online できるようにするには、スケジュール、作成、ブロードキャスト会議またはイベントをオンライン参加者に向けた最高 10,000 人の Skype の Skype 会議メディアの機能について説明します。"
ms.openlocfilehash: 9dab3a7e74b9f69a3df6bd06c3ad868d109343fe
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 会議メディアのネットワークをセットアップします。

Skype 会議メディアの[Skype 会議メディアを有効に](enable-skype-meeting-broadcast.md)した後に、ネットワークを構成する必要があります。組織外のユーザーのウェビナーとその他のブロードキャストを保持する場合は、この手順を実行します。
  
ファイアウォールの設定に経験豊富な場合は、この手順を行うには[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。
  
この手順をスキップして、代わりに、それらをブロードキャストに招待できるように、フェデレーションを別のビジネスを追加、[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)」の手順に従います。
  
## <a name="step-1-set-up-allowed-domains"></a>手順 1: 許可ドメインを設定します。

許可ドメインを設定するには、 **1 つ**の次の方法を使用します。
  
### 

 **方法 1: Office 365 管理センターを使用します。**
  
1. **Office 365 管理センター**に移動し、左側のナビゲーションで [**設定**] をクリックして > **サービス&amp;アドイン**、[ **Skype for Business**] を選びます。
    
2. [**外部共有**] ページの [**ドメインの例外****を除くすべてのドメインがブロック**を選択し、[コンマ (,) で、次のドメインを入力します。
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. {[**保存**] をクリックします。}
    
### 

 **方法 2: Windows PowerShell を使用します。**
  
- **[スタート] メニュー**で、 **Windows PowerShell**を右クリックし、[**管理者として実行**] をクリックします。**Windows PowerShell**ウィンドウで、それぞれの行を入力し、[Enter キーを押します。
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>手順 2: 追加の Skype 会議メディア ドメインの Url と IP アドレス

セットアップ中に、2 番目の手順では、最初に必要なし、IP アドレスと Url を操作する Skype 会議メディアに必要な追加のドメインを追加します。
  
- **必要な Skype for Business Online のエンドポイントの Url を追加してどのプレゼンスを表示して IP アドレスが必要な**[次のとおり](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)です。
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>ハイブリッド展開や組織で Skype 会議メディアを設定します。

場合はで実行する必要がありますその他のセットアップ手順、Skype for Business Online の組織とを設置型の Lync Server 2010、Microsoft Lync Server 2013 では、Skype for Business Server 2015 とオンライン ユーザーの両方があるがあり内部設置型。Skype for Business Online 通信を許可するすべてのユーザーを作成し、[Skype 会議メディアに参加できるように、内部設置型の組織を有効にするのには、上記に追加します。このような要件とは何を表示するには、 [Skype 会議メディアのオンプレミス展開の構成](https://go.microsoft.com/fwlink/?LinkId=617070)を参照してください。
  
## <a name="related-topics"></a>関連トピック

[Skype 会議メディアを有効にします。](enable-skype-meeting-broadcast.md)
  
[Office 365 の Url と IP アドレス範囲](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Skype for Business Online をセットアップします。](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

