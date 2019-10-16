---
title: Microsoft Teamsでチームをアーカイブまたは削除する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: チームをアーカイブする、または完全に削除する方法について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82ba160c1b2a36d67d67b69a0d7eb71bdde4c35f
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515916"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Microsoft Teamsでチームをアーカイブまたは削除する
===========================================

時間の経過と共に、Microsoft Teams で作成されたチームが使用できなくなったり、プロジェクトの終了時にチームをアーカイブまたは削除したりする場合があります。 Microsoft Teams の管理者である場合は、この記事に示す手順に従って、不要になったチームをアーカイブまたは削除します。 チームをアーカイブすると、そのチームのすべてのアクティビティは停止されますが、メンバーの追加や削除、ロールの更新を行うことはできますが、チャネル、ファイル、およびチャットでは、すべてのチームアクティビティを表示できます。 チームを削除すると、関連付けられたチャネル、ファイル、およびチャットでのチームアクティビティも削除されます。

> [!IMPORTANT]
> アーカイブされたチームを再アクティブ化することはできますが、削除されたチームを直接削除することはできません。 チームを最初にアーカイブし、チームが不要になったことを確認するまで、削除を延期することを検討してください。

## <a name="archive-a-team"></a>チームをアーカイブする

チームをアーカイブするには、次の手順に従います。

1. Microsoft Teams 管理センターで、[**チーム**] を選択します。
2. チーム名をクリックしてチームを選びます。
3. [**アーカイブ**] を選びます。 次のメッセージが表示されます。

    ![Teams アーカイブメッセージのスクリーンショット](media/teams-archive-message.png)

4. チームの SharePoint サイトを読み取り専用にする場合は、このチェックボックスをオンにします。
5. [**アーカイブ**] を選択して、チームをアーカイブします。 チームの状態は [**アーカイブ**済み」に変わります。

## <a name="make-an-archived-team-active"></a>アーカイブしたチームをアクティブにする

次の手順に従って、アーカイブされているチームを再度アクティブにします。

1. Microsoft Teams 管理センターで、[**チーム**] を選択します。
2. チーム名をクリックしてチームを選びます。
3. [**アーカイブ**解除] を選択します。 チームの状態が [**アクティブ**」に変わります。

## <a name="delete-a-team"></a>チームを削除する

今後チームが必要とならない場合は、アーカイブするのではなく、削除することができます。 チームを削除するには、次の手順に従います。

1.  Microsoft Teams 管理センターで、[**チーム**] を選択します。
2.  チーム名をクリックしてチームを選びます。
3.  [**削除**] を選びます。 確認メッセージが表示されます。
4.  チームを完全に削除するには、[**削除**] を選択します。

## <a name="restore-a-deleted-team"></a>削除されたチームを復元する

チームに関連付けられている Office 365 グループを復元して、削除されたチームを復元するには、次の手順を実行します。 既定では、削除された Office 365 グループは30日間保持されます。 この30日間の期間は、グループを復元できるため、"ソフト削除" と呼ばれます。 詳細については、「[削除済みの Office 365 グループを復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)する」を参照してください。

### <a name="install-the-azureadpreview-module"></a>AzureADPreview モジュールをインストールする

1. 管理者として Windows PowerShell を開きます。
2. 以前のバージョンの AzureADPreview モジュールがインストールされているか、AzureAD モジュールがインストールされている場合は、次のいずれかを実行してアンインストールします。

    ``` 
    Uninstall-Module AzureADPreview
    ```

    ```
    Uninstall-Module AzureAD
    ```
3. 次を実行して、最新バージョンの AzureADPreview モジュールをインストールします。

    ```
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>削除された Office 365 グループを復元する

1. Azure AD に接続するには、次の操作を実行します。
    ```
    Connect-AzureAD
    ```
    メッセージが表示されたら、管理者アカウントとパスワードを使用してサインインします。  
2. 次を実行すると、30日の保持期間内のすべてのソフト削除された Office 365 グループの一覧が表示されます。 多数のグループがある場合は、 **-All $True**パラメーターを使用します。
    ```
    Get-AzureADMSDeletedGroup
    ``` 
3. 復元するグループを見つけて、Id をメモします。
4. グループを復元するには、次を実行します。 [Id] はグループ Id です。
    ```
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  グループが正常に復元されたことを確認するには、次を実行します。 [Id] はグループ Id です。
    ```
    Get-AzureADGroup -ObjectId [Id]
    ```

    復元プロセスが完了するまでに最大で24時間かかる場合があります。その後、タブやチャネルなど、チームに関連付けられたチームとコンテンツが Teams に表示されます。
