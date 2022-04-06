---
title: カスタム コネクタMicrosoft 365使用する
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.openlocfilehash: 7fef0b28d9663cdb472f4daf79076c2d4eefcd66
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2022
ms.locfileid: "64642981"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Microsoft 365コネクタとカスタム コネクタを使用Microsoft Teams

チームを最新の状態に保つために、コネクタは頻繁に使用されるコンテンツとサービスの更新をチャネルに直接Teamsします。 コネクタを使用すると、Teamsユーザーは、Trello、Wunderlist、GitHub、Azure DevOps Services などの一般的なサービスから更新プログラムを受け取Azure DevOps Services。 更新プログラムは、チームのチャット ストリームに直接投稿されます。

Microsoft 365コネクタは、Microsoft Teams グループと Microsoft 365 グループの両方で使用され、すべてのメンバーが同期を取り合い、関連する情報をすばやく受信しやすくなります。 両方Microsoft TeamsとExchange同じコネクタ モデルを使用します。これにより、両方のプラットフォーム内で同じコネクタを使用できます。 ただし、チームが依存している Microsoft 365 グループのコネクタを無効にすると、そのチームのコネクタを作成する機能も無効にされるので、ご確認ください。

チームのメンバーは誰でも、チームのアクセス許可が許可され、すべてのチーム メンバーにそのサービスからのアクティビティが通知される場合、人気のあるクラウド サービスにコネクタを接続できます。 コネクタは、コネクタを最初にセットアップしたメンバーが離した後も引き続き機能します。 追加または削除するアクセス許可を持つチーム メンバーは、他のメンバーによるコネクタのセットアップを変更できます。

> [!NOTE]
> Government Cloud Community (GCC) 環境では、コネクタは既定で無効になっています。 これらのパラメーターを有効にするには、 または パラメーター `ConnectorsEnabled` を コマンドレット `ConnectorsEnabledForTeams` で `$true` に設定 `SetOrganizationConfig` します。 Connect [PowerShell にExchange Onlineします](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。

## <a name="add-a-connector-to-a-channel"></a>コネクタをチャネルに追加する

現時点では、デスクトップクライアントと Web クライアントを使用Microsoft Teamsコネクタを追加できます。 ただし、これらのコネクタによって投稿された情報は、モバイルを含むすべての **クライアントで** 表示できます。

1. コネクタをチャネルに追加するには、チャネル名の右側にある省略記号 **(...** ) をクリックし、[コネクタ] **をクリックします**。

    > [!div class="mx-imgBorder"]
    > ![[コネクタ] Teamsを選択したインターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 使用可能なさまざまなコネクタから選択し、[追加] をクリック **します**。

    > [!div class="mx-imgBorder"]
    > ![使用可能なコネクタを示す [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。

    > [!div class="mx-imgBorder"]
    > ![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. コネクタによって提供されるデータはチャネルに自動的に投稿されます。

    > [!div class="mx-imgBorder"]
    > ![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete --->

> [!IMPORTANT]
> **コネクタ URL の更新通知**
>
> 新Teamsコネクタは、セキュリティを強化するために新しい URL に移行しています。 この移行の過程で、新しい URL を使用するように構成されたコネクタを更新する特定の通知を受信します。 コネクタ サービスの中断を防ぐために、コネクタを直ちに更新強く推奨します。 URL を更新するには、次の手順に従う必要があります。
>
> 1. コネクタの構成ページで、更新する必要がある接続の [管理] ボタンの下に "注意が必要です" というメッセージが表示されます。
> !["要注意" メッセージのスクリーンショット。](media/Teams_Attention_Required_message.png)
> 2. 受信 webhook コネクタの場合、[URL の更新] を選択し、新しく生成された webhook URL を使用するだけで、接続を再作成できます。
> ![[URL の更新] ボタンのスクリーンショット。](media/Teams_update_URL_button.png)
> 3. 他の種類のコネクタの場合、ユーザーはコネクタを削除し、コネクタの構成を再作成する必要があります。
> 4. URL が正常に更新されると、"URL は最新の情報です" というメッセージが表示されます。
> !["URL is up-to-date" メッセージのスクリーンショット。](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>関連項目

* [カスタム コネクタと webhook を構築する](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
