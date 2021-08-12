---
title: Microsoft 365 URL Office 365 IP アドレス範囲
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Microsoft 365 または Office 365 URL と IP アドレス範囲を適切に構成し、Microsoft Teams サービスとの接続に対して転送プロキシをバイパスする方法についてMicrosoft Teamsします。
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
ms.openlocfilehash: f6b42865666538c6af431ab8f6e69ef495f3d5daf89c673a118eb4a2dd429564
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850162"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 URL Office 365 IP アドレス範囲

Teams 用に正しく構成する必要がある URL、IP アドレス、ポート、プロトコルの詳細および最新の一覧については、Microsoft 365 URL と Office 365 URL と[IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)アドレス範囲に関するページを参照してください。 Microsoft は、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Microsoft 365 サービスおよび Office 365 サービスを改善し、新機能を追加します。 お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)することをお勧めします。

Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。 したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。

すべてのワークロードMicrosoft 365およびOffice 365、サービスへの推奨される接続方法はTeams可能な場合は、転送プロキシをバイパスすることです。 プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。 トラフィック バイパスの構成に使用できるサンプル プロキシ PAC ファイルをダウンロードします。このファイルは、エンドポイントの管理Microsoft 365[およびOffice 365します](/office365/enterprise/managing-office-365-endpoints)。

ネットワークポリシーとセキュリティ ポリシーでプロキシ サーバーを通過するために Microsoft 365 または Office 365 トラフィックが必要な場合は、Teams を実稼働環境にデプロイする前に、上記の要件が既に満たTeamsしてください。 詳細については、「プロキシ サーバー for [Teams または Skype for Business Online」を参照してください](proxy-servers-for-skype-for-business-online.md)。