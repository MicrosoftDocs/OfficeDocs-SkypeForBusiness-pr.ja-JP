---
title: Teams 電話システム電話番号をユーザーに割り当てる
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Microsoft Teams 電話システム電話番号を組織内のユーザーに割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ac68e38975eaece18554a1aa04f18734da2c851
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053016"
---
# <a name="step-5-assign-teams-phone-system-phone-numbers-to-your-users"></a>手順 5: Teams 電話システム電話番号をユーザーに割り当てる

ユーザーがTeamsを使用して通常の電話回線との間で通話を発信または受信できるようにするには、そのユーザーに電話番号を割り当てる必要があります。 Microsoft Teams クライアントでは、ユーザーが **[通話**] をクリックすると、ユーザーに割り当てる電話番号がダイヤル パッドに表示されます。 電話番号を必要とするユーザーごとに、次の操作を行います。

> [!NOTE]
> 電話番号が表示されない場合は、お待ちください。 新しい電話番号がTeamsで利用できるようになるまでに数時間かかる場合があります。

1. Microsoft Teams管理センターを開き、グローバル管理者であるユーザーでログインします。これは通常、Microsoft 365にサインアップするために使用したアカウントです。
1. 左側のナビゲーション ウィンドウで、[<a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **電話 numbers**</a>] に移動します。
1. **[電話番号**] ページで、一覧で割り当てられていない番号を選択し、[編集] をクリック **します**。  
1. **[編集]** ウィンドウの [**割り当て元**] で、表示名またはユーザー名でユーザーを検索し、[**割り当て**] をクリックします。
1. [ **緊急の場所**] で、[緊急の場所の設定] ステップで追加した緊急対応 [の場所](set-up-emergency-locations.md) を選択するか、別のオフィスまたはホーム オフィスの新しい場所を作成する必要がある場合は、[ **場所の追加]** をクリックします。
1. 電話番号情報を含むウェルカム メールをユーザーに送信するかどうかを決定します。 以下を希望する場合:
    - **既存の電話番号を** 電話システム (電話番号の移植と呼ばれる) に移動し、電話番号 **情報を含む電子メール ユーザー***の選択を解除します*。
    - 電話システムによって選択された **新しい電話番号を使用し**、**電話番号情報を含む [電子メール ユーザー***] を選択します*。
1. **[保存]** をクリックします。
1. 電話番号を割り当てるユーザーごとに、上記の手順を繰り返します。

> [!NOTE]
> Microsoft 通話プランをユーザーに割り当てた後、Teams クライアントにダイヤル パッドが表示されるまでに最大で 24 時間かかる場合があります。 24 時間以内にダイヤル パッドが表示されない場合は、 [ダイヤル パッドの構成](/microsoftteams/dial-pad-configuration)を確認します。 必要に応じて、 [サポートにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products)。

> [!div class="nextstepaction"]
> [次の手順: 自動応答を設定する](set-up-auto-attendant.md?tabs=general-info#steps)
