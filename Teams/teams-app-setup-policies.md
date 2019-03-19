---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: マイクロソフトのチームおよび組織内のユーザーのチームをカスタマイズするのには暗証番号 (pin) のアプリケーションを使用するアプリケーション設定のポリシーについて説明します。
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: 29fcd5541e4817a2c5880316bba33d7d55047444
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664749"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

管理者としては、マイクロソフトのチームは、ユーザーにとって最も重要なアプリケーションを強調表示をカスタマイズするのにはアプリケーションの設定のポリシーを使用できます。 固定し、表示される順序を設定するアプリケーションを選択します。 アプリケーション設定のポリシーを使用するサード ・ パーティまたは組織内の開発者によって構築されたものなど、組織内のユーザーを必要とするアプリケーションを紹介します。 どの組み込みの機能を管理するアプリケーション設定のポリシーを使用することも表示されます。

アプリケーション バーには、アプリが固定されています。 これは、チームのデスクトップ クライアント側にし、チームのモバイル クライアント (iOS および Android) の下部にあるバーです。 

|チームのデスクトップ クライアント  |モバイル クライアントのチーム |
|---------|---------|
|![app-setup-policies-desktop-app-bar.png](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![app-setup-policies-mobile-app-bar.png](media/app-setup-policies-mobile-app-bar.png)      |

マイクロソフトのチームの管理センターでのアプリケーション設定のポリシーを管理します。 グローバル (組織全体の既定値) ポリシーを使用して、またはカスタム ポリシーを作成してユーザーに割り当てます。 組織内のユーザーを作成し、カスタム ・ ポリシーを設定しない限り、グローバル ポリシーが自動的に表示されます。

アプリケーションを含めるには、グローバル ポリシーの設定を編集することができます。 チーム、組織内のユーザーのグループごとにカスタマイズする場合は、作成し、1 つまたは複数のカスタム ポリシーを割り当てます。

![アプリケーション ・ セットアップ ・ policies.png](media/app-setup-policies.png)

> [!NOTE]
> ユーザーには、カスタム ポリシーが割り当てられているが場合、は、ユーザーにそのポリシーが適用されます。 ユーザーには、カスタム ポリシーが割り当てられていない、グローバル ポリシーがユーザーに適用されます。

## <a name="create-a-custom-app-setup-policy"></a>カスタム アプリケーション設定のポリシーを作成します。

マイクロソフトのチームの管理センターを使用すると、カスタム ポリシーを作成します。

1. マイクロソフトのチーム管理センターの左側のナビゲーションで**チームのアプリケーション**に移動する > **のポリシーを設定**します。
2. **新しいポリシー**を選択します。
3. ポリシーのわかりやすい名前を入力し、[**アプリケーションの追加**] をクリックします。
4. **追加には、アプリが固定されている**ウィンドウで、アプリケーションの**追加**] をクリックし、追加する検索します。 アプリケーションのアクセス許可ポリシーによってアプリケーションを抽出することもできます。 アプリケーションの一覧を選択したら、[**追加**を] をクリックします。

     ![アプリケーション ・ セットアップ ・ ポリシーの追加-apps.png](media/app-setup-policies-add-apps.png)

