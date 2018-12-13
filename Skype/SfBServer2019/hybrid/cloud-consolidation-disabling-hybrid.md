---
title: ハイブリッド クラウドへの移行を完了するを無効にします。
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、チームおよびビジネス用の Skype のためのクラウドの統合の一部としてハイブリッドを無効にする詳細な手順が含まれています。
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247690"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>ハイブリッド クラウドへの移行を完了するを無効にします。

オンプレミスからクラウドに移行するすべてのユーザーを移動した後は、ビジネスの展開の設置型の Skype を解除できます。 以外のハードウェアを削除するには、重要なステップは、ハイブリッドを無効にしてから Office 365 には、その設置型展開を論理的に分離。 ハイブリッドを無効にするには、3 つのステップで構成されます。

1. Office 365 をポイントする DNS レコードを更新します。
2. Office 365 テナント ドメイン分割を無効にします。
3. Prem 上での機能は、Office 365 との通信を無効にします。


次の手順は、単位としてまとめて行う必要があります。 詳細情報が記載されています。

> [!Note] 
> まれに、組織の Office 365 に施設内のポイントから DNS を変更する場合があります連合その他の組織が、フェデレーションの構成を更新するまで動作を停止するのにはいくつか他の組織。<ul><li>
古いの直接フェデレーション モデル (とも呼ばれる許可されたパートナー サーバー) を使用しているフェデレーションの組織は、プロキシの FQDN を削除するのには、組織に対して、許可されているドメインのエントリを更新する必要があります。 この従来のフェデレーション モデルに基づかない DNS SRV レコードでは、組織がクラウドへの移動後に、このような構成が古くなったためです。 </li><li>Sipfed.online.lync を有効になっているホスティング プロバイダーがない連合組織です。<span>com を有効にするのには、その構成を更新する必要があります。 このような状況を可能なは、フェデレーション組織設置型には、ハイブリッドまたはオンラインのテナントと連合がない場合だけです。 このような場合は、そのホスティング プロバイダーを有効にするまでこれらの組織とのフェデレーションは機能しません。</li></ul>疑われる場合は、直接フェデレーションを使用して、フェデレーション パートナーのいずれか、またはオンラインのいずれかのフェデレーションがハイブリッド組織では、私たちを提案することを送信する通信について、クラウドへの移行を完了する前にします。

1.  *Office 365 を指すように DNS を更新します。*
設置組織の組織の外部の DNS では、ビジネス記録の Skype は設置型展開ではなく Office 365 をポイントするように更新する必要があります。 具体的には：

    |レコードの種類|名前|TTL|値|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync。<span>com|
    |SRV|ゾーンに追加|3600|100 1 443 sipdir.online.lync。<span>com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync。<span>com|
    |CNAME| sip|    3600|   sipdir.online.lync。<span>com|
    |CNAME| 対応|   3600|   webdir.online.lync。<span>com|
    |CNAME| ダイヤルイン  |3600|  webdir.online.lync。<span>com|

2.  *Office 365 のテナントでの SIP アドレス空間の共有を無効にします。*
次のコマンドは、Skype のビジネス オンライン PowerShell ウィンドウから実行する必要があります。

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Prem 上での機能は、Office 365 との通信を無効にします。*  
次のコマンドでは、オンプレミスの PowerShell ウィンドウから実行する必要があります。  ビジネスのオンライン セッションの以前の Skype をインポートした場合は、ビジネスの PowerShell セッションで新しい Skype を起動します。

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>関連項目

[チームと Skype のビジネス向けのクラウド統合](cloud-consolidation.md)