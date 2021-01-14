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
description: 最大 10,000 人のオンライン参加者に会議やイベントをスケジュール、作成、ブロードキャストできる Skype for Business Online の Skype 会議ブロードキャスト機能について学習します。
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865161"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 会議ブロードキャスト用にネットワークをセットアップする

Skype 会議 [ブロードキャストの Skype 会議ブロードキャストを](enable-skype-meeting-broadcast.md) 有効にした後、ネットワークを構成する必要があります。 社外のユーザーのためにウェビナーや他のブロードキャストを開催する場合は、この手順を実行します。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、サービスへのアクセスが終了します。 Microsoft 365 のコミュニケーションとチームワークのコア クライアントである Microsoft Teams へのアップグレードを開始する方法をお勧めしています。

ファイアウォールの構成にまだ時間がかからなかった場合は、この手順を [実行するために Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用することを検討してください。

この手順をスキップし、代わりに別のビジネスをフェデレーションに追加してブロードキャストに招待するには、「ユーザーが外部の Skype for Business ユーザーに連絡することを許可する」の [手順に従います](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。

## <a name="step-1-set-up-allowed-domains"></a>手順 1: 許可されているドメインをセットアップする

次 **のいずれかの** 方法を使用して、許可されたドメインをセットアップします。

## #

 **方法 1: 管理センターを使用する**

1. 管理センターに移動し、左側のナビゲーションで **[Settings** Services アドイン] をクリックし  >  **&amp;****、[Skype for Business] を選択します**。

2. [ドメインの **例外**]の [外部共有] ページで、[ブロックするドメインを除くすべてのドメイン] を選択し、次のドメインをコンマ (,) で区切って入力します。

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. **[保存]** をクリックします。

## #

 **方法 2: 次の方法Windows PowerShell**

- [スタート] **メニューで、** アプリを右 **クリックWindows PowerShell、[** 管理者として実行] **をクリックします**。 ウィンドウの **Windows PowerShell、** 各行を入力し、Enter キーを押します。

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>手順 2: Skype 会議ブロードキャストのドメイン、URL、IP アドレスを追加する

セットアップ プロセスの 2 番目の手順では、最初に必要なドメインを追加してから、Skype 会議ブロードキャストを動作するために必要な IP アドレスと URL を追加します。

- **必要な Skype for Business Online** エンドポイントの URL と IP アドレスを追加するには、ここで必要な URL を確認 [します](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>ハイブリッド展開と組織で Skype 会議ブロードキャストをセットアップする

Skype for Business Online 組織と Lync Server 2010、Microsoft Lync Server 2013、および Skype for Business Server 2015 のオンプレミス展開を使用し、オンラインとオンプレミスの両方のユーザーを持っている場合、オンプレミスの組織が Skype for Business Online と通信し、すべてのユーザーが Skype 会議ブロードキャストに参加するには、上記の手順に加えて実行する必要があるその他のセットアップ手順があります。 これらの要件を確認するには、「Skype 会議ブロードキャストのオンプレミス展開を構成する」 [を参照してください](https://go.microsoft.com/fwlink/?LinkId=617070)。

## <a name="related-topics"></a>関連項目

[Skype 会議ブロードキャストを有効にする](enable-skype-meeting-broadcast.md)

[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



