---
title: Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837637"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング
======================================================

> [!IMPORTANT]
> 変更が有効になるまで最大で 24 時間かかる場合があります。 


- Teams でのゲスト アクセスに関する最新のサポートの問題を確認するには、[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)に関するページに移動します。
- Microsoft がお客様の問題を把握しているかどうかを確認するには、「[Microsoft Teams の既知の問題](Known-issues.md)」を参照してください。
- ゲストとは、自分の組織の外部のユーザーのことです。 ユーザーが組織内にいる場合 (社内の従業員、オンサイトの請負業者、オンサイトの代理業者など) は、ゲストとして追加することはできません。 これは、関連会社についても同じです。
- 今後実装される新機能や更新されたゲスト アクセス機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。

## <a name="if-your-guests-are-seeing-license-errors"></a>ゲストに対してライセンスのエラーが表示されている場合

Teams のゲスト アクセスでは Azure Active Directory (Azure AD) ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。 ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Office 365 ライセンスは不要です。

ライセンスのエラーが表示される場合は、[Azure Active Directory B2B ライセンスのガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)を必ず読んで、自分の組織でのゲスト アクセスのニーズを満たすライセンスの要件を判断してください。


- ゲスト ライセンスは、招待する組織に対してカウントされます。 必要なライセンスの数を算出するときは、このことを考慮に入れます。
- 招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。

## <a name="support-for-b2b-user-types"></a>B2B ユーザーの種類のサポート
現在、Teams Only は、[Azure B2B で定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)されている状態 1 および状態 2 のゲスト ユーザーをサポートします。

## <a name="related-topics"></a>関連項目

[Teams でのゲスト アクセス](guest-access.md)


