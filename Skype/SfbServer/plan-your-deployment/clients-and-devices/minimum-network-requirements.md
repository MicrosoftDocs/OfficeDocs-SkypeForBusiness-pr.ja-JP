---
title: Skype 会議アプリの最小ネットワーク要件
ms.author: v-cichur
author: cichur
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
description: '概要: Microsoft 365 または Office 365 を使用しない組織、および Microsoft 365 がホストする組織がホストする会議にアクセスする必要がある組織向け情報。'
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816307"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会議アプリの最小ネットワーク要件
 
**概要:**  Microsoft 365 または Office 365 を使用しない組織、および Microsoft 365 がホストする組織がホストする会議にアクセスする必要がある組織向け情報。 この記事は、これらのアプリのユーザー向けではありません。
  
ユーザーが Skype for Business Online でホストされている会議に Skype 会議アプリを使用して参加するには、Microsoft 365 または Office 365 を使用しない組織のネットワーク管理者が、以下に説明する FQDN、IPS、およびポートを許可するか、利用できる必要があります。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 会議アプリの接続の要件

ここに示す情報は [、Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)URL と IP アドレス範囲のサブセットであり、より深く提供され、常に最新の情報になります。
                    
 
|アプリ |宛先 FQDN  |IP アドレス  |ポート  |
|---|---------|---------|---------|
|**Skype 会議アプリ** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   これらの IP アドレスは頻繁に更新されます。  Skype [for Business の IP 範囲と](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) IP 範囲Office [参照](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | これらの IP アドレスは頻繁に更新されます。  Skype [for Business の IP 範囲と](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) IP 範囲Office [参照](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

[Skype for Business Server で Web ダウンロード可能なクライアントを展開する](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリでサポートされるプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
