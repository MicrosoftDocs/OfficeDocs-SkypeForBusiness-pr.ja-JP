---
title: 共通領域電話のライセンスをセットアップする
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
description: 'ロビー、受付エリア、会議室に共通領域電話を設定する方法について説明します '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117115"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Microsoft Teams での共通領域電話のライセンスをセットアップする
> [!NOTE]
> 共通領域電話はボイスメールをサポートしていません。

通常、共通領域電話はロビーなどのエリアや、多くの人が通話できる別のエリアに配置されます。たとえば、受付エリア、ロビー、会議電話などです。 共通領域電話は、共通領域電話ライセンスに関連付けられているアカウントでサインインします。 また、電話が共通領域のユーザー エクスペリエンスを提供できるように適切に TeamsIPPhone ポリシーが設定されている必要もあります。

以下の手順では、組織の共通領域電話を展開するための電話システムのアカウントを設定する方法について説明します。 電話会議を含む、より完全な会議室エクスペリエンスを実現するには、会議室デバイスで専用のミーティング ルーム ライセンスのご購入を検討してください。 

まず、共通領域電話 (CAP) のライセンスを購入し、認定された電話があることを確認する必要があります。 認定された電話の検索方法、および詳細情報を確認するには、[Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)にアクセスしてください。 

## <a name="step-1---buy-the-licenses"></a>手順 1 - ライセンスを購入する

1. Microsoft 365 管理センターで、[**課金情報**]  >  [**サービスの購入**] と進み、[**他のプラン**] を展開します。

    ![[共通領域電話] のタイルを示すスクリーンショット](media/set-up-common-area-phone-image1.png)

2. [**共通領域電話**]  >  [**今すぐ購入**] を選択します。

3. [チェックアウト] ページで、[**今すぐ購入**] クリックします。

4. **アドオン サブスクリプション** を展開し、クリックして通話プランを購入します。 [**国内通話プラン**] または [**国内および国際通話プラン**] のいずれかを選択します。

> [!NOTE]
> Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスは必要ありません。

> [!NOTE]
> 電話システムのライセンスは必要ありません。 共通領域電話のライセンスに含まれています。

ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

共通領域電話のライセンスは以下をサポートしています: 


|   |  共通領域電話  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|電話システム |    &#x2714; |
|電話会議 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|世界的な可用性 |       &#x2718; &sup2;  |
|チャネルの可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;共通領域電話は、会議開催者が提供するダイヤルイン番号を使用して音声会議に参加できます

&sup2; ソブリン クラウドでは使用できません  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>手順 2 - 電話機の新しいユーザ アカウントを作成し、ライセンスを割り当てます

1. Microsoft 365 管理センターで、[**ユーザー**]  >  [**アクティブ ユーザー**]  >  [**ユーザーの追加**] の順に選択します。

2. 名に "メイン" のようなユーザー名を入力し、姓に "受け付け" と入力します。

3. "受け付け メイン" のように自動生成されない場合は、表示名を入力します。

4. "MainReception" や "Mainlobby" などのユーザー名を入力します。

5. 共通領域電話では、パスワードを手動で設定するか、すべての共電話機に対して同じパスワードを設定した方がよい場合があります。 また、[**ユーザーが初回サインイン時にパスワードを変更する**] のチェック ボックスをオフにしてもよいでしょう。

6. ライセンスをユーザーに割り当てます。 同じページで、**[製品ライセンス]** をクリックして展開してください。 共通領域電話の電源を入れ、 **国内通話プラン** または **国内および国際通話プラン** を選択します。 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスを割り当てる必要はありません。

詳細については、「[ユーザーにライセンスを割り当てる](/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>手順 3 - 共通エリア電話機のユーザー アカウントに電話番号を割り当てる

Teams 管理センターを使用して、ユーザーに番号を割り当てます。

1. Teams 管理センターで、[**音声**]  >  [**電話番号**] の順に選択します。

3.    電話番号のリストから番号を選択し、[**割り当て**] をクリックします。

4. [**割り当て**] ページで、[音声ユーザー] ボックスに、電話を使用するユーザーの名前を入力し、[**音声ユーザーの選択**] のドロップダウン リストでユーザーを選択します。

5. 次に、緊急アドレスを追加する必要があります。 [**都市で検索**]、[**説明で検索**]、またはドロップダウン リストから [**場所で検索**] をし、テキスト ボックスに都市、説明、または場所を入力します。 検索したら、 [**緊急住所の選択**] の下を見て、適切な住所を選択します。

6. [**保存**] をクリックすると、ユーザーが以下のように表示されます。

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 電話システム ライセンスが適用さている場合のみ、ユーザーが表示されます。 この操作を実行したばかりだと、ユーザーがリストに表示されるまでに少し時間がかかることがあります。

詳細については、「[ユーザーの電話番号を取得する](getting-phone-numbers-for-your-users.md)」を参照してください。

迷っている場合は、別のキャリアや "ポート " で持っている電話番号を使用するか、それらを Microsoft 365 から Office 365 へ転送することもできます。 「[Teamsに電話番号を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。