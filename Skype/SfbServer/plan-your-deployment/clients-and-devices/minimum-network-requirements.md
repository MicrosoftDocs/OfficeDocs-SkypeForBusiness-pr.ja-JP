---
title: Skype 会議アプリの最小ネットワーク要件
ms.author: serdars
author: SerdarSoysal
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
description: '概要: Microsoft 365またはOffice 365を使用せず、組織がホストする会議にアクセスする必要がある組織向けの情報。'
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674529"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会議アプリの最小ネットワーク要件

**概要：** Microsoft 365またはOffice 365を使用せず、組織がホストする会議にアクセスする必要がある組織の情報。 この記事は、エンド ユーザーのOffice 365またはMicrosoft 365向けではありません。

Microsoft 365またはOffice 365を使用していない組織のSkype会議アプリのユーザーは、Skype for Business Online で開催される会議に出席する必要がある場合があります。 これらの会議に出席するには、ネットワーク管理者がファイアウォール経由で次の FQDN、IP アドレス、ポートを許可する必要があります。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype Meetings アプリ接続の要件

ここに示す情報は、[Office 365 URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)の情報のサブセットです。 このトピックは、より詳細であり、常に最新のトピックになります。

|アプリ|宛先 FQDN|IP アドレス|ポート|
|---|---------|---------|---------|
|**Skype会議アプリ**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|これらの IP アドレスは頻繁に更新されます。 [IP 範囲のSkype for BusinessとMicrosoft Teams](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)、および [IP 範囲のOffice](/microsoft-365/enterprise/urls-and-ip-address-ranges)を参照してください|TCP: 80 & 443<br/>UDP: 3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|これらの IP アドレスは頻繁に更新されます。 [IP 範囲のSkype for BusinessとMicrosoft Teams](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)、および [IP 範囲のOffice](/microsoft-365/enterprise/urls-and-ip-address-ranges)を参照してください|TCP: 443 <br/> UDP: 3478-3481|

## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](meetings-clients.md)

[Skype for Business Serverに Web ダウンロード可能なクライアントをデプロイする](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype Meetings App でサポートされているプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
