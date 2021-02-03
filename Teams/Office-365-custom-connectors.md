---
title: Microsoft 365 とカスタム コネクタを使用する
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
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076419"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Microsoft Teams で Microsoft 365 とカスタム コネクタを使用する
=======================================================

コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に保つ。 コネクタを使用すると、Microsoft Teams ユーザーは、チームのチャット ストリーム内で Trello、Wunderlist、GitHub、Azure DevOps Services などの一般的なサービスから更新プログラムを受信できます。

チームのアクセス許可が許可されている場合、チームのメンバーは誰でも、人気のあるクラウド サービスにコネクタを接続できます。また、すべてのチーム メンバーに、そのサービスからのアクティビティが通知されます。 コネクタを最初にセットアップしたメンバーが残った後でも、コネクタは引き続き機能します。 追加\削除する権限を持つチーム メンバーは、他のメンバーによるコネクタのセットアップを変更できます。

Microsoft 365 コネクタは、Microsoft Teams と Microsoft 365 グループの両方で使用することができるので、すべてのメンバーの同期を簡単に行い、関連する情報をすばやく受信できます。 Microsoft Teams と Exchange の両方で同じコネクタ モデルが使用され、両方のプラットフォーム内で同じコネクタを使用できます。 ただし、チームが依存している Microsoft 365 グループのコネクタを無効にすると、そのチームのコネクタを作成する機能も無効にすることもできます。

<a name="add-a-connector-to-a-channel"></a>チャネルにコネクタを追加する
----------------------------

現在、Microsoft Teams デスクトップおよび Web クライアントを使用してコネクタを追加できます。 ただし、これらのコネクタによって投稿された情報は、モバイルを含むすべての **クライアントで** 表示できます。

1. チャネルにコネクタを追加するには、チャネル名の右側にある省略記号 **(...)** をクリックし、[コネクタ] を **クリックします**。

    > [!div class="mx-imgBorder"]
    > ![[コネクタ] オプションが選択された Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 使用可能なさまざまなコネクタから選び、[追加] をクリック **します**。

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
> **コネクタの URL 更新通知**
>
> Teams コネクタは、セキュリティを強化するために新しい URL に移行しています。 この移行中に、新しい URL を使用するように構成されたコネクタを更新する特定の通知を受け取る。 コネクタ サービスが中断されるのを防ぐために、コネクタを直ちに更新してください。 URL を更新するには、次の手順に従う必要があります。
> 1. コネクタの構成ページで、更新する必要がある接続の [管理] ボタンの下に "注意が必要です" というメッセージが表示されます。
> !["要注意" メッセージのスクリーンショット。](media/Teams_Attention_Required_message.png)
> 2. 受信 Webhook コネクタの場合は、[URL の更新]を選択し、新しく生成された Webhook URL を使用するだけで、接続を再作成できます。
> ![[URL の更新] ボタンのスクリーンショット。](media/Teams_update_URL_button.png)
> 3. その他の種類のコネクタの場合、ユーザーはコネクタを削除し、コネクタの構成を再作成する必要があります。
> 4. URL が正常に更新されると、"URL は最新です" というメッセージが表示されます。
> !["URL は最新の情報です" というメッセージのスクリーンショット。](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>カスタム コネクタを開発する
----------------------------

また、カスタム コネクタだけでなく、受信および送信 Webhook を作成することもできます。 詳細については、「[開発者向けドキュメント](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください:
