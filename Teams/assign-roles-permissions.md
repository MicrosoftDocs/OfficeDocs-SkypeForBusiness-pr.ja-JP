---
title: "Microsoft チームの役割および権限を割り当てる"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "チームの所有者とメンバーの役割と権限を割り当てるチームを作成するのにはアクセス許可などの Microsoft チームにする方法を学習します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: ec15844064a88cf1e6aa8af9e510107e342dd369
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>Microsoft チームの役割および権限を割り当てる
===============================================

Microsoft チーム内では、2 つの役割があります:**所有者**と**メンバー**。既定では、新しいチームを作成したユーザーには、所有者のステータスが与えられます。既存の Office 365 グループからチームを作成すると、権限は継承されます。

次の表は、所有者とメンバーのアクセス許可の違いを示します。

|  |チームの所有者  |チーム メンバー  |
|---------|---------|---------|
|**チームを作成します。**     |○        |×         |
|**チームのままに**     |○         |○         |
|**チームの名前と説明を編集します。**      |○         |×         |
|**チームを削除します。**      |○         |×         |
|**チャンネルを追加します。**      |○         |○*         |
|**チャンネルの名前と説明を編集します。**      |○         |○*         |
|**チャンネルを削除します。**      |○         |○*         |
|**メンバーを追加します。**      |[はい] * *         |×         |
|**タブを追加します。**      |○         |○*         |
|**コネクタを追加します。**      |○         |○*         |
|**コンポーネントを追加します。**      |○         |○*         |
\*これらのアイテム オフにできますチーム レベル、所有者によって場合に、メンバーにをへのアクセスはありません。

\*\*チームにメンバーを追加した後所有者がメンバーを所有者のステータスに昇格させることもできます。所有者、メンバーに自分のステータスをレベル下げすることもできます。



> [!NOTE]
> 所有者は、チームの表示] オプションで他のメンバーの所有者を作成できます。チーム最大 100 所有者ことができます。チームの管理に役立てる少なくともいくつかの所有者にことをお勧めまた、唯一の所有者が組織を離れる場合は、親グループこれもできなくなります。親グループの詳細については、[親グループに新しい所有者を割り当てる](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)を参照してください。


<a name="permissions-to-create-teams"></a>チームを作成する権限
---------------------------

既定では、Exchange Online にメールボックスを持つすべてのユーザーは、Microsoft チーム内ではチームと Office 365 グループを作成するのには権限を持っています。密接に制御でき、グループの作成および複数ユーザーの管理権限を委任することで、新しいチームの作成と Office 365 の新しいグループの作成を制限することができます。

組織がこれに関心を持っていない場合のアウトラインは以下の手順、タスクが必要これを行う。

1.  特定するか、Office 365 グループを作成する権限を委任しているユーザーのセキュリティ グループ (ストレージ ・ グループ) を作成します。

    a:**アクション:** Office 365 グループを作成するユーザーを追加できるように、Office 365 でのセキュリティ グループを設定します。

    b. の詳細については、[作成、編集、または Office 365 管理センターでセキュリティ グループを削除する](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)を参照してください。

2.  グループを作成するユーザーの全社的コントロールが有効になっていることを確認します。

    a:**アクション:**次の PowerShell スクリプトを実行し、UsersPermissiontoCreateGroupsEnabled パラメーターを設定することを確認**True** 。

    接続 MsolService

    Get-msolcompanyinformation

    b. でない場合は true、実行 Set-msolcompanysettings コマンドレット**を True に設定**します。Set-msolcompanysettings-UsersPermissionToCreateGroupsEnabled $True

    c. の詳細についてを参照してください: [Office 365 グループの作成を管理](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)します。

3.  特定のセキュリティ グループのみがグループを作成する権限を許可する Office 365 のグループの設定を構成します。

    a:**アクション:**グループを作成するのには、委任されたアクセス許可を設定するグループの設定を含むグループの設定のオブジェクトを作成します。 

    接続 AzureAD

    $Template = get AzureADDirectorySettingTemplate-Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template します。CreateDirectorySetting()

    $setting ["EnableGroupCreation"] ="false"

    $setting ["GroupCreationAllowedGroupId"] ="&lt;グループを作成するグループのオブジェクト Id 許可 >"

    新しい-AzureADDirectorySetting-DirectorySetting $settings

    b. の詳細についてを参照してください: [Office 365 グループの作成を管理します。](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)


||||
|---------|---------|---------|
| ![判断するポイントをタップします。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |判断するポイント         |Microsoft チームのすべてのユーザーは (推奨) チームを作成できるようになりますか。         |
| ![次の手順をタップします。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |次のステップ         |Office 365 のグループを作成するには、チームを作成できるユーザーを制限する必要がある場合の既定の権限を変更します。         |
