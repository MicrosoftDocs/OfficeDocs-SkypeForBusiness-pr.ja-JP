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
ms.openlocfilehash: 30913e67c80f5f5e8c04ddf5d7855dcf25536834
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992907"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Microsoft Teamsでチームをアーカイブまたは削除する
===========================================

時間の経過と共に、Microsoft Teams で作成されたチームが使用できなくなったり、プロジェクトの終了時にチームをアーカイブまたは削除したりする場合があります。 Microsoft Teams の管理者である場合は、この記事に示す手順に従って、不要になったチームをアーカイブまたは削除します。

チームをアーカイブすると、そのチームのすべてのアクティビティが停止します。 チームをアーカイブすると、チーム内のプライベートチャネルと、関連付けられたサイトコレクションもアーカイブされます。  ただし、メンバーを追加または削除したり、ロールを更新したりすることはできますが、標準チャネル、プライベートチャネル、ファイル、チャットで、すべてのチームアクティビティを表示できます。

チームを削除すると、標準チャネルとプライベートチャネル (および関連付けられたサイトコレクション) でのチームアクティビティ、ファイル、チャットも削除されます。

> [!IMPORTANT]
> アーカイブされたチームを再アクティブ化することはできますが、削除されたチームを直接復元することはできません。 チームを最初にアーカイブし、チームが不要になったことを確認するまで、削除を延期することを検討してください。

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

チームに関連付けられている Office 365 グループを復元して、削除されたチームを復元するには、次の手順を実行します。 チームの Office 365 グループを復元すると、タブ、標準チャネル、プライベートチャネル、関連付けられたサイトコレクションなどのチームコンテンツが復元されます。

既定では、削除された Office 365 グループは30日間保持されます。 この30日間の期間は、グループを復元できるため、"ソフト削除" と呼ばれます。 詳細については、「[削除済みの Office 365 グループを復元](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)する」を参照してください。

### <a name="install-the-azureadpreview-module"></a>AzureADPreview モジュールをインストールする

1. 管理者として Windows PowerShell を開きます。
2. 以前のバージョンの AzureADPreview モジュールがインストールされているか、AzureAD モジュールがインストールされている場合は、次のいずれかを実行してアンインストールします。

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. 次を実行して、最新バージョンの AzureADPreview モジュールをインストールします。

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>削除された Office 365 グループを復元する

1. Azure AD に接続するには、次の操作を実行します。
    ```PowerShell
    Connect-AzureAD
    ```
    メッセージが表示されたら、管理者アカウントとパスワードを使用してサインインします。  
2. 次を実行すると、30日の保持期間内のすべてのソフト削除された Office 365 グループの一覧が表示されます。 多数のグループがある場合は、 **-All $True**パラメーターを使用します。
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. 復元するグループを見つけて、Id をメモします。
4. グループを復元するには、次を実行します。 [Id] はグループ Id です。
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  グループが正常に復元されたことを確認するには、次を実行します。 [Id] はグループ Id です。
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    復元プロセスが完了するまでに最大で24時間かかる場合があります。その後、タブやチャネルなど、チームに関連付けられたチームとコンテンツが Teams に表示されます。
