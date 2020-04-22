---
title: Microsoft 365 とカスタムコネクタを使用する
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 33a407de891f0d988b1fb32988556059c6adc2e0
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778593"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Microsoft Teams で Microsoft 365 とカスタムコネクタを使用する
=======================================================

コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に維持します。 コネクタを使用すると、Microsoft Teams ユーザーは、Twitter、Trello、Wunderlist、GitHub、Azure DevOps サービスなどの一般的なサービスからの更新情報を、チームのチャットストリームで受け取ることができます。

チームの権限が許可されていて、すべてのチームメンバーがそのサービスのアクティビティについて通知する場合は、チームのメンバー全員がそのコネクタを使用して、チームの主要なクラウドサービスに接続できます。 コネクタを最初に設定したメンバーが残っている場合でも、コネクタは引き続き機能します。 権限を持つすべてのチームメンバーは、他のメンバーによるコネクタの設定を変更できます。

Microsoft 365 コネクタは、Microsoft Teams と Microsoft 365 グループの両方で使用できます。すべてのメンバーが同期して、関連する情報をすばやく受け取ることができるようになります。 Microsoft Teams と Exchange は両方とも同じコネクタモデルを使用しており、両方のプラットフォームで同じコネクタを使用できます。 ただし、チームが依存している Office 365 グループのコネクタを無効にすると、そのチームのコネクタの作成機能も無効になります。

<a name="add-a-connector-to-a-channel"></a>チャネルにコネクタを追加する
----------------------------

現時点では、Microsoft Teams のデスクトップと web クライアントを使用してコネクタを追加できます。 ただし、これらのコネクタによって投稿された情報は、mobile を含む**すべてのクライアント**で表示できます。

1. チャネルにコネクタを追加するには、チャネル名の右にある**省略記号 (...)** をクリックし、[**コネクタ**] をクリックします。

    ![[コネクタ] オプションが選択されている Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. さまざまなコネクタから選んで、[**追加**] をクリックします。

    ![使用可能なコネクタが表示されている [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。

    ![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. コネクタによって提供されるデータはチャネルに自動的に投稿されます。

    ![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>カスタム コネクタを開発する
----------------------------

カスタムコネクタや、受信および送信の web フックを作成することもできます。 詳細については、「[開発者向けドキュメント](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください:
