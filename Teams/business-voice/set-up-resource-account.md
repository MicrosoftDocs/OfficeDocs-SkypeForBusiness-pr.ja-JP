---
title: リソース アカウントMicrosoft 365 Business Voice設定する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 自動応答で使用するためにMicrosoft 365 Business Voiceリソース アカウントを設定する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130438"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>手順 4: Business Voice リソース アカウントを設定する

このMicrosoft Teams、自動応答キューまたは通話キューごとにリソース アカウントが必要です。 リソース アカウントには、サービスの電話番号も割り当てることができます。 次に、自動応答と通話キューに電話番号を割り当て、外部の発信者が自動応答または通話キュー Teamsに到達できるようにします。

## <a name="obtain-virtual-user-licenses"></a>仮想ユーザー ライセンスを取得する

リソース アカウントでは、自動応答と呼び出しキューを操作するためにライセンスが必要です。 無料の仮想ユーザー ライセンス *Microsoft 365 電話システム使用* できます。

1. Microsoft 365 管理センターにサインインします。
2. [課金購入  >  **サービスの**  >  **アドオン] に移動すべての**  >  **アドオン製品を表示する**
3. 最後までスクロールして、仮想ユーザー ライセンスMicrosoft 365 電話システム **を見** つける。 [詳細 **] を選択** し、[購入] **を選択します**。
4. [ライセンス購入] ページで、必要な仮想ユーザー ライセンスの数を選択します。 セットアップする予定の自動応答キューと通話キューごとに 1 つの仮想ライセンスが必要です。 少なくとも 5 つのライセンスを選択することをお勧めします。今後は、より多くのライセンスを購入することなく、より多くの自動応答と通話キューを簡単に設定できます。
5. [ライセンス **を持つすべてのユーザーに自動的に割り当てる] をオフにします**。
6. [今 **すぐチェックアウト] を選択します**。
7. 注文を確認し、[次へ] **を選択** し、[注文 **を行う] を選択します**。

> [!NOTE]
> コストが 0 の  **場合でも、** ライセンスを購入する必要があります。

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

仮想ユーザー ライセンス - 仮想Microsoft 365 電話システム *を受け* 取った後、リソース アカウントを作成できます。

![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add.png)

1. 管理センター Teams、組織全体の設定 **を** 展開し、[リソース アカウント]**をクリックします**。
2. **[追加]** を選択します。
3. [リソース アカウント **の追加] ウィンドウで** 、[表示名] **と**[ユーザー名] の順に **入力します**。 リソース アカウントの目的を説明するために、"メイン ライン自動応答" などのわかりやすい表示名を選択します。
4. [ **リソース アカウントの種類] で、[** 自動応答] **を選択します**。
5. **[保存]** を選択します。

![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a>ライセンスを割り当てる

リソース アカウントを作成したら、仮想ユーザー ライセンスまたは仮想ユーザー ライセンスMicrosoft 365 電話システム *割* り当てる *電話システムがあります。*

![管理者センターでライセンスを割り当てるユーザー インターフェイスMicrosoft 365スクリーンショット](../media/resource-account-assign-virtual-user-license.png)

1. 管理センター Microsoft 365、ユーザーのアクティブな **ユーザーに**  >  **移動します**。
2. リソース アカウントを選択します。
1. [ライセンスと **アプリ] タブの**[ライセンス **] の下で**、[Microsoft 365 電話システム **- 仮想ユーザー] を選択します**。
1. [変更 **の保存] を選択** し、[閉じる] **を選択します**。

## <a name="assign-a-service-number"></a>サービス番号を割り当てる

![サービス番号の割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-phone-number.png)

1. 管理センター Teams、組織全体の **設定に** 移動し、[リソース アカウント]**に移動します**。 
1. 作成したリソース アカウントを選択し、[割り当て/割り当て解除] **をクリックします**。
1. [ユーザー番号 **電話] ドロップダウンで、[** オンライン] を **選択します**。
1. [割り **当て済み電話番号]** ボックスで、使用する番号を検索し、[追加] を **クリックします**。 必ず国コードを含める (たとえば **、+1** 250 555 0012)
1. **[保存]** をクリックします。
    > [!NOTE]
    > 番号を追加する自動応答が既に選択されているので、[割り当て] で自動応答を選択する必要はない。

> [!div class="nextstepaction"]
> [次の手順: ユーザーに電話番号を割り当てる](set-up-assign-numbers.md)
