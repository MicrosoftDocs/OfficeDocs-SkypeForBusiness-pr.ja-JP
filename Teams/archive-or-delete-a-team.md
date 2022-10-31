---
title: Microsoft Teams でチームをアーカイブまたは削除する
manager: serdars
ms.author: mikeplum
author: MikePlumleyMSFT
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: この記事では、Microsoft Teams でチームをアーカイブまたは完全に削除する方法について説明します。
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
ms.openlocfilehash: e9178bb793f25d9c052041432c20af4be8fb4033
ms.sourcegitcommit: 57616ad45eaa8be7f78dd0126d324c8777c5a367
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2022
ms.locfileid: "68792786"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>Microsoft Teams でチームをアーカイブまたは削除する

時間の経過と共に、Microsoft Teams で作成したチームを使用しなくなることがあります。あるいは、プロジェクトの終了時にチームをアーカイブまたは削除したい場合もあります。 Microsoft Teams の管理者は、この記事に示す手順に従って、不要になったチームをアーカイブまたは削除できます。 (チーム所有者の場合は、 [チームをアーカイブ](https://support.microsoft.com/office/dc161cfd-b328-440f-974b-5da5bd98b5a7)することもできます)。

チームをアーカイブすると、そのチームのすべてのアクティビティが停止します。 チームをアーカイブすると、そのチーム内のプライベート チャネルと、関連付けられたサイト コレクションもアーカイブされます。  ただし、メンバーを追加または削除したり、ロールを更新したりすることはできます。また、標準およびプライベートのチャネル、ファイル、チャットでの、そのチームのすべてのアクティビティを表示することも可能です。

チームを削除すると、標準およびプライベートのチャネル (および関連するサイト コレクション)、ファイル、チャットでのチーム アクティビティも削除されます。

> [!IMPORTANT]
> アーカイブされたチームを再アクティブ化することはできますが、削除されたチームを直接復元することはできません。 チームをまずアーカイブし、チームが不要になったことが確実になるまで削除を延期することを検討してください。

## <a name="archive-a-team"></a>チームをアーカイブする

チームをアーカイブするには、次の手順に従います。 これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. 管理センターで、[**Teams**] を選択します。
2. チーム名をクリックして、チームを選びます。
3. Select **Archive**. The following message will appear.

    ![Teams のアーカイブ メッセージのスクリーンショット。](media/teams-archive-message.png)

4. ユーザーが SharePoint サイトとチームに関連付けられている Wiki タブで内容を編集できないようにするには、[**SharePoint サイトをチーム メンバーに対して読み取り専用にする**] を選択します。 (チームの所有者は引き続きこの内容を編集できます。)
5. [**アーカイブ**] を選択して、チームをアーカイブします。 チームの状態が **[アーカイブ済み**] に変更され、チーム リストの下部にある **[非表示] チーム** 内で一時的に使用できるようになり、アーカイブされた状態を表す小さなアイコンが横に追加されます。 **非表示のチーム** から削除されると、[**アーカイブ** 済み] の [**チームの管理**] ビューで使用できるようになります。 アーカイブされたチームのコンテンツを表示および検索するには、[アーカイブ済み **] リストでその** 名前を選択します。

## <a name="make-an-archived-team-active"></a>アーカイブしたチームをアクティブにする

次の手順に従って、アーカイブされているチームを再度アクティブにします。

1. 管理センターで、[**Teams**] を選択します。
2. チーム名をクリックして、チームを選びます。
3. **[復元]** を選択します。 チームの状態が **[アクティブ]** に変わります。 **チーム** 内に自動的に戻されるわけではありません。

## <a name="delete-a-team"></a>チームを削除する

If the team will not be required in the future, then you can delete it rather than archiving it. Follow these steps to delete a team.

1. 管理センターで、[**Teams**] を選択します。
2. チーム名をクリックして、チームを選びます。
3. Select **Delete**. A confirmation message will appear.
4. チームを完全に削除するには、[**削除**] を選択します。

## <a name="restore-a-deleted-team"></a>削除したチームを復元する

チームに関連付けられている Office 365 グループを復元して、削除したチームを復元するには、次の手順を実行します。 チームの Microsoft 365 グループを復元すると、タブ、標準チャネル、プライベート チャネル、それらに関連付けられたサイト コレクションなどのチーム コンテンツが復元されます。

既定では、削除された Office 365 グループは 30 日間保持されます。 この 30 日の期間は、グループを復元できるため、「ソフト削除」と呼ばれます。 詳細については、「[削除済みのグループを復元する](/microsoft-365/admin/create-groups/restore-deleted-group)」を参照してください。

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

1. 次を実行すると、30 日の保持期限内にあるすべてのソフト削除された Microsoft 365 グループの一覧が表示されます。 多数のグループがある場合は、**-All $True** パラメーターを使用します。

    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```

1. 復元するグループを見つけて、`Id` をメモします。
1. グループを復元するには、次のようにします。`[Id]` はグループ ID です。

    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```

1. グループが正常に復元されたことを確認するには、次を実行します。`[Id]` はグループ ID です。

    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    復元プロセスが完了するまで、最大で 24 時間かかる場合があります。その後、タブやチャネルなど、該当するチームに関連付けられたチームとコンテンツが Teams に表示されます。

## <a name="related-topics"></a>関連項目

- [チームをアーカイブまたは復元する](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

