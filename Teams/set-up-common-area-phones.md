---
title: Microsoft Teams での共通領域電話のライセンスをセットアップする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'ロビー、受付、および会議室の共通領域電話を設定する方法を学習します。 '
ms.openlocfilehash: 9e68d5bc4ef0355e80e1fe6359385c10a339c0fe
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632378"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Microsoft Teams での共通領域電話のライセンスをセットアップする

共通領域電話は通常、ロビーのような領域、またはをかけるには多くの人々 に利用できる別の領域に配置しています。たとえば、受信エリア、ロビー、または会議電話します。 共通領域電話は、ユーザーではなくデバイスとして設定して、ネットワークに自動的に署名できます。

以下の手順でお手伝いの組織の共通領域電話を展開する電話システムのアカウントを設定します。 包括的な会議室の経験、音声会議を含む会議では、専用の会議室ライセンスの購入を検討してくださいルーム デバイスです。 

最初に作業を実行する必要がありますは、共通領域電話 (CAP) のライセンスを購入には、認定の電話があるかどうかを確認します。 検索し、認定された電話の詳細についてには、[マイクロソフトのチームのデバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)に移動します。 

## <a name="step-1---buy-the-licenses"></a>手順 1  - ライセンスを購入する

1. Microsoft 365 管理センターでは、**請求先**に移動 > **購買サービス**し、**他の計画**を展開します。

    ![共通領域電話を示すスクリーン ショットを並べて表示します。](media/set-up-common-area-phone-image1.png)

2. **共通領域電話**を選択して > **今すぐ購入**します。

3. [**チェック アウト**] ページで、**今すぐ購入**] をクリックします。

4. **アドオンのサブスクリプション**を展開し、呼び出す計画を購入する] をクリックします。 **国内計画を呼び出す**か、**国内または国際通話プラン**を選択します。

> [!NOTE]
> 電話システムのライセンスは必要ありません。  共用エリア電話機  のライセンスに含まれています。

ライセンスの詳細については、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます

1. Microsoft 365 管理センターでは、**ユーザー**に移動 > **アクティブなユーザー** > **ユーザーを追加**します。

2. ユーザー名"Main"のように [名] および [受信] の 2 番目の名前を入力します。

3. 「メインの受信」のような 1 つを自動生成していない場合は、表示名を入力します。

4. "MainReception"または"Mainlobby です"のようにユーザー名を入力してください。

5. 共通領域電話のパスワードを手動で設定するか、すべての共通領域電話に対して同じパスワードを入力する場合。 また、**このユーザーが最初にサインインするときにパスワードを変更する**] チェック ボックスをオフにする考えてください。

6. ユーザーにライセンスを割り当てます。 同じページで、**[製品ライセンス]** をクリックして拡大してください。 共通領域電話をオンにし、**国内の計画を呼び出す**か**国内および国際を呼び出す計画**を選択します。 

    ![スクリーン ショットの表示されているライセンスの割り当て](media/set-up-common-area-phone-image2.png)

詳細については、[ユーザーの追加](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)を参照してください。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる

番号をユーザーに割り当てるには、ビジネス管理センターの Skype を使用します。

1. Microsoft 365 管理センターの**管理センター**を選択して > **チーム & Skype** > **従来のポータル**です。

2. ビジネス管理センターの Skype での**音声**を選択して > **の電話番号**です。

3.  電話番号のリストから番号を選択し、** [割り当て]**  をクリックします。

4. [**割り当てる**] ページで、音声ユーザー ボックスで、**音声ユーザーを選択**」ドロップ ダウン リストで、電話番号、し、ユーザーを選択に使用したユーザーの名前を入力します。

5. この作業の間に、緊急アドレスを追加する必要があります。 」ドロップ ダウン リストから、**市区町村別の検索****の説明で検索**、または**別の場所の検索**を選択し、テキスト ボックスに、市区町村、説明、または場所を入力します。 検索すると後、は、[**緊急時のアドレスを選択**するにふさわしいものを選択するのには確認します。

6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

   ![スクリーン ショットの表示されているライセンスの割り当て](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> ユーザーのみが表示されます適用電話システムのライセンスがあるかどうか。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。

詳細については、[ユーザーの電話番号の取得](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)を参照してください。

別のキャリアと「ポート」を持っているか、Office 365 に転送する電話番号を実行することもできます。 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。


