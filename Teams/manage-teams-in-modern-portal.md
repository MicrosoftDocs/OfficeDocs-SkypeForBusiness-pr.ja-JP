---
title: Microsoft Teams 管理センターでチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin
description: Microsoft Teams の管理センターで自分のチームの表示や更新を行う方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f495a9cc5b3bfb1fd270e85b2a1fb17bd5f11e68
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233354"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでチームを管理する
==========================================


## <a name="overview"></a>概要

IT 管理者である場合、自分の組織で共同作業のためにセットアップされたチームを表示所有者したり更新したりする必要が発生する可能性があります。また、所有者のいないチームに対して所有者を割り当てるなどの修復アクションを実行する必要がある場合もあります。 組織のチームは、Microsoft Teams PowerShell モジュールと Microsoft Teams 管理センターの両方から管理することができます。 これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。

- グローバル管理者
- Teams サービス管理者

Teams での管理者の役割の詳細については、「[ Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。また、PowerShell コマンドレットを使用してチームを管理する方法の詳細については、「[Microsoft Teams コマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。  

この記事では、Microsoft Teams の管理センターでのチーム 管理ツールの概要を説明します。

## <a name="teams-overview-grid"></a>Teams の概要グリッド

チームの管理ツールは、Microsoft Teams 管理センターの [**Teams**] ノードの下にあります。 (管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。

![チームの概要グリッドのスクリーンショット](media/manage-teams-in-modern-portal-image1.png)  

このグリッドには、次のプロパティが表示されます。

- **チーム名**
- **チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。
- **ユーザー** - テナントの所有者、ゲスト、およびメンバーを含む合計ユーザーの数。
- **所有者** - このチームの所有者の数。
- **ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。
- **プライバシー** - 基となる Office 365 グループの可視性/AccessType。
- **状態** - このチームの状態がアーカイブ済みかアクティブか。  チームのアーカイブに関する詳細については、「[チームをアーカイブまたは復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。
- **グループ ID** - 基となる Office 365 グループの一意の GroupID
- **分類** - 基となる Office 365 の グループに割り当てられている分類 (組織内で使用されている場合)。  分類の詳細については、「[組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)」を参照してください。
- **説明** - 基となる Office 365 グループの説明

### <a name="search"></a>検索

検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。

### <a name="edit"></a>編集

グリッドからチームを選択し、[**編集**] ボタンを選択することによって、グループおよびチーム固有の設定を編集することができます。

![[チームの編集] オプションのスクリーンショット](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>チーム プロフィール

メインのチームの概要グリッドから、チーム名をクリックすることによって、任意のチームのチーム プロフィール ページに移動することができます チーム プロフィール ページには、チームのチャネルと設定に加えて、チーム (およびそれをサポートする Office 365 グループ) に属しているメンバー、所有者、およびゲストが表示されます。 チーム プロフィール ページから、次の操作を行うことができます。

- メンバーおよび所有者の追加または削除。
- チャネルの追加または削除 (全般チャネルを削除することはできません)
- チームおよびグループの設定の更新。
 
![チームプロファイルの例のスクリーンショット](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>チームに対する変更

チームの次の要素を変更することができます。
- **チーム内のユーザー** - メンバーの追加や削除、昇格または降格を行うことができます。
- **チャネル** - 新しいチャネルを追加したり既存のチャネルを削除したりすることができます。  既定の「全般」チャネルを削除することはできません。作成したチャネルについては、チャネル名のみを編集することができます。説明を編集することはできません。
- **チーム名**
- **チームの説明**
- **チームのプライバシー** - パブリックまたはプライベート
- **チームの分類** - 自分の Office 365 グループの分類に基づきます
- **チーム メンバーの設定** - チーム メンバーの設定を選択します

## <a name="other-supported-changes-to-teams"></a>その他サポートされているチームへの変更

- **削除** - チームを削除すると、チームとそれに対応する Office 365 グループが論理的に削除されます。  誤って削除したチームを復元するには、「[削除された Office 365 グループの復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)」の手順に従ってください。
- **アーカイブ** - チームをアーカイブすると、チームは Microsoft Teams 内で読み取り専用モードに切り替わります。  管理者は組織の代理として、管理ポータルを通じてチームをアーカイブしたりアーカイブを解除したりできます。


チームに対して行う変更はログに記録されます。 グループ設定 (名前、説明、写真、プライバシー、分類、またはチーム メンバー) を変更する場合、これらの変更は監査パイプラインを通して自分自身によるものとされます。 Teams 固有の設定に対するアクションを実行している場合、自分による変更は、チームの全般チャネル内で記録され、自分自身によるものとされます。

## <a name="troubleshooting"></a>トラブルシューティング

**問題: チームがチームの概要グリッドに表示されません。**

Microsoft Teams 管理センターを開いた際に、[**チーム**] オプションの下で、チームの概要グリッドの一覧に一部のチームが表示されない問題。

**原因**: この問題は、チームがシステムによって不適切にプロファイルされた場合 (またはまだプロファイルされていない場合) に発生し、チームを認識するためのプロパティが見つからない状態を作ります。

**解決方法: MS Graph でプロパティを適切な値に手動で設定します。**

該当する GroupId に対するクエリで **{groupid}** を置き換えます。{groupid} は、Exchange Online powershell で "**ExternalDirectoryObjectId**" 属性として **"[Get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** コマンドレットを使用して取得できます。　

1. [Graph エクスプローラー](https://developer.microsoft.com/en-us/graph/graph-explorer)にアクセスします

2. 左側のメニューで、Graph エクスプ ローラーにサインインします。

3. クエリの行を次のように変更します: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}

4. リクエストの本文に、次の値を追加します: {"resourceProvisioningOptions": ["Team"]}

5. 右上のクエリを実行します。

6. Microsoft Teams 管理センターのチームの概要のページで、チームが正しく表示されていることを確認します。


## <a name="learn-more"></a>詳細情報

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Microsoft Teams の管理者ロール](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

