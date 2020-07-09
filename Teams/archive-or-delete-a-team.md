---
title: Microsoft Teams でチームをアーカイブまたは削除する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: この記事では、Microsoft Teams でチームをアーカイブする、または完全に削除する方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d3548ead35c63e2d34c47b340559c3174f1c895
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086193"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Microsoft Teams でチームをアーカイブまたは削除する
===========================================

時間の経過と共に、Microsoft Teams で作成したチームを使用しなくなることがあります。あるいは、プロジェクトの終了時にチームをアーカイブまたは削除したい場合もあります。 Microsoft Teams の管理者は、この記事に示す手順に従って、不要になったチームをアーカイブまたは削除できます。

チームをアーカイブすると、そのチームのすべてのアクティビティが停止します。 チームをアーカイブすると、そのチーム内のプライベート チャネルと、関連付けられたサイト コレクションもアーカイブされます。  ただし、メンバーを追加または削除したり、ロールを更新したりすることはできます。また、標準およびプライベートのチャネル、ファイル、チャットでの、そのチームのすべてのアクティビティを表示することも可能です。

チームを削除すると、標準およびプライベートのチャネル (および関連するサイト コレクション)、ファイル、チャットでのチーム アクティビティも削除されます。

> [!IMPORTANT]
> アーカイブされたチームを再アクティブ化することはできますが、削除されたチームを直接復元することはできません。 チームをまずアーカイブし、チームが不要になったことが確実になるまで削除を延期することを検討してください。

## <a name="archive-a-team"></a>チームをアーカイブする

チームをアーカイブするには、次の手順に従います。

1. の管理センターで <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 、[ **Teams**] を選択します。
2. チーム名をクリックして、チームを選びます。
3. [**アーカイブ**] を選びます。 次のメッセージが表示されます。

    ![Teams のアーカイブ メッセージのスクリーンショット](media/teams-archive-message.png)

4. チームに関連付けられている SharePoint サイトと Wiki タブのコンテンツをユーザーが編集できないようにするには、[**チームメンバーに対して sharepoint サイトを読み取り**専用にする] を選択します。 (チームの所有者は、このコンテンツを引き続き編集できます)。
5. [**アーカイブ**] を選択して、チームをアーカイブします。 チームの状態が [**アーカイブ済み**] に変わります。

## <a name="make-an-archived-team-active"></a>アーカイブしたチームをアクティブにする

次の手順に従って、アーカイブされているチームを再度アクティブにします。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>で、[**チーム**] を選択します。
2. チーム名をクリックして、チームを選びます。
3. [**アーカイブ解除**] を選択します。 チームの状態が [**アクティブ**] に変わります。

## <a name="delete-a-team"></a>チームを削除する

今後チームが必要にならない場合、アーカイブではなく、削除することができます。 チームを削除するには、次の手順に従います。

1.  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>で、[**チーム**] を選択します。
2.  チーム名をクリックして、チームを選びます。
3.  [**削除**] を選びます。 確認メッセージが表示されます。
4.  チームを完全に削除するには、[**削除**] を選択します。

## <a name="restore-a-deleted-team"></a>削除したチームを復元する

チームに関連付けられている Microsoft 365 グループを復元して、削除されたチームを復元するには、次の手順を実行します。 チームの Microsoft 365 グループを復元すると、タブ、標準チャネル、プライベートチャネル、関連付けられたサイトコレクションなどのチームコンテンツが復元されます。

既定では、削除された Microsoft 365 グループは30日間保持されます。 この 30 日の期間は、グループを復元できるため、「ソフト削除」と呼ばれます。 詳細については、「[削除したグループを復元](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)する」を参照してください。

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

### <a name="restore-the-deleted-microsoft-365-group"></a>削除された Microsoft 365 グループを復元する

1. Azure AD に接続するには、次の操作を実行します。
    ```PowerShell
    Connect-AzureAD
    ```
    メッセージが表示されたら、管理者アカウントとパスワードを使用してサイン インします。  
2. 次を実行して、30日の保持期間内のすべてのソフト削除された Microsoft 365 グループの一覧を表示します。 多数のグループがある場合は、**-All $True** パラメーターを使用します。
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. 復元するグループを見つけて、ID をメモします。
4. グループを復元するには、次のようにします。[Id] はグループ ID です。
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  グループが正常に復元されたことを確認するには、次を実行します。[Id] はグループ ID です。
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    復元プロセスが完了するまで、最大で 24 時間かかる場合があります。その後、タブやチャネルなど、該当するチームに関連付けられたチームとコンテンツが Teams に表示されます。
