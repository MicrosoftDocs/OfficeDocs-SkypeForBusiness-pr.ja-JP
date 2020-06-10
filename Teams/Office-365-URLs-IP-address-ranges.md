---
title: Microsoft 365 および Office 365 の Url と IP アドレスの範囲
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Microsoft Teams サービスとの接続に可能な場合、Microsoft 365 または Office 365 Url と IP アドレス範囲を適切に構成し、転送プロキシをバイパスする方法について説明します。
localization_priority: Normal
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
ms.openlocfilehash: 30736a347f447d265059de1a26ded5ef690e53dc
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665693"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 および Office 365 の Url と IP アドレスの範囲
=======================================================

Office の Url、IP アドレス、ポート、プロトコルの詳細と最新の一覧を表示するには、 [Microsoft 365 および Office 365 の url と ip アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。 Microsoft は、Microsoft 365 および Office 365 サービスを継続的に改善し、新しい機能を追加しています。これは、必要なポート、Url、IP アドレスが時間の経過と共に変化する可能性があることを意味します。 お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)することをお勧めします。

Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。 したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。

Microsoft 365 および Office 365 のすべてのワークロードについては、可能であれば、Teams サービスへの推奨される接続方法をバイパスすることをお勧めします。 プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。 [Microsoft 365 および Office 365 エンドポイントの管理](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)からのトラフィックのバイパスを構成するために使用できるサンプルのプロキシ PAC ファイルをダウンロードします。

ネットワークとセキュリティポリシーで、Microsoft 365 または Office 365 のトラフィックをプロキシサーバー経由で送信する必要がある場合は、前述の要件を既に満たしていることを確認してから、チームを運用環境に展開してください。 詳細については、「 [Teams または Skype For Business Online のプロキシサーバー](proxy-servers-for-skype-for-business-online.md)」を参照してください。
