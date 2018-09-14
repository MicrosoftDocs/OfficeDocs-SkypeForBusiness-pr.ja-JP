---
title: Skype 会議アプリの最小ネットワーク要件
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '組織で Office 365 を使用しないしを行っている組織でホストされている会議にアクセスする必要があります: の概要情報です。'
ms.openlocfilehash: 00862a4acecb8a5e6555f44d9416a2efa5834e61
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965906"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会議アプリの最小ネットワーク要件
 
**の概要:** 組織 Office 365 を使用しないを行っている組織でホストされている会議にアクセスする必要があるユーザーの情報です。 この記事はこれらのアプリのユーザー向けのものではありません。
  
Skype 会議アプリケーションを使用して、オンライン ビジネスの Skype でホストされている会議に参加できるように、組織のネットワーク管理者が Office 365 を使用しないユーザーには、ホワイト リストや、Fqdn、ip アドレス、およびポートは、以下に説明を使用することが必要があります。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 会議アプリの接続の要件

ここで記載されている情報は、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)詳細を提供しは必ず、最新のサブセットです。
                    
 
|アプリケーション |宛先の FQDN  |IP アドレス  |ポート  |
|---|---------|---------|---------|
|**Skype 会議アプリ** | \*。 lync.com <br/>\*。 infra.lync.com<br/>\*。 pipe.aria.microsoft.com<br/>\*。 sfbassets.com<br/>\*。 msecnd.net<br/>\*ブロードキャスト<span></span>です officeapps.live.com。 <br/>\*powerpoint<span></span>です officeapps.live.com。 <br/>\*。 office.live.com<br/>\*。 cdn.office.net<br/>microsoft.com の *.s<br/>        |   これらの IP アドレスは頻繁に更新されます。  [ビジネス IP の範囲の Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)と[Office オンラインの IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)を参照してください。         |TCP: 80 &amp; 443<br/>UDP: 3478 ～ 3481<br/>
|**Teams**    | \*<span></span>。 microsoft.com <br/>\*<span></span>。 skype.com | これらの IP アドレスは頻繁に更新されます。  [ビジネス IP の範囲の Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)と[Office オンラインの IP 範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)を参照してください。      |TCP: 443 <br/> UDP: 3478 ～ 3481

## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="BKMK_Conferencing"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

[Skype のダウンロード可能なクライアントの Web をビジネスのサーバーの展開します。](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリケーションでサポートされるプラットフォーム](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)