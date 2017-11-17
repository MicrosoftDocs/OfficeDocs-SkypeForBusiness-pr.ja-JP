---
title: "Microsoft Teams で役割と権限を割り当てる | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9cc8a72cdabacb76638acb689c6622642c524c8e
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>Microsoft Teams で役割と権限を割り当てる
===============================================

Microsoft Teams には、**所有者**と**メンバー**の 2 つの役割があります。既定では、新しいチームを作成するユーザーに所有者の状態が付与されます。既存の Office 365 グループからチームを作成する場合は、そのグループの権限が継承されます。

所有者とメンバーの権限の違いを以下の表に示します。

|  |チーム所有者  |チーム メンバー  |
|---------|---------|---------|
|**チームの作成**     |はい        |いいえ         |
|**チームを抜ける**     |はい         |はい         |
|**チーム名/説明の編集**      |はい         |いいえ         |
|**チームの削除**      |はい         |いいえ         |
|**チャネルの追加**      |はい         |はい*         |
|**チャネル名/説明の編集**      |はい         |はい*         |
|**チャネルの削除**      |はい         |はい*         |
|**メンバーの追加**      |はい**         |いいえ         |
|**タブの追加**      |はい         |はい*         |
|**コネクタの追加**      |はい         |はい*         |
|**ボットの追加**      |はい         |はい*         |
\* 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。

\*\*チームへのメンバーの追加後、所有者はメンバーを所有者の状態に昇格させることもできます。また、所有者は自分のステータスをメンバーに降格させることもできます。

| | |
|---------|---------|
|![電球アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br>注意     |所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。1 つのチームあたりの所有者の最大数は 10 人です。         |

<a name="permissions-to-create-teams"></a>チームを作成するための権限
---------------------------

既定により、Exchange Online のメールボックスを持つすべてのユーザーは Office 365 グループを作成するための権限を持つため、Microsoft Teams でもチームを作成することができます。作成と管理の権限を特定のユーザーに付与することで、新規チームの作成、すなわち新規 Office 365 グループの作成をより厳しく制御、制限することができます。

組織でこの制限を実施する場合は、そのために必要な以下のタスクを参照してください。

1.  Office 365 グループを作成するための権限を他のユーザーに付与するセキュリティ グループ (SG) を特定または作成します。

    a.  **アクション:** Office 365 でセキュリティ グループを設定し、Office 365 グループを作成できるユーザーを追加します。

    b.  詳しくは、「[作成、編集、または Office 365 管理センターでセキュリティ グループを削除します。](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)」をご覧ください。

2.  会社全体で、グループを作成するユーザーが制御されていることを確認します。

    a.  **アクション:** 次の PowerShell スクリプトを実行し、UsersPermissiontoCreateGroupsEnabled パラメーターが **True** であることを確認します。

    Connect-MsolService

    Get-MsolCompanyInformation

    b.  True でない場合は、Set-MsolCompanySettings コマンドレットを実行して **True に設定**します。
Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True

    c. 詳細については、「[Office 365 グループの作成を管理する](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)」をご覧ください。

3.  特定したセキュリティ グループのみにグループ作成の権限を許可するように Office 365 グループの設定を構成します。

    a.  **アクション:** グループ作成の権限を割り当てるグループの構成を含むグループ設定オブジェクトを作成します。 

    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "false"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings

    b. 詳細については、「[Manage Office 365 Group Creation (Office 365 グループの作成を管理する)](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)」をご覧ください。


||||
|---------|---------|---------|
| ![判断ポイント アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |判断ポイント         |Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?         |
| ![次のステップ アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |次のステップ         |チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。         |
