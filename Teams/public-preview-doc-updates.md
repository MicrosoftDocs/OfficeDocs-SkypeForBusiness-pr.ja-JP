---
title: Microsoft Teams でのパブリック プレビュー
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams のパブリック プレビューについて説明します。新機能を試して、フィードバックを送信してください。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 6de899156cb4d6267d5a0fda6a8afef8cb9ad358cc4ebeb73514b276abdb817b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285696"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams パブリック プレビュー

> [!NOTE]
> プレビューに含まれている機能は完全でないため、一般公開前に変更される場合があります。これらは、評価と調査のみを目的としています。Office 365 Government Community Cloud (GCC) ではサポートされていません。

Microsoft Teams のパブリック プレビューを使用すると、Teams の未公開機能にいち早くアクセスできます。プレビューでは、今後加えられる機能を探したり、テストしたりできます。パブリック プレビューのあらゆる機能に関するフィードバックをお待ちしております。パブリック プレビューは、それぞれのチーム ユーザーごとに有効になっているので、組織全体への影響を心配する必要はありません。

Teams のパブリック プレビューで利用可能な機能の一覧については、「[Release Notes for Office Current Channel (Preview) (Office 最新チャネル (プレビュー版) のリリース ノート)](/officeupdates/current-channel-preview)」を参照してください。

## <a name="set-the-update-policy"></a>更新ポリシーを設定する

パブリック プレビューは、ユーザー単位で有効になっています。また、パブリック プレビューを有効にするオプションは管理者ポリシーで制御されます。更新ポリシーは、Teams アプリのプレリリースやプレビュー機能を表示する Teams や Office のプレビュー ユーザーを管理するために使用されます。グローバル (組織全体の既定) ポリシーを使用してカスタマイズすることも、ユーザー用に 1 つまたは複数のカスタム ポリシーを作成することもできます。このポリシーは、グローバル ポリシーを上書きしないため、特定のユーザーに割り当てる必要があります。

1. 管理センターにサインインします。
2. **[Teams**>**更新ポリシー]** を選択します。

   ![[更新ポリシー オプション] を選択します。](media/updatePolicies.png)

3. **[追加]** を選択します。
4. 更新ポリシーに名前を付け、説明を追加し **[プレビュー機能の表示]** をオンにします。

また、`-AllowPreview` ブール型パラメーターを指定して `Set-CsTeamsUpdateManagementPolicy` コマンドレットを使用すると、PowerShell を使用してポリシーを設定することもできます。

## <a name="enable-public-preview"></a>パブリック プレビューを有効にする

デスクトップまたは Web クライアントでパブリック プレビューを有効にするには、次のタスクを実行する必要があります。

1. プロフィールの左側にある 3 つのドットを選択して、[Teams] メニューを表示します。
2. **[情報]** > **[パブリック プレビュー]** を選択します。
3. **[パブリック プレビューに切り替える]** を選択します。

## <a name="related-topics"></a>関連項目

[開発者向けパブリック プレビュー](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
