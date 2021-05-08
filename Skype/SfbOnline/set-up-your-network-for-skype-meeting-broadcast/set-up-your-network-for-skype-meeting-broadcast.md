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
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Skype for Business Online の Skype 会議ブロードキャスト機能について学習します。この機能を使用すると、最大 10,000 人のオンライン ユーザーに会議やイベントをスケジュール、作成、ブロードキャストできます。
ms.openlocfilehash: da27110313765bb50df92e3bafb6f09ceae5f301
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237553"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 会議ブロードキャスト用にネットワークをセットアップする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[会議[ブロードキャスト] Skypeを有効Skype、](enable-skype-meeting-broadcast.md)ネットワークを構成する必要があります。 社外のユーザー向けウェビナーや他のブロードキャストを開催する場合は、この手順を実行します。

> [!IMPORTANT]
> Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、その時点でサービスへのアクセスが終了します。 お客様には、コミュニケーションとチームワークの中核となるMicrosoft Teamsクライアントであるクライアントへのアップグレードを開始Microsoft 365。

ファイアウォールを構成する経験が十分でない場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用してこの手順を実行することを検討してください。

この手順をスキップし、代わりにフェデレーションに別のビジネスを追加してブロードキャストに招待するには、「ユーザーが外部のユーザーに連絡することを許可する」の手順に従Skype for Business[します](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。

## <a name="step-1-set-up-allowed-domains"></a>手順 1: 許可されているドメインを設定する

次 **のいずれかの** 方法を使用して、許可されているドメインを設定します。

## #

 **方法 1: 管理センターを使用する**

1. 管理センターに移動し、左側のナビゲーションで [設定Services アドイン] をクリックし、[Skype for Business]  >  **&amp;****を選択します**。

2. [**ドメインの例外**]の [外部共有] ページで、[すべてのドメインがブロックされます] を選択し、次のドメインをコンマ (,) で区切って入力します。

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. **[保存]** をクリックします。

## #

 **方法 2: Windows PowerShell**

- [スタート]**メニューの [** ファイル名] を右 **クリックWindows PowerShell** 管理者として **実行] をクリックします**。 このウィンドウ **Windows PowerShell、** 各行を入力し、Enter キーを押します。

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>手順 2: 会議Skype、URL、IP アドレスを追加する

セットアップ プロセスの 2 番目の手順では、最初に必要なドメインを追加してから、Skype 会議ブロードキャストを機能するために必要な IP アドレスと URL を追加します。

- **必要なエンドポイント URL Skype for Business IP** アドレスを追加するには、 で必要な URL を確認 [します](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>ハイブリッド展開Skype組織で会議ブロードキャストをセットアップする

Skype for Business Online 組織と Lync Server 2010、Microsoft Lync Server 2013、および Skype for Business Server 2015 のオンプレミス展開を使用し、オンラインとオンプレミスの両方のユーザーを持っている場合は、オンプレミスの組織が Skype for Business Online と通信し、すべてのユーザーが Skype 会議ブロードキャストに参加するために、上記の手順に加えて必要なセットアップ手順もあります。 これらの要件を確認するには、「会議ブロードキャスト用にオンプレミスデプロイを構成[するSkype参照してください](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)。

## <a name="related-topics"></a>関連トピック

[Skype 会議ブロードキャストを有効にする](enable-skype-meeting-broadcast.md)

[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
