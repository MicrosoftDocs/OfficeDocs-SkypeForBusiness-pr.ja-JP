---
title: 共通領域電話のライセンスを設定する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'ロビー、受付領域、会議室の共通領域電話を設定する方法について学習します。 '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117115"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Microsoft Teams での共通領域電話のライセンスをセットアップする
> [!NOTE]
> 一般的な地域の電話ではボイスメールはサポートされていません。

一般的な地域の電話は、ロビーや、多くの人が通話できる別の場所に置かれるのが一般的です。たとえば、受付領域、ロビー、電話会議などです。 共通領域の電話は、共通領域の電話ライセンスに関連付られたアカウントでサインインします。 また、スマートフォンで共通の領域のユーザー エクスペリエンスを利用するには、TeamsIPPhone ポリシーも適切に設定する必要があります。

以下の手順では、組織の共通領域の電話を展開する電話システムのアカウントを設定する方法について説明します。 より完全な会議室エクスペリエンス (電話会議を含む) を行う場合は、会議室デバイスで専用の会議室ライセンスを購入する方法を検討してください。 

まず、共通領域電話 (CAP) ライセンスを購入し、認定された電話を持っている必要があります。 認定された電話を検索して詳細を確認するには [、Microsoft Teams デバイスを参照してください](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。 

## <a name="step-1---buy-the-licenses"></a>手順 1  - ライセンスを購入する

1. Microsoft 365 管理センターで、[課金 **購入サービス**] に移動し、[その他のプラン]  >  **を展開します**。

    ![[共通領域の電話] タイルを示すスクリーンショット](media/set-up-common-area-phone-image1.png)

2. [今すぐ **購入] を選択**  >  **します**。

3. [チェックアウト] ページで、[今すぐ購入 **] をクリックします**。

4. アドオン **サブスクリプションを展開し、** クリックして通話プランを購入します。 国内通話プラン **または国内通話プランと** 国際通話 **プランのいずれかを選択します**。

> [!NOTE]
> Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスは必要ではありません。

> [!NOTE]
> 電話システム ライセンスを追加する必要はない。  共用エリア電話機  のライセンスに含まれています。

ライセンスの詳細については [、Microsoft Teams のアドオン ライセンスを参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

共通領域電話のライセンスでは、次の機能がサポートされます。 


|   |  共用エリア電話機  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|電話システム |    &#x2714; |
|電話会議 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|世界的な可用性 |       &#x2718; &sup2;  |
|チャネルの可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;共通領域電話は、会議開催者から提供されたダイヤルイン番号を使用して音声会議に参加できます。

&sup2; ソブリン クラウドでは使用不可  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます

1. Microsoft 365 管理センターで、アクティブなユーザーがユーザーを追加  >    >  **するユーザーに移動します**。

2. 名の場合は "メイン"、2 番目の名前には "受信" のようなユーザー名を入力します。

3. "メイン受付" のように自動生成しない場合は、表示名を入力します。

4. "MainReception" や "Mainlobby" のようなユーザー名を入力します。

5. 一般的な地域の電話の場合は、手動でパスワードを設定するか、すべての一般的な地域の電話に同じパスワードを設定できます。 また、[このユーザーが最初にサインインするときにパスワードを変更する] チェック ボックス **をオフにすることもできます** 。

6. ユーザーにライセンスを割り当てる。 同じページで、**[製品ライセンス]** をクリックして拡大してください。 Common Area Phone をオンにし、国内通話プランまたは国内通話プランと国際通話プラン **のいずれかを選択します**。 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスを割り当てる必要があります。

詳細については、「ライセンスをユーザーに割り [当てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる

Teams 管理センターを使用して、ユーザーに番号を割り当てる。

1. Teams 管理センターで、[音声電話番号 **] を**  >  **選択します**。

3.    電話番号のリストから番号を選択し、**[割り当て]**  をクリックします。

4. [割 **り当** て] ページの [音声ユーザー] ボックスに、電話を使用するユーザーの名前を入力し、[音声ユーザーの選択] ドロップダウン リストでユーザーを選択します。

5. 次に、緊急対応の住所を追加する必要があります。 ドロップダウン **リストから [****市区町** 地で検索]、[説明で検索]、または [場所で検索] を選択し、テキスト ボックスに市区町町区町間、説明、または場所を入力します。 検索が完了したら、[緊急対応の住所 **の選択]** の下で、適切な緊急対応の住所を選択します。

6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 電話システム のライセンスが適用されている場合にのみ、ユーザーが表示されます。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。

詳細については、「ユーザーの [電話番号を取得する」を参照してください](getting-phone-numbers-for-your-users.md)。

また、別の携帯電話会社で使用している電話番号を「ポート」したり、Microsoft 365 または Office 365 に転送したりすることができます。 「 [電話番号を Teams に転送する」を参照してください](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。