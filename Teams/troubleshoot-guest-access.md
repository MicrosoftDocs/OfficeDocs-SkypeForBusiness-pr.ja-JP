---
title: Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティングと解決に役立つヘルプをご利用ください。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8d54e236583211c2a8169987bf03ceba756facf
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641217"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング

- お客様の問題について知っているかどうかを確認するには、「組織のサポート[Teams」を参照してください](/MicrosoftTeams/troubleshoot/teams-welcome)。
- Teams でのゲスト アクセスに関する最新のサポートの問題を確認するには、[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/)に関するページに移動します。
- ゲストは組織外のユーザーです。 ユーザーが組織内にいる場合 (社内の従業員、オンサイトの請負業者、オンサイトの代理業者など) は、ゲストとして追加することはできません。 これは、関連会社についても同じです。
- 今後実装される新機能や更新されたゲスト アクセス機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>ゲストに対してライセンスのエラーが表示されている場合

Teams のゲスト アクセスでは Azure Active Directory (Azure AD) ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。 ゲスト アクセスは、Microsoft 365 Business Standard、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Microsoft 365 または Office 365 ライセンスは不要です。

> [!NOTE]
> Teamsゲストがサインインして別の (リソース) テナントのゲストとして Teams を使用するには、ゲストのホーム テナントで有効にする必要があります。

ライセンス エラーが表示される場合は[、Azure AD](/azure/active-directory/external-identities/external-identities-pricing)外部 ID の課金モデルを読んで、組織のゲスト アクセスのニーズを満たすライセンス要件を決定してください。

- ゲスト ライセンスは、招待する組織に対してカウントされます。 必要なライセンスの数を算出するときは、このことを考慮に入れます。
- ライセンスは、招待されたゲストが別の組織から送信された場合でも、Microsoft 365メール アドレスを使用している場合でも、組織に対してカウントされます。

## <a name="related-topics"></a>関連項目

[Teams でのゲスト アクセス](guest-access.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
