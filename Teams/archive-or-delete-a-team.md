---
title: Microsoft Teams でチームをアーカイブまたは削除する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: この記事では、チームをアーカイブまたは完全に削除する方法についてMicrosoft Teams。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c310794d439af79e53618d9b6e93e567c652cf47
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766640"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>Microsoft Teams でチームをアーカイブまたは削除する

時間の経過と共に、Microsoft Teams で作成したチームを使用しなくなることがあります。あるいは、プロジェクトの終了時にチームをアーカイブまたは削除したい場合もあります。 Microsoft Teams の管理者は、この記事に示す手順に従って、不要になったチームをアーカイブまたは削除できます。

チームをアーカイブすると、そのチームのすべてのアクティビティが停止します。 チームをアーカイブすると、そのチーム内のプライベート チャネルと、関連付けられたサイト コレクションもアーカイブされます。  ただし、メンバーを追加または削除したり、ロールを更新したりすることはできます。また、標準およびプライベートのチャネル、ファイル、チャットでの、そのチームのすべてのアクティビティを表示することも可能です。

チームを削除すると、標準チャネルとプライベート チャネル (および関連付けられているサイト コレクション)、ファイル、チャットのチーム アクティビティも削除されます。

> [!IMPORTANT]
> アーカイブされたチームを再アクティブ化することはできますが、削除されたチームを直接復元することはできません。 チームをまずアーカイブし、チームが不要になったことが確実になるまで削除を延期することを検討してください。

## <a name="archive-a-team"></a>チームをアーカイブする

チームをアーカイブするには、次の手順に従います。 これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. 管理センターで、[Teams]**を選択します**。
2. チーム名をクリックして、チームを選びます。
3. [**アーカイブ**] を選びます。 次のメッセージが表示されます。

    ![アーカイブ メッセージTeamsスクリーンショット。](media/teams-archive-message.png)

4. ユーザーがチームに関連付けられている SharePoint サイトと Wiki タブでコンテンツを編集するのを防ぐには、[チーム メンバーの SharePoint サイトを読み取り専用にする]**を選択します**。 (Teamsは引き続きこのコンテンツを編集できます)。
5. [**アーカイブ**] を選択して、チームをアーカイブします。 チームの状態は [アーカイブ済み] に変わります。チームリストの下部にある非表示のチーム内に移動され、アーカイブされた状態を表す小さなアイコンが横に追加されます。

## <a name="make-an-archived-team-active"></a>アーカイブしたチームをアクティブにする

次の手順に従って、アーカイブされているチームを再度アクティブにします。

1. 管理センターで、[Teams]**を選択します**。
2. チーム名をクリックして、チームを選びます。
3. [復元] **を選択します**。 チームの状態が [**アクティブ**] に変わります。 チーム内では自動的には戻されません。 

## <a name="delete-a-team"></a>チームを削除する

今後チームが必要にならない場合、アーカイブではなく、削除することができます。 チームを削除するには、次の手順に従います。

1.  管理センターで、[Teams]**を選択します**。
2.  チーム名をクリックして、チームを選びます。
3.  [**削除**] を選びます。 確認メッセージが表示されます。
4.  チームを完全に削除するには、[**削除**] を選択します。

## <a name="restore-a-deleted-team"></a>削除したチームを復元する

次の手順に従って、チームに関連付けられているMicrosoft 365グループを復元して、削除されたチームを復元します。 チームの Microsoft 365グループを復元すると、タブ、標準チャネル、プライベート チャネル、関連するサイト コレクションなどのチーム コンテンツが復元されます。

既定では、削除されたMicrosoft 365は 30 日間保持されます。 この 30 日の期間は、グループを復元できるため、「ソフト削除」と呼ばれます。 詳細については、「削除されたグループ [を復元する」を参照してください](/microsoft-365/admin/create-groups/restore-deleted-group)。

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

### <a name="restore-the-deleted-microsoft-365-group"></a>削除したグループをMicrosoft 365する

1. Azure AD に接続するには、次の操作を実行します。
    ```PowerShell
    Connect-AzureAD
    ```
    メッセージが表示されたら、管理者アカウントとパスワードを使用してサイン インします。  
2. 次のコマンドを実行して、まだ 30 日間のリテンション期間Microsoft 365削除されたグループの一覧を表示します。 グループが **多数の場合$True** -All パラメーターを使用します。
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. 復元するグループを見つけて、 をメモします `Id` 。
4. 次のコマンドを実行してグループを復元します。 `[Id]` ここで、 はグループ ID です。
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  次のコマンドを実行して、グループが正常に復元されたことを確認します。ここで `[Id]` 、 はグループ ID です。
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    復元プロセスが完了するまで、最大で 24 時間かかる場合があります。その後、タブやチャネルなど、該当するチームに関連付けられたチームとコンテンツが Teams に表示されます。
    
## <a name="related-topics"></a>関連項目

- [チームをアーカイブまたは復元する](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 
