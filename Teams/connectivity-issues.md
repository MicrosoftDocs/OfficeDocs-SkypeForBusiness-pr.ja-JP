---
title: Teams クライアントに関する接続の問題のトラブルシューティング
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
ms.openlocfilehash: 524a78f5a588b0a3a233385f7892624c46e5bac541f7e8a13f647e541b0ffbff
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308956"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Microsoft Teams クライアントとの接続に関するトラブルシューティングを行う

Microsoft Teams クライアントで発生する問題のほとんどは、ファイアウォールやプロキシ接続に原因があります。 必要な URL、IP アドレス、ポートがファイアウォールやプロキシで開かれていることを確認することにより、不要なトラブルシューティングを最小限に抑えることができます。 Microsoft Teamsに必要な URL と IP の詳細については、[Microsoft 365とOffice 365 URL と IP アドレス](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)のサポートに関する記事を参照してください。 次のシナリオでは、ファイアウォールで特定の URL とポートを開く必要があります。

- 認証

- Microsoft Teams クライアントの接続性

- グループ作業

- メディア

- [共有サービス]

- サードパーティ統合

- Skype For Business の相互運用

- Skype for Business クライアントの相互運用

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Teamsがオフラインまたは低帯域幅の状態の場合

良いニュースは、オフラインの場合や低帯域幅の状態で実行している場合でも、Teamsが実行し続けるということです。 Teams既存のチャットのすべての未送信メッセージを保存し (最大 24 時間)、オンラインに戻るとすぐに送信されます。 オフラインで 24 時間を超える場合は、Teamsを使用して、送信されていないメッセージを再送信または削除できます。 この機能を新しいチャットに追加する作業に取り組んでおり、このドキュメントが利用可能になった時点で更新されます。

## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)