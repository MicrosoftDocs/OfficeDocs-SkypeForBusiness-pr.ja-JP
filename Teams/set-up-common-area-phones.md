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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'ロビー、受付領域、会議室の一般的なエリア電話を設定する方法について説明します。 '
ms.openlocfilehash: a62399c1c7b7b27e35fdea1fc52b9531a1fa25cc
ms.sourcegitcommit: 66213b972920b4e09faf7d7e732c4bfe7b322ac4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131513"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Microsoft Teams での共通領域電話のライセンスをセットアップする
> [!NOTE]
> 一般的なエリア電話ではボイスメールはサポートされません。

通常、一般的なエリアの電話は、ロビーなどの領域に配置され、多くのユーザーが通話を発信できるようになります。たとえば、受付領域、ロビー、会議電話などです。 一般的なエリア携帯電話は、ユーザーではなくデバイスとして設定されるため、ネットワークに自動的にサインインすることができます。

以下の手順では、組織の一般的なエリア電話を展開するために電話システムのアカウントをセットアップする方法について説明します。 電話会議など、会議室の完全なエクスペリエンスを実現するには、会議室のデバイスを使用して、専用の会議室ライセンスを購入することを検討してください。 

まず、一般的なエリア電話 (CAP) ライセンスを購入して、認定された電話機を持っていることを確認する必要があります。 認定された電話の検索および詳細については、「 [Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)」を参照してください。 

## <a name="step-1---buy-the-licenses"></a>手順 1  - ライセンスを購入する

1. Microsoft 365 管理センターで、[**課金** > **サービス**] に移動し、[**その他のプラン**] を展開します。

    ![一般的なエリア電話のタイルを示すスクリーンショット](media/set-up-common-area-phone-image1.png)

2. [**一般的な市外局番** > を**今すぐ購入**] を選択します。

3. [**チェックアウト**] ページで、[**今すぐ購入**] をクリックします。

4. **アドオンサブスクリプション**を展開し、をクリックして通話プランを購入します。 **国内通話プラン**または**国内および国際通話プラン**のいずれかを選択します。

> [!NOTE]
> 電話システムのライセンスは必要ありません。  共用エリア電話機  のライセンスに含まれています。

ライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

一般的な市外局番のライセンスは次の機能をサポートしています。 


|   |  共用エリア電話機  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|電話システム |    &#x2714; |
|電話会議 |       &#x2718; &sup1;  |
|Microsoft Intune |        &#x2718; &sup2; |
|世界中どこでも利用可能 |    &#x2714; |
|チャネルの可用性 |    EA、EAS、CSP、GCC、EES、Web ダイレクト  |
|      |         |

&sup1;一般的なエリア電話では、会議の開催者によって提供されるダイヤルイン番号を使用して、音声会議に参加できます。

&sup2;主権 cloud では使用できません。  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます

1. Microsoft 365 管理センターで、[ **** > **アクティブな** > ユーザー] に移動して**ユーザーを追加**します。

2. 名として "Main" のようなユーザー名を入力し、2番目の名前に "受信" と入力します。

3. 表示名は、"Main 受付" のように自動生成されない場合に入力します。

4. "MainReception" または "Mainreception" のようなユーザー名を入力します。

5. 一般的な市外局番については、手動でパスワードを設定するか、すべての共通エリア電話に同じパスワードを設定することができます。 また、[**ユーザーが最初にサインインしたときにパスワードの変更を行う**] チェックボックスをオフにすることも考えられます。

6. ライセンスをユーザーに割り当てます。 同じページで、**[製品ライセンス]** をクリックして拡大してください。 共通の市外局番をオンにして、**国内通話プラン**または**国内および国際通話プラン**を選択します。 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

詳細については、「[ユーザーを追加する](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)」を参照してください。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる

Skype for Business 管理センターを使用して、ユーザーに電話番号を割り当てます。

1. Microsoft 365 管理センターで、[**管理センター** > **チーム & Skype** > **レガシポータル**] を選択します。

2. Skype for business 管理センターで、[ **** > **電話番号**] を選択します。

3.  電話番号のリストから番号を選択し、** [割り当て]**  をクリックします。

4. [**割り当て**] ページの [音声ユーザー] ボックスに電話を使用するユーザーの名前を入力し、[**音声ユーザーの選択**] ドロップダウンリストでユーザーを選択します。

5. この作業の間に、緊急アドレスを追加する必要があります。 [**都市で検索**する]、[説明] で**検索**する、またはドロップダウンリストから**場所で検索**する、テキストボックスに市区町村、説明、または場所を入力します。 検索が完了したら、[**緊急対応の住所の選択]** の下で、適切なものを選びます。

6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> ユーザーは、電話システムのライセンスが適用されている場合にのみ表示されます。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。

詳細については、「[ユーザー用に電話番号を取得](/microsoftteams/getting-phone-numbers-for-your-users)する」を参照してください。

他の電話会社と共に使用している電話番号を取得したり、"ポート" を Office 365 に転送したりすることもできます。 「 [Office 365 に電話番号を転送する」を](transfer-phone-numbers-to-office-365.md)参照してください。


