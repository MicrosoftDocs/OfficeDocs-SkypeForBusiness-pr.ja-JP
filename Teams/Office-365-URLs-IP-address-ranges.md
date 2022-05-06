---
title: URL と IP アドレス範囲のMicrosoft 365とOffice 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: URL と IP アドレス範囲のMicrosoft 365またはOffice 365を適切に構成し、Microsoft Teams サービスとの接続に可能な場合は転送プロキシをバイパスする方法について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebbac20f7306aa5014aa5703a57813e3c631a9d3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601222"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL と IP アドレス範囲のMicrosoft 365とOffice 365

Teams用に正しく構成する必要がある [URL、IP アドレス](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)、ポート、プロトコルの詳細で最新の一覧については、Microsoft 365とOffice 365 URL と IP アドレス範囲に移動します。 Microsoft は、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Microsoft 365 サービスおよび Office 365 サービスを改善し、新機能を追加します。 お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)することをお勧めします。

Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。 したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。

すべてのMicrosoft 365およびOffice 365ワークロードで、サービスをTeamsするための推奨される接続方法は、可能な限り前方プロキシをバイパスすることです。 プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。 [Microsoft 365とOffice 365エンドポイントの管理](/office365/enterprise/managing-office-365-endpoints)からトラフィック バイパスを構成するために使用できるサンプル プロキシ PAC ファイルをダウンロードします。

ネットワークポリシーとセキュリティ ポリシーで、プロキシ サーバーを通過するためにMicrosoft 365またはOffice 365トラフィックが必要な場合は、運用環境にTeamsを展開する前に、上記の要件が既に満たされていることを確認してください。 詳細については、[TeamsまたはオンラインSkype for Business用のプロキシ サーバーに関する記事を参照](proxy-servers-for-skype-for-business-online.md)してください。