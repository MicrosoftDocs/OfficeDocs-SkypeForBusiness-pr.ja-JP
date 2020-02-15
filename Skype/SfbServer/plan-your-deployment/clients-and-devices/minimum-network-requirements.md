---
title: Skype 会議アプリの最小ネットワーク要件
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '概要: Office 365 を使用せず、組織によってホストされている会議にアクセスする必要がある組織に関する情報。'
ms.openlocfilehash: 162d05f9786f02258afa080e630c85d4b513db4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033191"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会議アプリの最小ネットワーク要件
 
**概要:** Office 365 を使用せず、組織によってホストされている会議にアクセスする必要がある組織の情報。 この記事は、これらのアプリのユーザーを対象としたものではありません。
  
ユーザーが skype for Business Online でホストされている会議に参加するために Skype 会議アプリを使用できるようにするには、Office 365 を使用していない組織のネットワーク管理者は、以下に記載されている Fqdn、IPs、およびポートをホワイトリストまたはその他の方法で使用できるようにする

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 会議アプリの接続の要件

ここに記載されている情報は、 [Office 365 の url と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)の一部であり、より詳細で、常に最新の状態になります。
                    
 
|アプリ |宛先の Fqdn  |IP アドレス  |ポート  |
|---|---------|---------|---------|
|**Skype 会議アプリ** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*<span></span>officeapps.live.com <br/>\*<span></span>officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   これらの IP アドレスは頻繁に更新されます。  「 [Skype For business の ip 範囲](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)」および「 [Office の ip 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」を参照してください。         |TCP:80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | これらの IP アドレスは頻繁に更新されます。  「 [Skype For business の ip 範囲](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)」および「 [Office の ip 範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」を参照してください。      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[会議クライアントを計画する (Web アプリと会議アプリ)](meetings-clients.md)

[Skype for Business Server で Web ダウンロード可能なクライアントを展開する](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリでサポートされているプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