5. **保存**] をクリックし、チームの順序でアプリケーションを配置します。

    ![app-setup-policies-new-policy-setup.png](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>アプリケーション設定ポリシーを編集します。

グローバル (組織) のポリシー、カスタム ポリシーを作成するなど、ポリシーを編集するのには、マイクロソフトのチームの管理センターを使用できます。

1. マイクロソフトのチーム管理センターの左側のナビゲーションで**チームのアプリケーション**に移動する > **のポリシーを設定**します。
2. 編集するポリシーを選択します。 
3. ここでは、変更します。 追加、削除、およびアプリケーションの順序を変更することができます。
4. **[保存]** をクリックします。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>カスタム アプリケーション設定のポリシーをユーザーに割り当てる

カスタム ポリシーを個々 のユーザーまたはセキュリティ グループなど、ユーザーのグループまたは配布グループをカスタム ポリシーを割り当てるには、ビジネスの PowerShell モジュールの Skype を割り当てるには、マイクロソフトのチームの管理センターを使用できます。

> [!IMPORTANT]
> PowerShell を使用して、ユーザーにポリシーを割り当てることをお勧めします。 作成、編集、およびポリシーを管理するには、マイクロソフトのチームの管理センターを使用します。

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>カスタム アプリケーション設定のポリシーを個々 のユーザーに割り当てる

1. マイクロソフトのチーム管理センターの左側のナビゲーションでは、**ユーザー**に移動し、し、[ユーザー] をクリックします。
2. **[割り当てられているポリシー]** の隣にある **[編集]** を選択します。
3. **チームのアプリケーション設定のポリシー**では、アプリケーションの設定ポリシーを割り当てるを選択し、**保存**します。

    ![アプリケーション ・ セットアップ ・ ポリシーの割り当て-policy.png](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>グループ内のユーザーにカスタム アプリケーション設定のポリシーを割り当てる

既に認められた複数のユーザーにカスタム アプリケーション設定ポリシーを設定することがあります。 などのセキュリティ グループ内のすべてのユーザーにポリシーを設定する場合があります。 グラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype への接続で、これを行うことができます。 PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。

この例では、contoso 社の製薬会社の人事プロジェクト グループ内のすべてのユーザーに HR アプリケーションのセットアップのポリシーと呼ばれるカスタム アプリケーション設定のポリシーを割り当てます。  

> [!NOTE]
> 「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。

特定のグループの GroupObjectId を取得します。
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
指定したグループのメンバーを取得します。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
特定アプリケーションの設定のポリシーをグループ内のすべてのユーザーを割り当てます。 この例では、HR アプリケーションの設定のポリシーを勧めします。
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="faq"></a>FAQ

### <a name="working-with-app-setup-policies"></a>アプリケーション設定のポリシーを使用します。

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>マイクロソフトのチームの管理センターでは、どのような組み込みのアプリケーション設定のポリシーが含まれますか。

- **グローバル (組織全体の既定値)**: 別のポリシーを割り当てない限り、組織内のすべてのユーザーがこの既定のポリシーが適用されます。 暗証番号 (pin) アプリでは、ユーザーにとって最も重要なグローバル ポリシーを編集します。
- **FirstLineWorker**: このポリシーは、先頭行の作業者に対して。 先頭行の作業者に、組織内、ことを割り当てることができます。 カスタム ポリシーを作成することによりのようなあること設定をアクティブにするためにユーザーにポリシーを割り当てることを知っているが重要です。 詳細については、この資料の「[カスタム アプリケーション設定のポリシーをユーザーに割り当てる](#assign-a-custom-app-setup-policy-to-users)を参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>固定されたアプリケーションの追加] ウィンドウでアプリケーションを見つけることができないのはなぜでしょうか。

すべてのアプリケーション追加するにはチーム、アプリケーション設定のポリシーを使用します。 いくつかのアプリケーションは、この機能をサポートしない可能性があります。 固定できるアプリケーションを見つけるには、アプリケーションの**追加には、アプリが固定されている**ウィンドウ内の検索してください。 チームのデスクトップ クライアントに個人の範囲 (静的タブ)、bot が設定されているタブを固定することができます、これらのアプリケーションの**追加には、アプリが固定されている**ウィンドウで利用可能なです。

チームのアプリケーション ストアでは、**固定されている追加のアプリケーション**ウィンドウに追加するにはチームのポリシーを使用するアプリケーションのみが含まれていますに、チームのすべてのアプリケーションが一覧表示されることに留意してください。 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>私は、チームの管理者の教育教育のチームでのアプリケーション設定のポリシーについて理解するには何が必要でしょうか。

通話アプリでは、チームの教育では使用できません。 新しいカスタム アプリケーション設定のポリシーを作成するときは、アプリの一覧で通話アプリが表示されます。 ただし、アプリケーションは、クライアントのチームに固定表示されていないし、教育のユーザーのチームがチームでの呼び出しアプリケーションに表示されません。 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>どのように多くのアプリケーションは、ポリシーに追加できますか。

最低 2 つのアプリケーションは、チームのモバイル クライアント (iOS および Android) に固定する必要があります。 ポリシーに 2 つ以上のアプリケーションがある場合は、モバイル クライアントはポリシーの設定は反映されず、代わりには引き続き既存の構成を使用します。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>ポリシーの変更を有効にするためにどのくらい時間がかかりますか。

グローバル ポリシーを編集またはポリシーを設定すると、変更を反映させるには、最大で 24 時間がかかることができます。

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>ユーザーはチーム内のすべてが固定されたアプリをどのように表示できますか。

ユーザーが指定されているすべてのアプリケーションを表示するには、ユーザーはインストールされたアプリの数とそのチームのクライアント ウィンドウのサイズに応じて以下を実行する必要があります。

|チームのデスクトップ クライアント |モバイル クライアントのチーム |
|---------|---------|
|チームの横に、アプリケーション バーでは、**をクリックします。複数のアプリケーション**。| チームの下部にあるアプリケーション バーを機械に通します。|
|![app-setup-policies-desktop-more-apps.png](media/app-setup-policies-desktop-more-apps.png)<br>   |![app-setup-policies-mobile-more-apps.png](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>チーム モバイル エクスペリエンスについて理解するには何が必要でしょうか。

チームのモバイル クライアント (iOS および Android) 静的タブで個人用のアプリケーションが現在サポートされていません。 アプリケーション ポリシーの設定によってチームのデスクトップ クライアントに固定されているアプリケーションは、可能性があります、チームのモバイル クライアントでは表示されません。 個人 bot は、モバイル クライアントのチャットにも表示されます。

チームのモバイル クライアントでは、ユーザーはアクティビティ、チャット、チームなどのコア ・ チームのアプリケーションを参照してくださいし、シフトなど、マイクロソフトからいくつかのファースト パーティのアプリケーションを固定することができます。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>ユーザーは、ポリシーによって固定されているアプリケーションの順序を変更できますか。

現時点では、ユーザーは、チームのモバイル クライアントではなくチームのデスクトップまたは web クライアントは、固定されたアプリケーションの順序を変更することができます。 

### <a name="custom-teams-apps"></a>サバイバル-カスタム アプリケーション

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>自分の所属組織のカスタム チームのアプリケーションをビルドおよび発行、AppSource またはテナント アプリケーション カタログには、アプリケーションをチームでアプリケーション バーを固定するときに期待どおりにアプリケーションのアイコンが表示されていません。 どのように修正しますか。 

アプリケーションを送信する前に、ロゴのガイドラインに従うことを確認します。 詳細については、[販売者のダッシュ ボードの提出書類のチェックリスト](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)を参照してください。 

 ## <a name="related-topics"></a>関連項目
- [Teams でのアプリの管理設定](admin-settings.md)
- [チームでのアプリケーションのアクセス許可ポリシーを管理します。](teams-app-permission-policies.md)
- [カスタム アプリケーションのポリシーおよびチームの設定を管理します。](teams-custom-app-policies-and-settings.md)
- [テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。](tenant-apps-catalog-teams.md)
