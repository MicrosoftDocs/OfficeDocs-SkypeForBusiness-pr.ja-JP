---
title: Microsoft Teams 管理センターでチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 表示またはマイクロソフトのチームの管理センターで、チームを更新する方法について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 956c81b7305a6e26322ab29755b39eefb9a12344
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460245"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでチームを管理する
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>概要

IT 管理者である場合、自分の組織で共同作業のためにセットアップされたチームを表示所有者したり更新したりする必要が発生する可能性があります。また、所有者のいないチームに対して所有者を割り当てるなどの修復アクションを実行する必要がある場合もあります。 マイクロソフト チームの PowerShell モジュールとマイクロソフトのチームの管理センターの両方で、組織で使用されているチームを管理することができます。 これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。

- グローバル管理者
- Teams サービス管理者

You should also make sure that your account has been assigned a non-trial Teams license for management. As part of a known issue, you should make sure that your account has only **one** admin role assigned.  You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

この資料では、マイクロソフト チームの管理センターでのチームの管理ツールの概要を提供します。

## <a name="teams-overview-grid"></a>Teams の概要グリッド

チームの管理ツールは、マイクロソフトのチームの管理センターで [**チーム**] ノードの下。 (管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。

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

マイクロソフトのチームの管理センターを入力すると**チーム**のオプション] の下のチームの一部はチーム概要グリッド内の一覧に表示されません。

**原因**: この問題と、チームが正しくない (まだ) プロファイリングが行われたが認識するために不足しているプロパティにつながることがシステムによって発生します。

**解決方法: は、MS グラフを使用して適切な値にプロパティを設定する手動で**

**{グループ id}** 問題の実際のグループ Id のクエリで、Exchange Online の powershell を使用して取得することができますを"**ExternalDirectoryObjectId**"属性として **「[Get UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)」** コマンドレットに置き換えます。

1. アクセス[グラフのエクスプ ローラー](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. 左のメニューでグラフのエクスプ ローラーにサインインします。

3. クエリ行を変更: 修正プログラム _gt v1.0 _gthttps://graph.microsoft.com/v1.0/groups/{groupid}

4. 要求の本文に次の値を追加します {"resourceProvisioningOptions": ["チーム"]}。

5. 右上でクエリを実行します。

6. チームの概要をマイクロソフトのチーム管理センターでのチームが正しく表示されるを確認します。


## <a name="learn-more"></a>詳細情報

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Microsoft Teams の管理者ロール](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

