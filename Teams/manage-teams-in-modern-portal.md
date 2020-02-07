---
title: Microsoft Teams 管理センターでチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Microsoft Teams の管理センターで自分のチームの表示や更新を行う方法を説明します。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d07c9c1f19b86b3b95a597a52290acb2fdaa80cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836269"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでチームを管理する
==========================================

## <a name="overview"></a>概要

この記事では、Microsoft Teams 管理センターの Teams の管理ツールの概要について説明します。

管理者として、組織が共同作業のためにセットアップしたチームを表示または更新する必要がある場合、または ownerless teams の所有者を割り当てるなどの修復アクションを実行する必要がある場合があります。 組織のチームは、Microsoft Teams PowerShell モジュールと Microsoft Teams 管理センターの両方から管理することができます。 これらの 2 つのツールセットを使用した完全な管理機能については、次の役割の 1 つが割り当てられることを確認する必要があります。

- グローバル管理者
- Teams サービス管理者

Teams での管理者の役割の詳細については、「[ Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。また、PowerShell コマンドレットを使用してチームを管理する方法の詳細については、「[Microsoft Teams コマンドレットのリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」をご覧ください。



## <a name="teams-overview-grid"></a>Teams の概要グリッド

チームの管理ツールは、Microsoft Teams 管理センターの [**Teams**] ノードの下にあります。 (管理センターでは、[**Teams**] > [**Manage teams (チームの管理)**] を選択します。)各チームは Offfice 365 グループによって支えられていて、このノードは自分の組織内で Microsoft Teams に対応しているグループの表示を提供します。

![チームの概要グリッドのスクリーンショット](media/manage-teams-in-modern-portal-grid.png)  

このグリッドには、次のプロパティが表示されます。

- **チーム名**
- **チャネル** - 既定の全般チャネルを含む、チーム内のすべてのチャネルの数。
- **チームメンバー** -テナントの所有者、ゲスト、メンバーを含む、ユーザーの合計数です。
- **所有者** - このチームの所有者の数。
- **ゲスト** - このチームのメンバーである、Azure Active Directory B2B ゲスト ユーザーの数。
- **プライバシー** - 基となる Office 365 グループの可視性/AccessType。
- **状態** - このチームの状態がアーカイブ済みかアクティブか。 チームのアーカイブの詳細について[は、「チームをアーカイブまたは復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。
- [ **Description** ]-バッキング Office 365 グループの説明。
- **分類** - 基となる Office 365 の グループに割り当てられている分類 (組織内で使用されている場合)。 分類の詳細については、「[組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)」を参照してください。
- **Groupid** -バッキング Office 365 グループの固有の groupid。

> [!NOTE]
> グリッドにこれらのプロパティがすべて表示されない場合は、[**列の編集**] アイコンをクリックします。 [**列の編集**] ウィンドウで、トグルを使用して、グリッドの列のオンとオフを切り替えることができます。 完了したら、[**適用**] をクリックします。

### <a name="add"></a>追加

新しいチームを追加するには、[**追加**] をクリックします。 [**新しいチームの追加**] ウィンドウで、チームに名前と説明を入力し、プライベートチームとパブリックチームのどちらにするかを設定し、分類を設定します。

### <a name="edit"></a>編集

グループおよびチーム固有の設定を編集するには、チーム名の左側をクリックしてチームを選択し、[**編集**] を選択します。

### <a name="archive"></a>アーカイブ

チームをアーカイブすることができます。 チームをアーカイブすると、チームはチーム内で読み取り専用モードになります。 管理センターでは、管理者として、組織の代理としてチームのアーカイブやアーカイブの解除を行うことができます。 

### <a name="delete"></a>削除

チームを削除すると、チームと対応する Office 365 グループのソフト削除となります。 誤って削除されたチームを復元するには、「[削除された Office 365 グループを復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)する」の手順に従います。

### <a name="search"></a>検索

検索では現在「Begins with (次で始まる)」文字列をサポートされていて、[**Team name (チーム名)**] フィールドの検索を行います。

## <a name="team-profile"></a>チーム プロフィール

チーム名をクリックすると、チームのメインの概要グリッドからチームプロファイルページに移動できます。 チームプロファイルページには、チーム (およびそのバッキング Office 365 グループ) に属しているメンバー、所有者、ゲスト、およびチームのチャネルと設定が表示されます。 チーム プロフィール ページから、次の操作を行うことができます。

- メンバーおよび所有者の追加または削除。
- チャネルを追加または削除する (一般的なチャネルは削除できないことに注意してください)。
- チームとグループの設定を変更します。
 
![チームプロファイルの例のスクリーンショット](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>チームに対する変更

チームのプロファイルページで、チームの次の要素を変更することができます。

- **メンバー** -メンバーの追加または削除、所有者のレベル上げまたはレベル下げを行います。
- **チャネル**-新しいチャネルを追加し、既存のチャネルを編集または削除します。 既定の [全般] チャネルは削除できないことに注意してください。
- **チーム名**
- **説明**
- [**プライバシー** -チームが公開または非公開のどちらであるかを設定します。
- **分類**-これは、Office 365 グループの分類によってサポートされます。 [**社外秘**]、[**機密性の高い**]、または **[標準**] を選びます。
- [**スレッドの設定**]-送信されたメッセージをメンバーが編集および削除できるかどうかを設定します。
- [**チャネルの設定**]-メンバーが新しいチャネルを作成したり、既存のチャネルを編集したりできるかどうかを設定します。また、タブ、コネクタ、アプリを追加、編集、削除することもできます。

チームに対して行う変更はログに記録されます。 グループ設定 (名前、説明、写真、プライバシー、分類、またはチームメンバーの変更) を変更する場合、変更は監査パイプラインによって表示されます。 チーム固有の設定に対して操作を実行している場合、変更はチームの [全般] チャネルで管理され、自分に帰属しています。

## <a name="troubleshooting"></a>トラブルシューティング

**問題: チームの概要グリッドでチームが見つからない**

チームの概要グリッドのチームの一覧に一部のチームが表示されない。

**原因**: この問題は、チームがシステムによって不適切にプロファイルされた場合 (またはまだプロファイルされていない場合) に発生し、チームを認識するためのプロパティが見つからない状態を作ります。

**解決方法: MS Graph でプロパティを適切な値に手動で設定します。**

該当する GroupId に対するクエリで **{groupid}** を置き換えます。{groupid} は、Exchange Online powershell で "**ExternalDirectoryObjectId**" 属性として **"[Get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** コマンドレットを使用して取得できます。　

1. Access [Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)。

2. 左側のメニューで、[Graph エクスプローラー] にサインインします。

3. クエリ行を次のように変更します。 https://graph.microsoft.com/v1.0/groups/{groupid}[PATCH > v 1.0 > を選びます。

4. 要求本文に次の値を追加します: {"Resourceてオプション": ["Team"]}

5. 右上のクエリを実行します。

6. [Microsoft Teams 管理センター-チームの概要」でチームが正しく表示されることを確認します。

## <a name="learn-more"></a>詳細情報

- [Teams コマンドレットリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [チーム管理者ロールを使用してチームを管理する](using-admin-roles.md)
- [Teams でのライフサイクル管理を計画する](plan-teams-lifecycle.md)
