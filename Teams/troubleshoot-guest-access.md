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
ms.openlocfilehash: 7e4db423d262f939362400cdec489ca065b5d5c1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086204"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング
======================================================

- 問題がわかっているかどうかを確認するには、「[組織内のサポートチーム](Known-issues.md)」を参照してください。
- Teams でのゲスト アクセスに関する最新のサポートの問題を確認するには、[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)に関するページに移動します。
- ゲストとは、自分の組織の外部のユーザーのことです。 ユーザーが組織内にいる場合 (社内の従業員、オンサイトの請負業者、オンサイトの代理業者など) は、ゲストとして追加することはできません。 これは、関連会社についても同じです。
- 今後実装される新機能や更新されたゲスト アクセス機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。

## <a name="if-your-guests-are-seeing-license-errors"></a>ゲストに対してライセンスのエラーが表示されている場合

Teams のゲスト アクセスでは Azure Active Directory (Azure AD) ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。 ゲスト アクセスは、Microsoft 365 Business Standard、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Microsoft 365 または Office 365 ライセンスは不要です。

> [!NOTE]
> ゲストのゲストのホームテナントで teams を有効にしておく必要があるのは、ゲストが別の (リソース) テナントでゲストとしてチームにサインインして使用できるようにするためです。

ライセンスエラーが表示される場合は、組織でのゲストアクセスのニーズに合わせて、ライセンス要件を特定するために、 [Azure Active DIRECTORY B2B ライセンスガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をお読みください。


- ゲスト ライセンスは、招待する組織に対してカウントされます。 必要なライセンスの数を算出するときは、このことを考慮に入れます。
- 招待されたゲストが別の Microsoft 365 または Office 365 組織から提供されているか、または個人用メールアドレスを使用しているかにかかわらず、ライセンスは組織によってカウントされます。

## <a name="support-for-b2b-user-types"></a>B2B ユーザーの種類のサポート
現在、Teams Only は、[Azure B2B で定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)されている状態 1 および状態 2 のゲスト ユーザーをサポートします。

## <a name="related-topics"></a>関連項目

[Teams でのゲスト アクセス](guest-access.md)


[チームのトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)