---
title: Microsoft 365 と Office 365 URL と IP アドレス範囲
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Microsoft 365 または Office 365 URL と IP アドレス範囲を適切に構成し、可能な場合は転送プロキシをバイパスして Microsoft Teams サービスとの接続を行う方法について説明します。
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
ms.openlocfilehash: e2f638b9fb29c80806082e02f2d0b09ceec619d0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563735"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 と Office 365 URL と IP アドレス範囲

[Microsoft 365 に移動し、Teams 用](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)に正しく構成する必要がある URL、IP アドレス、ポート、プロトコルの詳細で最新の一覧の URL と IP アドレス範囲をOffice 365します。 Microsoft は、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Microsoft 365 サービスおよび Office 365 サービスを改善し、新機能を追加します。 お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)することをお勧めします。

Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。 したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。

すべての Microsoft 365 および Office 365 ワークロードでは、Teams サービスへの推奨される接続方法は、可能な限り前方プロキシをバイパスすることです。 プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。 [Microsoft 365 および Office 365 エンドポイントの管理](/office365/enterprise/managing-office-365-endpoints)からトラフィック バイパスを構成するために使用できるサンプル プロキシ PAC ファイルをダウンロードします。

ネットワークポリシーとセキュリティ ポリシーで Microsoft 365 またはOffice 365トラフィックがプロキシ サーバーを通過する必要がある場合は、Teams を運用環境に展開する前に、上記の要件が既に満たされていることを確認してください。 詳細については、「[Teams 用プロキシ サーバー」または「オンライン Skype for Business」を参照してください](proxy-servers-for-skype-for-business-online.md)。