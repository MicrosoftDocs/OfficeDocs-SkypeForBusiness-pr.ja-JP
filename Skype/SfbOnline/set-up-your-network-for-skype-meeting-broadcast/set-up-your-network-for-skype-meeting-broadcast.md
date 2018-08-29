---
title: Skype 会議ブロードキャスト用にネットワークをセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
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
description: ビジネス オンライン スケジュール、生産、およびブロードキャストの会議、またはイベントを 10,000 の出席者に大規模なオンライン ユーザーを対象にできるようにするには、Skype の Skype 会議のブロードキャスト機能について説明します。
ms.openlocfilehash: 190911fcf87e0b3042bc8895ade016756a58a1ec
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23251660"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 会議ブロードキャスト用にネットワークをセットアップする

Skype 会議のブロードキャストの[Skype 会議のブロードキャストを有効に](enable-skype-meeting-broadcast.md)した後、ネットワークを構成する必要があります。 人、組織外からのウェビナー、他のブロードキャストを保持したい場合は、この手順を実行します。

ファイアウォールの構成に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。

この手順を省略し、代わりに、ブロードキャストに招待するため、フェデレーションに別のビジネスを追加、[ビジネス ユーザー向けの外部の Skype に連絡を許可する](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)の手順に従います。

## <a name="step-1-set-up-allowed-domains"></a>手順 1: を許可するドメインを設定します。

許可するドメインを設定するには、 **1 つ**の次の方法を使用します。

###

 **方法 1: Office 365 の管理ページを使用します。**

1. **Office 365 管理センター**に移動し、左側のナビゲーションでは、[**設定**] をクリックして > **サービス&amp;アドイン**、し、**ビジネスの Skype**を選択します。

2. [**ドメインの例外**の下にある**外部の共有**] ページ**を除くすべてのドメインがブロックされます**がを選択し、コンマ (,) で、次のドメインを入力してください。

  - noammeetings.lync.com

  - emeameetings.lync.com

  - apacmeetings.lync.com

  - resources.lync.com

3. [ **保存**] をクリックします。

###

 **方法 2: Windows PowerShell を使用します。**

- [**スタート] メニュー**から**Windows PowerShell**を右クリックし、**管理者として実行**] をクリックします。 **Windows PowerShell**ウィンドウで、各明細行を入力し、Enter キーを押します。

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>手順 2: 追加の Skype 会議のブロードキャスト ドメイン、Url、および IP アドレス

セットアップ プロセスでは、2 番目の手順では、まず必要し、し、IP アドレスと動作する Skype 会議のブロードキャストに必要な Url を追加するドメインを追加します。

- **オンライン ビジネスのエンドポイントの Url に必要な Skype を追加しどれを見ることによって IP アドレスが必要**[ここで](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)ください。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>ハイブリッド展開および組織で Skype 会議のブロードキャストを設定します。

場合は、他のセットアップで実行する必要がありますが、オンライン ビジネスの組織と、設置型展開の Lync Server 2010、Microsoft Lync Server 2013、および Skype、Skype ビジネス サーバー 2015 のとオンライン両方のユーザーが存在している設置ビジネス オンラインの Skype で通信し、すべてのユーザーを作成し、Skype の会議のブロードキャストに参加できるように、設置型の組織を有効にするのには、上記に追加します。 それらの要件とはどのようなものを表示するには、 [Skype 会議のブロードキャスト用の設置型展開の構成](https://go.microsoft.com/fwlink/?LinkId=617070)を参照してください。

## <a name="related-topics"></a>関連トピック

[Skype 会議ブロードキャストを有効にする](enable-skype-meeting-broadcast.md)

[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



