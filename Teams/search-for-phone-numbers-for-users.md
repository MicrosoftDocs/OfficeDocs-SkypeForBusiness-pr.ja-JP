---
title: ユーザーの電話番号を検索する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: cc22c49a-c644-4151-a2fc-a1474148f8ba
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: ユーザーに割り当て可能な電話番号を国または地域、市区町町会別に検索し、必要な電話番号の数を指定する方法を参照してください。
ms.openlocfilehash: b44a25865f58dcabd8876f0e4bfa6732cd4cde54
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046333"
---
# <a name="search-for-telephone-numbers-for-users"></a>ユーザーの電話番号を検索する

Microsoft が提供する電話番号を使用して電話を送受信するために組織内のユーザーを設定する場合は、まず **Microsoft Teams** 管理センターを使用し、ユーザーに割り当てる電話番号を取得する必要があります。 ユーザーに割り当てる電話番号は、組織で以前に取得した電話番号になります。ユーザーのプロパティを編集し、[割り当て] をクリックすると、この番号がドロップダウン リストに表示 **されます**。
  
Microsoft が提供する電話番号をユーザーに割り当てる前に、[新しい電話番号の取得] ページを使用して、使用可能な電話番号を検索する必要があります。 Country **(Market) 、Number** **type、Location** で **検索できます**。 その後、その国の数値を提供する演算子の一覧が表示されます。 

オペレーターとして [Microsoft] を選択した場合は、ユーザーに必要な電話番号の数を入力して、Teams 管理センターから番号を取得できます。このページでは、まだ取得できる数量に基づいて、数量が自動的に制限されます。 [オペレーター] 演算子をConnectすると、選択した演算子のランディング ページに移動して、番号の順序を完了します。 

電話番号を取得および管理する方法は、PSTN 接続オプション (Microsoft 通話プラン、オペレーター サービス、または直接ルーティング) によって異Connect異なります。 

この記事は[、Microsoft 通話](#search-for-telephone-numbers-for-microsoft-calling-plans)プランとオペレーター アカウント[に適用Connect。](#search-for-telephone-numbers-for-operator-connect) すべてのオプションの詳細については、「組織の電話番号を [管理する」を参照してください](/microsoftteams/manage-phone-numbers-landing-page)。

  
## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Microsoft 通話プランの電話番号を検索する

ユーザーの電話番号を検索するには: 
  
1. [管理センター **] Microsoft Teams移動します**。

2. 左側のナビゲーションで **、[Voice** 電話  >  **を選択します。**  >  
  
    > [!IMPORTANT]
    > Teams 管理センターの左側のナビゲーションに [音声] オプションを表示するには、まず、少なくとも 1 つの **Enterprise E5** または E3 ライセンス、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンスを購入する必要があります。  

3. [ **場所と数量の選択] ページ** で、[国 **(市場)** ドロップダウン リストから場所を選択します。

4. [ **数値の種類** ] **ドロップダウン リストから [** ユーザー] を選択します。

5. 選択した国 (市場) に応じて、必要な電話番号の検索に使用できるオプションが異なります。  

6. [ **数量]** で、組織に必要な電話番号の数を入力し、[次へ] を **クリックします**。 電話番号を選ぶ時間は 10 分間あります。 10 分以上かかる場合は、電話番号のプールに数値が返されます。

    > [!NOTE]
    > [数量] の横に表示されている使用可能な電話番号の数 (ライセンス数に基づく) を **確認できます**。 
  
8. [番号 **の取得] ページ** で、必要な電話番号を選択し、[番号の取得] をクリックして、[次へ] を **クリックします**。

    > [!IMPORTANT]
    > Microsoft ライセンスを持っている電話番号よりも多くの電話番号を取得できます。 取得できる電話番号の数を確認するには、Microsoft 通話プランのライセンス数を取得し、ライセンス数の 10% を追加してから、10 を追加してから、既に取得した電話番号を削除します。 たとえば、100 の Microsoft国内通話プランまたは **Microsoft** 国際通話プランのライセンスがある場合は、100 人のユーザーの電話番号をまだ取得していないと仮定して、120 の電話番号を予約できます。 詳細については、「取得できる電話番号 [の数」を参照してください。](./how-many-phone-numbers-can-you-get.md)

9. [確認 **] ページ** で、選択内容を確認し、[注文] **をクリックします**。

10. [電話番号] ページ電話、割り当てる電話番号または電話番号を選択し、[編集] をクリックしてユーザーに割り当てします。  


## <a name="search-for-telephone-numbers-for-operator-connect"></a>オペレーター の電話番号を検索Connect

1. [管理センター **] Microsoft Teams移動します**。

2. 左側のナビゲーションで **、[Voice** 電話  >  **を選択します。**  >  
  
    > [!IMPORTANT]
    > Teams 管理センターの左側のナビゲーションに [音声] オプションを表示するには、まず、少なくとも 1 つの **Enterprise E5** または E3 ライセンス、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンスを購入する必要があります。  

3. [ **場所と数量の選択] ページ** で、[国 **(市場)** ドロップダウン リストから場所を選択します。

4. [ **数値の種類** ] **ドロップダウン リストから [** ユーザー] を選択します。

5. 選択した国 (市場) に応じて、必要な電話番号の検索に使用できるオプションが異なります。 [演算子を表示] を選択すると、追加した演算子のみを表示 **するためにフィルター処理できます**。

6. オペレーターに既に同意した場合は、注文プロセスを完了するためにオペレーターのランディング ページに移動します。 

7. オペレーターに同意していない場合は、管理者センターの選択したオペレーター ページでオペレーターを有効Teamsされます。 詳細については、「演算子を有効 [にする」を参照してください](operator-connect-configure.md#enable-an-operator)。

8. 注文が完了すると、オペレーターはテナントに電話番号をアップロードし、ユーザーに割り当てできます。  

## <a name="related-topics"></a>関連項目

[組織の電話番号を管理する](manage-phone-numbers-landing-page.md)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)