---
title: 通話プランを使用して Teams Phone System に電話番号を移植する
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
description: 通話プランを使用して既存の電話番号を現在のプロバイダーから Microsoft Teams 電話 システムに移動する方法について説明します。
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
- M365initiative-voice
ms.openlocfilehash: a0e415b010a6c0c0250af5b3f95321f52324b43f
ms.sourcegitcommit: 46b5dc0519d487e264b1386e5074085c2d090e9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2022
ms.locfileid: "67668584"
---
# <a name="step-7-port-phone-numbers-to-teams-phone-system-with-calling-plan-optional"></a>手順 7: 通話プランを使用して Teams Phone System に電話番号を移植する (省略可能)

> [!IMPORTANT]
> この記事の情報は、通話プラン バンドルを **使用** する Teams Phone System にのみ適用されます。 通話プランバンドルを含む電話システムは、一部の国と地域でのみ使用できます。 この記事を読む前に、 [通話プラン バンドルを使用した Teams Phone System の国と地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) を確認して、お使いの国または地域が通話プラン バンドルを使用して電話システムをサポートしているかどうかを確認してください。
>
> 通話プラン バンドルを使用して電話システムをサポートしていない国または地域にテナントがある場合は、 [Microsoft リセラーまたはパートナーのヘルプを参照](reseller-partner-support.md)してください。
> 
## <a name="before-you-start"></a>開始する前に
このセットアップ ガイドの前半では、メインの会社の回線と、通話プランバンドル ライセンスを持つ Teams Phone を割り当てたすべてのユーザーの電話番号を取得しました。 **新しいビジネスで、通話プランを使用して Phone System に持ち込む既存の電話番号がない場合は、この手順をスキップできます。**

通話プランを使用して Phone System に移動するときに保持する電話番号が既にある場合は、電話番号移植と呼ばれるプロセスを使用して電話番号を通話プランの電話システムに移動することで、電話番号を持ち込むことができます。 通話プランを使用して電話番号を Phone System に移植した後、ユーザーとサービスに電話番号を割り当てます。 以前の番号は、このセットアップ ガイドの前に取得した一時的な番号に置き換わるものです。

通話プランを使用して電話番号を Phone System に移動する前に、 [電話番号の転送に関する一般的な質問を](../phone-number-calling-plans/port-order-overview.md)見てみましょう。 この記事には、サポートされている国や地域、転送できる番号と転送できない番号、必要な情報を含む質問への回答が含まれています。

## <a name="transferring-phone-numbers-to-microsoft-teams"></a>Microsoft Teams に電話番号を転送する
通話プランを使用して電話番号を電話システムに移動する準備ができたら、「 [Microsoft Teams に電話番号を転送して](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ポート注文を作成する」の手順に従います。 この注文には、現在の電話サービス会社から通話プランを使用して電話システムに番号を移動するために必要な情報が含まれます。

## <a name="assigning-phone-numbers-to-users"></a>ユーザーに電話番号を割り当てる
通話プランを使用して電話番号を電話システムに移動したら、その電話番号をユーザーに割り当てる必要があります。 これを行うには、「[ユーザーの電話番号を変更する](../assign-change-or-remove-a-phone-number-for-a-user.md)」の手順に従います。 これらの手順を実行すると、ユーザーに一時的に割り当てられた電話番号がポートした元の電話番号に置き換えられます。

## <a name="need-help"></a>サポートが必要な場合

電話番号を転送する際に問題が発生した場合は、 [よくある間違い](../phone-number-calling-plans/port-order-overview.md#common-mistakes-to-watch-out-for) を見て、問題の迅速な修正があるかどうかを確認してください。

さらにサポートが必要な場合、または特殊なケースの種類がある場合は、 [電話番号サービス (TNS) - サービス デスク](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)を参照してください。 通話プランを使用して電話番号を電話システムに移動できるように、できるだけ簡単にお手伝いします。

> [!div class="nextstepaction"]
> [次の手順: 通話プランの設定で Teams Phone System を終了する](set-up-finish.md)
