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
ms.openlocfilehash: 14ab474289e5a677e1125df7146ba7c5a6fc2ca1
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539058"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>Microsoft Teams と Skype for Business の管理センターのチームを管理する
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>概要

IT 管理者である場合、自分の組織で共同作業のためにセットアップされたチームを表示所有者したり更新したりする必要が発生する可能性があります。また、所有者のいないチームに対して所有者を割り当てるなどの修復アクションを実行する必要がある場合もあります。 Microsoft Teams PowerShell モジュールおよび Microsoft Teams と Skype for Business の管理センターを通して、組織で使用されたチームを管理することができます。 これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。

- グローバル管理者
- Teams サービス管理者

自分のアカウントに対して、管理のために試用版でない Teams のライセンスが割り当てられていることを確認する必要もあります。 既知の問題に関連して、自分のアカウントに割り当てられている管理者ロールが **1 つ**だけであることを確認する必要があります。  Microsoft Teams の管理者ロールの詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。PowerShell コマンドレットの使用方法の詳細については、「[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。  

この記事では、Microsoft Teams と Skype for Business の管理センターでの管理ツールの概要を説明します。

## <a name="teams-overview-grid"></a>Teams の概要グリッド

チームの管理ツールは、Microsoft Teams と Skype for Business の管理センターの **Teams** ノードの下にあります。 (管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。

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

メインのチームの概要グリッドから、チーム名をクリックすることによって、任意のチームのチーム プロフィール ページに移動することができます チーム プロフィール ページには、チームのチャネルと設定に加えて、チーム (およびそれをサポートする Office 365 グループ) に属しているメンバー、所有者、およびゲストが表示されます。 チーム プロフィール ページから、次の操作を行うことができます。

- メンバーおよび所有者の追加または削除。
- チャネルの追加または削除 (全般チャネルを削除することはできません)
- チームおよびグループの設定の更新。
 
![チーム プロフィール](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>チームに対する変更

チームの次の要素を変更することができます。
- **チーム内のユーザー** - メンバーの追加や削除、昇格または降格を行うことができます。
- **チャネル** - 新しいチャネルを追加したり既存のチャネルを削除したりすることができます。  既定の「全般」チャネルを削除することはできません。作成したチャネルについては、チャネル名のみを編集することができます。説明を編集することはできません。
- **チーム名**
- **チームの説明**
- **チームのプライバシー** - パブリックまたはプライベート
- **チームの分類** - 自分の Office 365 グループの分類に基づきます
- **チーム メンバーの設定** - チーム メンバーの設定を選択します


チームに対して行う変更はログに記録されます。 グループ設定 (名前、説明、写真、プライバシー、分類、またはチーム メンバー) を変更する場合、これらの変更は監査パイプラインを通して自分自身によるものとされます。 Teams 固有の設定に対するアクションを実行している場合、自分による変更は、チームの全般チャネル内で記録され、自分自身によるものとされます。


## <a name="learn-more"></a>詳細情報

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Microsoft Teams の管理者ロール](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

