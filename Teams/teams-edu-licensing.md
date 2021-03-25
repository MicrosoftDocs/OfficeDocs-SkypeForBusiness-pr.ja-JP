---
title: 教育機関管理者向け Microsoft Teams のリソース
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams for EDU のライセンスに関するチュートリアル。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83448f32ddfc96800a14b5a599ef9cb7af52bb9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119236"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a>教育機関向け Microsoft Teams ライセンスを割り当てる

Microsoft Teams は、会話、コンテンツ、アプリが 1 か所にまとめられたデジタル ハブです。 Microsoft Teams は Office 365 に組み込まれています。使い慣れている Office アプリおよびサービスと統合されているということは、学校にとって大きなメリットです。 教師は Microsoft Teams を使用することで、クラスでの共同作業環境の構築、教師仲間が集まる学習コミュニティへの参加、学校スタッフとのやり取りをすべて、Office 365 for Education の単一のエクスペリエンスで実現することができます。

使用を開始するには、IT 管理者は、Microsoft 365 管理センターを使用して[学校向けに Microsoft Teams を有効にする](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)必要があります。
この操作を完了したら、教職員と生徒が Microsoft Teams などの Office 365 サービスにアクセスできるよう、ユーザー アカウントにライセンスを割り当てる必要があります。

ユーザー アカウントへのライセンスの割り当ては、個別に行うことも、グループ メンバーシップを使用して自動的に行うこともできます。 この記事では、Microsoft 365 管理センターで Office 365 のライセンスを個々のユーザー アカウントまたは少数のユーザー アカウントに割り当てる手順を説明します。 グループ メンバーシップを使用してライセンスを自動的に割り当てるには、次のサポート記事を参照してください。

- [Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [Active Directory でのグループベースのライセンス認証](/azure/active-directory/users-groups-roles/licensing-groups-assign)

ユーザーへのライセンスの割り当ては、[**ライセンス**] ページまたは [**アクティブなユーザー**] ページで行えます。 どちらの方法を使用するかは、製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって決まります。

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>ライセンス ページでユーザーにライセンスを割り当てる

> [!NOTE]
> グローバル管理者、課金管理者、ライセンス管理者、またはユーザー管理の管理者のいずれかである必要があります。詳細については、「[Office 365 の管理者ロールについて](/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。

[**ライセンス**] ページを使用してライセンスを割り当てる場合、特定の製品のライセンスを最大 20 人のユーザーに割り当てることができます。 [**ライセンス**] ページには、サブスクリプションを所有するすべての製品のリストが表示されます。各製品のライセンスの総数、割り当て済みのライセンスの数、および使用可能なライセンスの数も表示されます。

1. 管理センターで、[**課金**] > [[ライセンス](https://go.microsoft.com/fwlink/p/?linkid=842264)] ページに移動します。

   ![[課金] ウィンドウとメニュー オプションのスクリーンショット。](media/EDU-Lic-Billing-License.png)
2. ライセンスを割り当てる製品を選択します。 Microsoft Teams は、無料の Office 365 A1 for Students SKU に含まれています。

   ![ライセンスを割り当てることができる製品を表示する、[ライセンス] ページのスクリーンショット。](media/EDU-Lic-Licenses-Products.png)
3. [**ライセンスの割り当て**] を選択します。

   ![ページの [ユーザー] セクションと、正符号に続く [ライセンスの割り当て] オプションのスクリーンショット。](media/EDU-Lic-Assign-Licenses.png)
4. [**ユーザーへのライセンスの割り当て**] ウィンドウで、名前を入力し始めます。名前のリストが作られて表示されるはずです。 表示された結果から目的の名前を選択し、リストに追加します。 最大 20 人のユーザーを同時に追加できます。

   ![名前の一部が入力され、部分的な名前に基づく検索の結果を表示する、[ユーザーへのライセンスの割り当て] ウィンドウのスクリーンショット。](media/EDU-Lic-Assign-Licenses-Users.png)
5. Microsoft Teams など、特定のアイテムへのアクセス権の割り当てまたは削除を行うには、[**アプリとサービスのオン/オフの切り替え**] を選択します。 [**Microsoft Teams**] と [**Office for the web (Education)**] が選択されていることを確認してください。
6. 完了したら、[**割り当て**] を選択し、[**閉じる**] を選択します。

ユーザーがアクセスできるアプリとサービスを変更する方法。

1. 目的のユーザーが含まれている行を選択します。
1. 右側のウィンドウで、アクセス権の付与または削除を行うアプリとサービスを選択または選択解除します。
1. 完了したら、[**保存**] を選択し、[**閉じる**] を選択します。

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a>[アクティブなユーザー] ページで複数のユーザーにライセンスを割り当てる

1. 管理センターで、**[ユーザー]** > [[アクティブなユーザー]](https://go.microsoft.com/fwlink/p/?linkid=834822) ページの順に移動します。

   ![Microsoft O365 管理センターの [アクティブなユーザー] メニュー オプションのスクリーンショット。](media/EDU-Lic-Active-Users.png)
2. ライセンスを割り当てるユーザー名の横にある丸を選択します。

   ![名前の横の丸が塗りつぶされているために何人かのユーザーが選択された状態の、[アクティブなユーザー] ページとそのページに表示されるアクティブなユーザーの一覧のスクリーンショット。](media/EDU-Lic-Active-Users-List.png)
3. 上部にある [**製品ライセンスの管理**] を選択します。

   ![[製品ライセンスの管理] タブとその下に表示される、[ライセンスなし] と示されるユーザーのスクリーンショット。](media/EDU-Lic-Manage-Product-Licenses.png)
4. [**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンスの割り当てに追加**] > [**次へ**] の順に選択します。

   ![[既存の製品ライセンスの割り当てに追加] ラジオ ボタンが選択されている、[製品ライセンスの管理] ウィンドウのスクリーンショット。](media/EDU-Lic-Add-Existing-Product.png)
5. [**既存の製品に追加**] ウィンドウで、選択したユーザーに付与するライセンスのトグルを [**オン**] の位置に切り替えます。 [**Microsoft Teams**] と [**Office for the web (Education)**] が選択されていることを確認してください。

   ![[既存の製品に追加] タブで選択されている [Microsoft Teams] と [Office for the web, Education] のスクリーンショット。](media/EDU-Lic-Add-Existing-Products.png)

   既定により、これらのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。 ユーザーが利用できるサービスを制限できます。 ユーザーに使用させないサービスのトグルを [**オフ**] の位置に切り替えます。
6. ウィンドウの下部で、[追加] > [閉じる] の順に選択します。