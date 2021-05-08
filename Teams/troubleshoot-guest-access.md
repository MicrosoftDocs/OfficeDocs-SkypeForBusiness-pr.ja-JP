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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948684"
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
> Teamsゲストがサインインし、別の (リソース) テナントのゲストとして Teams を使用するには、ゲストのホーム テナントで有効にする必要があります。

ライセンス エラーが発生する場合は [、Azure AD 外部](/azure/active-directory/external-identities/external-identities-pricing) ID の課金モデルを読んで、組織内のゲスト アクセスのニーズを満たすライセンス要件を決定してください。

- ゲスト ライセンスは、招待する組織に対してカウントされます。 必要なライセンスの数を算出するときは、このことを考慮に入れます。
- ライセンスは、招待されたゲストが別の組織から送信された場合でも、Microsoft 365メール アドレスを使用している場合でも、組織に対してカウントされます。

## <a name="support-for-b2b-user-types"></a>B2B ユーザーの種類のサポート

現在、Teams Only は、[Azure B2B で定義](/azure/active-directory/b2b/user-properties)されている状態 1 および状態 2 のゲスト ユーザーをサポートします。

## <a name="related-topics"></a>関連項目

[Teams でのゲスト アクセス](guest-access.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)