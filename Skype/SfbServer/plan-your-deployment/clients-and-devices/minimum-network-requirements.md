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
description: '概要: Office 365 を使用している組織が開催する会議に、Office 365 を使用していない組織がアクセスすることが必要な場合に役立つ情報です。'
ms.openlocfilehash: e158d93b68df761b59535f4e9239d14194c10443
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816026"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会議アプリの最小ネットワーク要件
 
**概要:** Office 365 を使用している組織が開催する会議に、Office 365 を使用していない組織がアクセスすることが必要な場合に役立つ情報です。 この記事はこれらのアプリのユーザーを対象にしていません。
  
ユーザーが Skype for Business Online で開催された会議に Skype 会議アプリを使用して出席できるようにするには、Office 365 を使用していないネットワーク管理者が、下記の FQDN、IP、およびポートをホワイトリストに記載するか、そうでない場合はそれらを利用できる状態にします。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 会議アプリの接続の要件

「[Office 365 の URL と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」には、常に最新の情報が詳細に記載されていますが、ここで示されている情報はその一部です。
                    
 
|アプリ |宛先の FQDN  |IP アドレス  |ポート  |
|---|---------|---------|---------|
|**Skype 会議アプリ** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com <br/>\*powerpoint.officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   これらの IP アドレスは頻繁に更新されます。  [Skype For business の ip 範囲](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)および OFFICE の[ip 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)を表示する         |TCP: 80、443<br/>UDP: 3478 ～ 3481<br/>
|**Teams**    | \*.microsoft.com <br/>\*.skype.com | これらの IP アドレスは頻繁に更新されます。  [Skype For business の ip 範囲](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)および OFFICE の[ip 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)を表示する      |TCP: 443 <br/> UDP: 3478 ～ 3481

## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

[Skype for Business Server で Web ダウンロード可能なクライアントを展開する](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリでサポートされるプラットフォーム](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
