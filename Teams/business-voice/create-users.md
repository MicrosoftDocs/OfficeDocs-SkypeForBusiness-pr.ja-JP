---
title: Microsoft 365 ユーザーを作成し、通話プラン バンドル ライセンスを使用して Teams Phone を追加し、電話番号を割り当てる
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 通話プランバンドル ユーザーを使用して Teams Phone System を作成してライセンスを付与し、電話番号を割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: ac665f46c7be619d26b0c6da371ba57e554a07ee
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272002"
---
# <a name="create-and-license-teams-phone-system-with-calling-plan-bundle-users-and-assign-them-phone-numbers"></a>通話プランバンドル ユーザーを使用して Teams Phone System を作成してライセンスを付与し、電話番号を割り当てる

通話プラン バンドルで Teams Phone System を使用するには、通話プラン バンドル ライセンスを持つ Teams Phone を持つ Microsoft 365 アカウントが必要です。 アカウントとライセンスがある場合は、電話番号の割り当てを開始できます。

## <a name="create-and-license-users"></a>ユーザーの作成とユーザーへのライセンスの割り当て

「[ユーザーを個別または一括で追加する](/microsoft-365/admin/add-users/add-users)」および「[ユーザーにライセンスを割り当てる](/microsoft-365/admin/manage/assign-licenses-to-users)」の手順に従います。

> [!NOTE]
> [ **製品ライセンスの割り当て** ] ウィンドウで、[ **通話プランを使用した Teams Phone**] を選択します。

## <a name="assign-phone-numbers-to-users"></a>ユーザーに電話番号を割り当てる

ユーザーを作成し、通話プラン バンドル ライセンスを使用して Teams Phone を割り当てた後、電話番号を割り当てることができます。 外部電話番号に対し発信または受信する必要がある各ユーザーに、割り当てられていない電話番号が必要です。 未使用の電話番号が十分ない場合、この記事で後述する「[追加の電話番号を取得する](#get-more-phone-numbers)」を参照してください。

1. [Teams 管理センター](https://admin.teams.microsoft.com)に移動します。
2. 電話番号の要求の名前と説明を入力します。
3. **[音声]**  >  **[電話番号]** の順に選択します。
4. ユーザーに割り当てる電話番号を選択し、次に **[編集]** を選択します。
5. **[編集]** パネルで、その電話番号を割り当てるユーザーの名前を **[割り当て先]** に入力します。 **[割り当て]** を選択します。
6. **[緊急対応の場所]** に、ユーザーの所在地を入力し、**[適用]** を選択します。

## <a name="get-more-phone-numbers"></a>追加の電話番号を取得する

新しいユーザーに割り当てるための電話番号が十分にない場合は、追加の電話番号を取得できます。 ご注文の番号が利用可能になるまでに最大 24 時間かかる場合があります。

1. [Teams 管理センター](https://admin.teams.microsoft.com)に移動します。
2. 電話番号の要求の名前と説明を入力します。
3. **[音声]**  >  **[電話番号]**  >  **[追加]** の順に選択します。
4. 電話番号の国または地域を選択します。
5. **[番号の種類]** で、**[ユーザー (サブスクライバー)]** を選択します。
6. **[場所]** では、ユーザーの場所を検索して選択します。 また、**[場所の追加]** を選択することもできます。
7. 市外局番を選択し、必要な電話番号の数を入力し、**[次へ]** を選択します。
8. 電話番号が予約されるのを待ってから、取得した番号を表示します。 すべて正常であれば、**[発注]**、**[完了]** の順に選択します。
