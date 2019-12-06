---
title: Microsoft Teams でのゲストアクセスに関する問題のトラブルシューティング
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
description: Microsoft Teams のゲストアクセスに関する問題のトラブルシューティングと解決に役立つ情報を入手します。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871733"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲストアクセスに関する問題のトラブルシューティング
======================================================

> [!IMPORTANT]
> 変更が有効になるまで最大24時間かかることがあります。 


- Teams でのゲストアクセスに関する現在のサポートの問題を確認するには、「 [teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)」を参照してください。
- 問題がわかっているかどうかを確認するには、「 [Microsoft Teams の既知の問題](Known-issues.md)」を参照してください。
- ゲストとは、自分の組織の外部のユーザーのことです。 組織内のユーザー (従業員、オンサイトの請負業者、オンサイトエージェントなど) は、ゲストとして追加することはできません。 これは、関連会社にも提供されます。
- 今後の新規または更新されたゲストアクセス機能については、「 [Teams のロードマップ](https://aka.ms/teamsroadmap)」を参照してください。
- [Teams UserVoice](https://aka.ms/TeamsUserVoice)でご希望のご意見をお聞かせください。

## <a name="if-your-guests-are-seeing-license-errors"></a>ゲストに対してライセンスのエラーが表示されている場合

Teams でのゲストアクセスでは、Azure Active Directory (Azure AD) Business to Business (B2B) とライセンスモデルが使用されます。 ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Office 365 ライセンスは不要です。

ライセンスエラーが表示される場合は、組織でのゲストアクセスのニーズに合わせて、ライセンス要件を特定するために、 [Azure Active DIRECTORY B2B ライセンスガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をお読みください。


- ゲスト ライセンスは、招待する組織に対してカウントされます。 必要なライセンスの数を算出するときは、このことを考慮に入れます。
- 招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。

## <a name="support-for-b2b-user-types"></a>B2B ユーザーの種類のサポート
現在、チームは、 [AZURE B2B によって定義され](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)た状態1と状態2のゲストユーザーをサポートしています。

## <a name="related-topics"></a>関連項目

[Teams でのゲスト アクセス](guest-access.md)


