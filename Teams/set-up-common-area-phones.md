---
title: 共通領域のライセンスを電話する
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
description: 'ロビー、受信エリア、会議室の共通領域電話を設定する方法について学習する '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117115"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Microsoft Teams での共通領域電話のライセンスをセットアップする
> [!NOTE]
> 一般的なエリアの電話ではボイスメールはサポートされていません。

一般的なエリアの電話は、通常、ロビーや、多くのユーザーが通話を行える別のエリアに配置されます。たとえば、受信エリア、ロビー、電話会議などです。 共通領域の電話は、共通領域のライセンスに関連付電話されます。 また、TeamsIPPhone ポリシーは、共通の領域のユーザー エクスペリエンスを持つ携帯電話に対して適切に設定する必要があります。

以下の手順では、組織の共通エリア電話を展開電話システムアカウントを設定する方法について説明します。 電話会議など、より完全な会議室エクスペリエンスを得る場合は、会議室デバイスで専用の会議室ミーティング ルームライセンスを購入してください。 

まず、Common Area 電話 (CAP) ライセンスを購入し、認定された電話を持っている必要があります。 認定された電話を検索して詳細を確認するには、デバイスのMicrosoft Teams[してください](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。 

## <a name="step-1---buy-the-licenses"></a>手順 1  - ライセンスを購入する

1. 管理センター Microsoft 365、[課金購入サービス] に移動 **し**、[その他のプラン]  >  **を展開します**。

    ![[共通領域] タイルを電話スクリーンショット](media/set-up-common-area-phone-image1.png)

2. [共通 **領域] を選択電話**  >  **購入] を選択します**。

3. [チェックアウト] ページで、[今すぐ購入 **] をクリックします**。

4. [ **アドオン サブスクリプション] を展開し** 、[通話プラン] をクリックして購入します。 [国内通話プラン **] または [** 国内通話プラン] または [ **国際通話プラン] を選択します**。

> [!NOTE]
> システム ダイレクト ルーティングMicrosoft 電話使用している場合は、通話プランライセンスは必要ではありません。

> [!NOTE]
> ライセンスを追加する必要電話システム。  共用エリア電話機  のライセンスに含まれています。

ライセンスの詳細については、「Microsoft Teams[ライセンス」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

共通領域ライセンスでは電話サポートされます。 


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

&sup1;共通領域電話は、会議開催者から提供されたダイヤルイン番号を介して音声会議に参加できます。

&sup2; ソブリン クラウドでは使用不可  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます

1. 管理センター Microsoft 365、アクティブなユーザーに **ユーザーを追加**  >    >  **するに移動します**。

2. 名には "Main" のようなユーザー名を入力し、2 番目の名前には "受信" を入力します。

3. "メイン の受信" のように自動生成しない場合は、表示名を入力します。

4. "MainReception" や "Mainlobby" のようなユーザー名を入力します。

5. 一般的な地域の電話の場合は、パスワードを手動で設定するか、すべての共通領域の電話に同じパスワードを設定できます。 また、[このユーザーが初めてサインインするときにパスワードを変更する] チェック ボックスをオフ **にすることもできます** 。

6. ライセンスをユーザーに割り当てる。 同じページで、**[製品ライセンス]** をクリックして拡大してください。 [共通エリア] をオン電話国内通話プランまたは国内通話プランと国際通話プラン **のいずれかを選択します**。 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> システム ダイレクト ルーティングMicrosoft 電話使用している場合は、通話プランライセンスを割り当てる必要があります。

詳細については、「ユーザーにライセンスを [割り当てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる

管理センター Teamsを使用して、ユーザーに番号を割り当てる。

1. [Teams 管理センターで、[Voice 電話  >  **numbers] を選択します**。

3.    電話番号のリストから番号を選択し、**[割り当て]**  をクリックします。

4. [割 **り** 当て] ページの [音声ユーザー] ボックスに、電話を使用するユーザーの名前を入力し、[音声ユーザーの選択] ドロップダウン リストでユーザーを選択します。

5. 次に、緊急対応の住所を追加する必要があります。 ドロップダウン **リストから [市****区町** 町地で検索]、説明で検索、または [場所で検索] を選択し、テキスト ボックスに都市、説明、または場所を入力します。 検索したら、[緊急対応の住所 **の選択] を見** て、適切な住所を選択します。

6. **[保存]** をクリックすると、ユーザーが以下のように表示されます。

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> ユーザーは、ライセンスが適用されている場合電話システム表示されます。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。

詳細については、「ユーザーの [電話番号を取得する」を参照してください](getting-phone-numbers-for-your-users.md)。

また、別の携帯電話会社と一緒に持っている電話番号を受け取り、"ポート" したり、携帯電話や携帯電話にMicrosoft 365 Office 365。 「[電話番号を電話番号に転送する」をTeams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)