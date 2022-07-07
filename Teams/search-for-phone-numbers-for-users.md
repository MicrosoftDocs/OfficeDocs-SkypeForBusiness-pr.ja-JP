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
description: ユーザーに割り当てることができる電話番号を国または地域、市区町村別に検索し、必要な番号の数量を指定する方法を確認します。
ms.openlocfilehash: 43aef76a16a8505e34407b15068a546dd2894343
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682506"
---
# <a name="search-for-telephone-numbers-for-users"></a>ユーザーの電話番号を検索する

Microsoft から提供された電話番号を使用して電話を発信および受信するように組織内のユーザーを設定する場合は、まず **Microsoft Teams 管理センター** を使用し、ユーザーに割り当てる電話番号を取得する必要があります。 ユーザーに割り当てる電話番号は、組織で以前に取得した電話番号になります。ユーザーのプロパティを編集して **[割り当て**] をクリックすると、ドロップダウン リストに数値が一覧表示されます。
  
Microsoft から提供された電話番号をユーザーに割り当てる前に、[ **新しい電話番号の取得** ] ページを使用して、使用可能な電話番号を検索する必要があります。 **国 (市場)**、**数値の種類**、**場所** で検索できます。 その後、その国で番号を指定する演算子の一覧が表示されます。

オペレーターとして Microsoft を選択した場合は、ユーザーに必要な電話番号の数量を入力して、Teams 管理センターから番号を取得できます。 ページでは、引き続き取得できる数量に基づいて数量が自動的に制限されます。 オペレーター接続演算子を選択すると、選択したオペレーターのランディング ページに移動して、番号の順序を完了します。

電話番号を取得および管理する方法は、PSTN 接続オプション (Microsoft 通話プラン、オペレーター接続、またはダイレクト ルーティング) によって異なります。

この記事は [、Microsoft 通話プラン](#search-for-telephone-numbers-for-microsoft-calling-plans) と [オペレーター接続](#search-for-telephone-numbers-for-operator-connect)に適用されます。 すべてのオプションの詳細については、「 [組織の電話番号を管理する」を参照してください](/microsoftteams/manage-phone-numbers-landing-page)。

## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Microsoft 通話プランの電話番号を検索する

ユーザーの電話番号を検索するには:
  
1. **Microsoft Teams 管理センター** に移動します。

2. 左側のナビゲーションで[**音声** > **電話番号** > ] を選択 **し、新しい番号を取得します**。
  
    > [!IMPORTANT]
    > Teams 管理センターの左側のナビゲーションで **[音声** ] オプションを表示するには、最初に少なくとも 1 つの **Enterprise E5 または E3 ライセンス**、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンス **を購入する** 必要があります。  

3. [ **場所と数量の選択** ] ページで、[ **国 (市場)]** ドロップダウン リストから場所を選択します。

4. [**数値の種類**] ドロップダウン リストから [**ユーザー**] を選択します。

5. 選択した国 (市場) に応じて、必要な電話番号の検索に使用できるオプションが異なります。  

6. [ **数量]** で、組織に必要な電話番号の数を入力し、[ **次へ**] をクリックします。 電話番号を選ぶ時間は 10 分間あります。 10 分を超えると、電話番号のプールに番号が返されます。

    > [!NOTE]
    > 使用可能な電話番号の数 (ライセンス数に基づく) が、[ **数量**] の横に表示されます。
  
7. [ **番号の取得** ] ページで、目的の電話番号を選択し、[ **番号の取得**] をクリックして、[ **次へ**] をクリックします。

    > [!IMPORTANT]
    > Microsoft ライセンスよりも多くの電話番号を取得できます。 取得できる電話番号の数を確認するには、Microsoft 通話プランライセンスの数を取得し、ライセンス数の 10% を追加してから 10 を追加し、既に取得した電話番号を削除します。 たとえば、Microsoft **国内通話プラン** または **国際通話プラン** のライセンスが 100 個ある場合は、100 人のユーザーの電話番号をまだ取得していないと仮定して、120 個の電話番号を予約できます。 詳細については、「電話番号を [取得できる電話番号の数](./how-many-phone-numbers-can-you-get.md)」を参照してください。

8. [ **確認** ] ページで、選択内容を確認し、[ **注文**] をクリックします。

9. **[電話番号**] ページに戻ったら、割り当てる電話番号を選択し、[**編集]** をクリックしてユーザーに割り当てます。

## <a name="search-for-telephone-numbers-for-operator-connect"></a>Operator Connect の電話番号を検索する

1. **Microsoft Teams 管理センター** に移動します。

2. 左側のナビゲーションで[**音声** > **電話番号** > ] を選択 **し、新しい番号を取得します**。
  
    > [!IMPORTANT]
    > Teams 管理センターの左側のナビゲーションで **[音声** ] オプションを表示するには、最初に少なくとも 1 つの **Enterprise E5 または E3 ライセンス**、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンス **を購入する** 必要があります。  

3. [ **場所と数量の選択** ] ページで、[ **国 (市場)]** ドロップダウン リストから場所を選択します。

4. [**数値の種類**] ドロップダウン リストから [**ユーザー**] を選択します。

5. 選択した国 (市場) に応じて、必要な電話番号の検索に使用できるオプションが異なります。 [自分の演算子を表示] を選択すると、追加した **演算子のみを表示** するようにフィルター処理できます。

6. オペレーターに既に同意を提供している場合は、注文プロセスを完了するためにオペレーターのランディング ページに移動します。

7. オペレーターに同意を提供していない場合は、Teams 管理センターの選択したオペレーター ページでオペレーターを有効にするように指示されます。 詳細については、「 [演算子を有効にする」を](operator-connect-configure.md#enable-an-operator)参照してください。

8. 注文が完了すると、オペレーターがテナントに電話番号をアップロードし、ユーザーに割り当てることができます。  

## <a name="related-topics"></a>関連項目

[組織の電話番号を管理する](manage-phone-numbers-landing-page.md)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
