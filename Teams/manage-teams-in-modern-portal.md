---
title: Microsoft Teams と Skype for Business の管理センターのチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Microsoft Teams と Skype for Business の管理センターで自分のチームの表示や更新を行う方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 210824858d953a99844817b3ef27265626d91928
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562784"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>Microsoft Teams と Skype for Business の管理センターのチームを管理する
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>概要

As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams. You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center. For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:

- グローバル管理者
- Teams サービス管理者

You should also make sure that your account has been assigned a non-trial Teams license for management. As part of a known issue, you should make sure that your account has only **one** admin role assigned.  You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

この記事では、Microsoft Teams と Skype for Business の管理センターでの管理ツールの概要を説明します。

## <a name="teams-overview-grid"></a>Teams の概要グリッド

Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center. (In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.

> [!NOTE]
> 以前に作成されたチームが、このビューに確実に表示されるようにするための埋め戻し処理を現在行っています。

![Teams の概要グリッド](media/manage-teams-in-modern-portal-image1.png)  

このグリッドには、次のプロパティが表示されます。

- **チーム名**
- **チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。
- **ユーザー** - テナントの所有者、ゲスト、およびメンバーを含む合計ユーザーの数。
- **所有者** - このチームの所有者の数。
- **ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。
- **プライバシー** - 背後にある Office 365 グループの AccessType 

### <a name="search"></a>検索

検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。

### <a name="edit"></a>編集

グリッドからチームを選択し、[**編集**] ボタンを選択することによって、グループおよびチーム固有の設定を編集することができます。

![チームの編集](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>チーム プロフィール

You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name. The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings. From the team profile page, you can:

- メンバーおよび所有者の追加または削除。
- チャネルの追加または削除 (全般チャネルを削除することはできません)
- チームおよびグループの設定の更新。
 
![チーム プロフィール](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>チームに対する変更

チームの次の要素を変更することができます。
- **チーム内のユーザー** - メンバーの追加や削除、昇格または降格を行うことができます。
- **Channels** - you can add new channels or remove existing channels.  You cannot delete the default "General" channel, and once created you can only edit channel name, not description.
- **チーム名**
- **チームの説明**
- **チームのプライバシー** - パブリックまたはプライベート
- **チームの分類** - 自分の Office 365 グループの分類に基づきます
- **チーム メンバーの設定** - チーム メンバーの設定を選択します


The changes that you make to a team are logged. If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline. If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.

## <a name="troubleshooting"></a>トラブルシューティング

**問題: チームのチーム概要グリッドに表示されません。**

Skype ビジネス管理センターの Microsoft チームの & を入力すると**チーム**のオプション] の下のチームの一部はチーム概要グリッド内の一覧に表示されません。

**原因**: この問題と、チームが正しくない (まだ) プロファイリングが行われたが認識するために不足しているプロパティにつながることがシステムによって発生します。

**解決方法: は、MS グラフを使用して適切な値にプロパティを設定する手動で**

**{グループ id}** 問題の実際のグループ Id のクエリで、Exchange Online の powershell を使用して取得することができますを"**ExternalDirectoryObjectId**"属性として **「[Get UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)」** コマンドレットに置き換えます。

1. アクセス[グラフのエクスプ ローラー](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. メニューの左側にあるグラフのエクスプ ローラーにサインインします。

3. クエリ行を変更: 修正プログラム _gt v1.0 _gthttps://graph.microsoft.com/v1.0/groups/{groupid}

4. 要求の本文に次の値を追加します {"resourceProvisioningOptions": ["チーム"]}。

5. 右上でクエリを実行します。

6. チームの概要をチームは、マイクロソフトのチームの & のビジネス管理センターでは、Skype で正しく表示されるを確認します。


## <a name="learn-more"></a>詳細情報

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Microsoft Teams の管理者ロール](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

