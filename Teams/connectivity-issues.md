---
title: クライアントの接続に関する問題Teamsトラブルシューティング
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: ファイアウォールまたはプロキシ接続が主な原因である Microsoft Teams クライアントの接続性の問題をトラブルシューティングする方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9ef787a5e103649c1526fab321cc8a9a088254c
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856166"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Microsoft Teams クライアントとの接続に関するトラブルシューティングを行う

Microsoft Teams クライアントで発生する問題のほとんどは、ファイアウォールやプロキシ接続に原因があります。 必要な URL、IP アドレス、ポートがファイアウォールやプロキシで開かれていることを確認することにより、不要なトラブルシューティングを最小限に抑えることができます。 Microsoft Teams に必要な URL と IP の詳細については、Microsoft 365 URL と IP アドレスのOffice 365に関する記事[を](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)参照してください。 次のシナリオでは、ファイアウォールで特定の URL とポートを開く必要があります。

- 認証

- Microsoft Teams クライアントの接続性

- グループ作業

- メディア

- [共有サービス]

- サードパーティ統合

- Skype For Business の相互運用

- Skype for Business クライアントの相互運用

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>オフラインTeamsまたは低帯域幅の状態の場合

オフラインまたは低帯域幅のTeamsでも、この機能は実行し続けるのが良いニュースです。 Teamsチャットのすべての未送信メッセージを保存し (最大 24 時間)、オンラインに戻るとすぐに送信します。 オフライン状態が 24 時間を超える場合は、Teamsメッセージの再送信または削除を選択できます。 この機能を新しいチャットに追加する作業を行っています。利用可能な場合は、このドキュメントを更新します。

## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)