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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '概要: 組織がホストする会議にMicrosoft 365またはOffice 365する必要がある組織の情報。'
ms.openlocfilehash: 29b9103d741440a480be27e9d4268d6cc8d94c47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615613"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会議アプリの最小ネットワーク要件
 
**概要:** 組織がホストする会議にMicrosoft 365またはOffice 365する必要がある組織向け情報。 この記事は、これらのアプリのユーザー向けではありません。
  
Skype Meetings App を使用して Skype for Business Online でホストされる会議に参加するには、Microsoft 365 または Office 365 を使用しない組織のネットワーク管理者が、以下に示す FQDN、AP、ポートを許可または利用できる必要があります。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>会議アプリSkypeの要件

ここに示す情報は、Office 365 [IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)アドレス範囲のサブセットであり、より深く、常に最新の情報になります。
                    
 
|アプリ |宛先 FQDN  |IP アドレス  |ポート  |
|---|---------|---------|---------|
|**Skype 会議アプリ** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   これらの IP アドレスは頻繁に更新されます。  IP [Skype for Businessと IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)範囲Office[参照](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | これらの IP アドレスは頻繁に更新されます。  IP [Skype for Businessと IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)範囲Office[参照](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

[Web ダウンロード可能なクライアントを展開Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[会議アプリでサポートSkypeプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
