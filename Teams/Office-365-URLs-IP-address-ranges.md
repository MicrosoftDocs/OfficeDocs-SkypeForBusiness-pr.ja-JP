---
title: 'Office 365 の URL と IP アドレスの範囲 '
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Office 365 の Url と IP アドレスの範囲を適切に構成する方法と、Microsoft Teams サービスとの接続に可能な限り、転送プロキシをバイパスする方法について説明します。
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
ms.openlocfilehash: 8056758fc707c53b780843f2fc25123b92f6e252
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136487"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 の URL と IP アドレスの範囲 
=====================================

Teams のために正しく構成されている必要がある URL、IP アドレス、ポート、およびプロトコルの詳細な最新のリストについては、「[Office 365 URL および IP アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)」をご覧ください。 マイクロソフトは、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Office 365 サービスを改善し、新機能を追加します。 お客様は、この情報が更新または変更されたときに通知を受け取れるように、[RSS で購読](https://go.microsoft.com/fwlink/p/?linkid=236301)することをお勧めします。

Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づいて構築された通話および会議のエクスペリエンスも提供しています。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。 したがって、Skype および Skype for Business の両方に関連付けられる可能性がある必要な URL と IP があります。

すべての Office 365 ワークロードで、推奨される Teams サービスへの接続方法は、可能な場合にフォワード プロキシをバイパスすることです。 プロキシ サーバーがクライアントと Office 365 データ センターとの間に位置している場合、メディアは UDP ではなく TCP 上を強制的に渡るようになり、メディアの品質に影響する可能性があります。 [Office 365 エンドポイントの管理](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)から、トラフィック バイパスを構成するために使用できるサンプルのプロキシ PAC ファイルをダウンロードします。

ネットワークとセキュリティポリシーで、Office 365 トラフィックをプロキシサーバー経由で送信する必要がある場合は、上記の要件が既に満たされていることを確認してから、チームを運用環境に展開してください。 詳細については、「 [Teams または Skype For Business Online のプロキシサーバー](proxy-servers-for-skype-for-business-online.md)」を参照してください。
