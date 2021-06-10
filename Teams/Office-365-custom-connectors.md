---
title: カスタム Microsoft 365を使用する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: コネクタにより、頻繁に使用するサービスからコンテンツと更新内容がチャネルに直接配信されるため、チームは最新の状態に保たれます。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77b1c99847ca35de51af5e062593a29c18e98999
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855796"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Microsoft 365コネクタとカスタム コネクタを使用Microsoft Teams

コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に保つ。 コネクタを使用すると、Microsoft Teams ユーザーは、チームのチャット ストリーム内で Trello、Wunderlist、GitHub、Azure DevOps Services などの一般的なサービスから更新プログラムを受信できます。

チームのメンバーは誰でも、チームのアクセス許可が許可されている場合に、人気のあるクラウド サービスにコネクタを接続できます。また、すべてのチーム メンバーには、そのサービスからのアクティビティが通知されます。 コネクタは、コネクタを最初にセットアップしたメンバーが離した後でも引き続き機能します。 add\remove アクセス許可を持つチーム メンバーは、他のメンバーによるコネクタのセットアップを変更できます。

Microsoft 365コネクタは、Microsoft Teams グループと Microsoft 365 グループの両方で使用することができるので、すべてのメンバーが同期を取り合い、関連する情報をすばやく受信しやすくなります。 両方Microsoft TeamsとExchange同じコネクタ モデルを使用します。これにより、両方のプラットフォーム内で同じコネクタを使用できます。 ただし、チームが依存している Microsoft 365 グループのコネクタを無効にすると、そのチーム用のコネクタを作成する機能も無効にされます。

> [!NOTE]
> コネクタは、既定では、一部の環境GCC無効になっています。 有効にする必要がある場合は、ConnectorsEnabled または ConnectorsEnabledForTeams パラメーターを [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) コマンドレットを使用$true に設定します。 以前は[、PowerShell に接続Exchange Online必要があります](/powershell/exchange/connect-to-exchange-online-powershell)。

> [!NOTE]
> Government Cloud Community (GCC) 環境では、コネクタは既定で無効になっています。 有効にする必要がある場合は、ConnectorsEnabled または ConnectorsEnabledForTeams パラメーターを [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) コマンドレット$trueに設定します。 以前は、PowerShell に接続するExchange Online[必要がありました](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。

## <a name="add-a-connector-to-a-channel"></a>コネクタをチャネルに追加する

現時点では、デスクトップクライアントと Web クライアントを使用Microsoft Teamsコネクタを追加できます。 ただし、これらのコネクタによって投稿された情報は、モバイルを含むすべての **クライアントで** 表示できます。

1. チャネルにコネクタを追加するには、チャネル名の右側にある省略記号 **(...)** をクリックし、[コネクタ] を **クリックします**。

    > [!div class="mx-imgBorder"]
    > ![[コネクタ] オプションTeamsインターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. さまざまな使用可能なコネクタから選択し、[追加] をクリック **します**。

    > [!div class="mx-imgBorder"]
    > ![使用可能なコネクタを示す [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。

    > [!div class="mx-imgBorder"]
    > ![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. コネクタによって提供されるデータはチャネルに自動的に投稿されます。

    > [!div class="mx-imgBorder"]
    > ![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **コネクタ URL の更新通知**
>
> 新Teams、セキュリティを強化するために新しい URL に移行しています。 この移行の過程で、新しい URL を使用するように構成されたコネクタを更新する特定の通知が表示されます。 コネクタ サービスの中断を防ぐために、コネクタを直ちに更新強く推奨します。 URL を更新するには、次の手順に従う必要があります。
> 1. コネクタの構成ページで、更新する必要がある接続の [管理] ボタンの下に "注意が必要です" というメッセージが表示されます。
> !["要注意" メッセージのスクリーンショット。](media/Teams_Attention_Required_message.png)
> 2. 受信 webhook コネクタの場合、[URL の更新] を選択し、新しく生成された webhook URL を使用するだけで、接続を再作成できます。
> ![[URL の更新] ボタンのスクリーンショット。](media/Teams_update_URL_button.png)
> 3. 他の種類のコネクタの場合、ユーザーはコネクタを削除し、コネクタの構成を再作成する必要があります。
> 4. URL が正常に更新されると、"URL は最新の情報です" というメッセージが表示されます。
> !["URL is up-to-date" メッセージのスクリーンショット。](media/Teams_URL_up_to_date.png)


## <a name="develop-custom-connectors"></a>カスタム コネクタを開発する


受信および送信 Webhook だけでなく、カスタム コネクタを構築することもできます。 詳細については、「[開発者向けドキュメント](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください:
