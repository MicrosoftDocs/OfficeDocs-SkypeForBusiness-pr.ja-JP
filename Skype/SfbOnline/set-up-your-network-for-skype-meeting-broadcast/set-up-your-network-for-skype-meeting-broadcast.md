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
f1keywords: None
ms.custom:
- SMB
description: Skype for Business Online の Skype 会議ブロードキャスト機能について説明します。この機能を使用すると、最大1万人までの会議やイベントのスケジュール、作成、ブロードキャストを行うことができます。
ms.openlocfilehash: f9a85a1f64f88b55d99c7a27694a46b7ea885849
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301290"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 会議ブロードキャスト用にネットワークをセットアップする

Skype[会議ブロードキャスト](enable-skype-meeting-broadcast.md)の Skype 会議ブロードキャストを有効にしたら、ネットワークを設定する必要があります。 社外の人に対して、ウェビナーやその他のブロードキャストを保留にする場合は、この手順を実行します。

ファイアウォールの設定が整っていない場合は、この手順を実行するために[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を採用することを検討してください。

この手順をスキップして、別のビジネスをフェデレーションに追加して、ブロードキャストに招待できるようにするには、「[ユーザーが外部の Skype For business ユーザーに連絡](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)できるようにする」の手順に従ってください。

## <a name="step-1-set-up-allowed-domains"></a>手順 1: 許可したドメインをセットアップする

許可したドメインをセットアップするには、次の**いずれか**の方法を使用します。

## #

 **方法 1: Office 365 管理センターを使用する**

1. **Office 365 管理センター**に移動し、左のナビゲーションで [**設定** > **サービス&amp;アドイン**] をクリックして、[ **Skype for business**] を選びます。

2. [**外部共有**] ページの [**ドメインの例外**] で、[すべてのドメインを**ブロックする**] を選択し、次のドメインをカンマ (,) で区切って入力します。

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. [**保存**] をクリックします。

## #

 **方法 2: Windows PowerShell を使用する**

- [**スタート] メニュー**で、[ **Windows PowerShell** ] を右クリックし、[**管理者として実行**] をクリックします。 **Windows PowerShell**ウィンドウで、各行を入力し、enter キーを押します。

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>手順 2: Skype 会議ブロードキャストのドメイン、Url、IP アドレスを追加する

セットアッププロセスの2番目の手順では、最初に必要なドメインを追加してから、Skype 会議ブロードキャストを使用するために必要な IP アドレスと Url を追加します。

- 必要なものを確認**して、必要な Skype For Business Online エンドポイント url と IP アドレスを追加**する[こちらをご覧](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)ください。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>ハイブリッド展開と組織で Skype 会議ブロードキャストをセットアップする

Skype for Business Online の組織と、Lync server 2010、Microsoft Lync Server 2013、および Skype for Business Server 2015 のオンプレミスの展開と、両方のユーザーがオンラインとオンプレミスの両方を使用している場合は、別のセットアップ手順を実行する必要があります。上のものに加えて、オンプレミスの組織が Skype for Business Online と通信できるようにし、すべてのユーザーが Skype 会議ブロードキャストに参加できるようにすることができます。 これらの要件については、「 [Skype 会議ブロードキャスト用にオンプレミス展開を構成](https://go.microsoft.com/fwlink/?LinkId=617070)する」を参照してください。

## <a name="related-topics"></a>関連トピック

[Skype 会議ブロードキャストを有効にする](enable-skype-meeting-broadcast.md)

[Office 365 の URL と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



