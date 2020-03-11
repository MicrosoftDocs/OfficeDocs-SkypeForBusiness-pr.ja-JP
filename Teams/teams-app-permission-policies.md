---
title: Microsoft Teams のアプリのアクセス許可ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams のアプリのアクセス許可ポリシーと、それらを使用して、組織内のユーザーが利用できるアプリを制御する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: baf3f025dd9b2340f59aee18d72d3707e4cab8fd
ms.sourcegitcommit: dde63e1b92c0bc3dbb41d8670778b863c3bc9bec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "42601414"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのアクセス許可ポリシーを管理する

管理者は、アプリのアクセス許可ポリシーを使って、組織内の Microsoft Teams ユーザーが利用できるアプリを制御することができます。 すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。 アプリをブロックすると、そのポリシーを持っているユーザーは、Teams app store からアプリをインストールできなくなります。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

アプリのアクセス許可ポリシーは、Microsoft Teams 管理センターで管理します。 グローバル (組織全体の既定) ポリシーを使用するか、またはグループ内の個々のユーザーまたはユーザーにカスタムポリシーを作成して割り当てることができます。  

![アプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies.png)

> [!NOTE]
> 組織内のユーザーは、カスタムポリシーを作成して割り当てる場合を除き、自動的にグローバルポリシーを取得します。 組織全体のアプリ設定は、グローバルポリシーや、作成してユーザーに割り当てるカスタムポリシーを上書きします。

組織が既に Teams に登録されている場合は、Microsoft 365 管理センターの**テナント全体の設定**で構成したアプリ設定が、[アプリの[管理](manage-apps.md)] ページの組織全体のアプリの設定に反映されます。 チームを初めて使い始めたばかりの場合は、既定ではすべてのアプリがグローバルポリシーで許可されています。 これには、Microsoft、サードパーティ、組織によって公開されたアプリが含まれます。

たとえば、すべてのサードパーティ製のアプリをブロックして、組織内の HR チーム向けに Microsoft が提供する特定のアプリを許可する必要があるとします。 最初に、[[アプリの管理](manage-apps.md)] ページに移動し、人事チームに許可するアプリが組織レベルで許可されていることを確認します。 次に、HR アプリのアクセス許可ポリシーという名前のカスタムポリシーを作成し、必要なアプリをブロックおよび許可するように設定し、人事チームのユーザーに割り当てます。

> [!NOTE]
> Microsoft 365 Government-GCC 環境に Teams を展開した場合は、「 [gcc のアプリのアクセス許可ポリシー](#app-permission-policies-for-gcc) 」を参照して、gcc に固有のサードパーティのアプリ設定の詳細を確認してください。

## <a name="create-a-custom-app-permission-policy"></a>カスタムアプリのアクセス許可ポリシーを作成する

組織内のユーザーグループごとに使用できるアプリを制御する場合は、1つ以上のカスタムアプリのアクセス許可ポリシーを作成して割り当てます。 Microsoft、サードパーティ、または組織によってアプリが公開されるかどうかに基づいて、個別のカスタムポリシーを作成して割り当てることができます。 組織全体のアプリ設定でサードパーティ製のアプリが無効になっている場合は、カスタムポリシーを作成した後にそれを変更することはできないことに注意してください。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ** > の**アクセス許可ポリシー**] に移動します。
2. [**追加**] をクリックします。
    ![新しいアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-new-policy.png)
3. ポリシーの名前と説明を入力します。
4. [ **Microsoft アプリ**]、[**サードパーティ製アプリ**]、[**テナントアプリ**] の下で、次のいずれかを選択します。

    - **すべてのアプリを許可する**
    - **特定のアプリを許可し、他のユーザーをブロックする**
    - **特定のアプリをブロックし、他のユーザーをすべて許可する**
    - **すべてのアプリをブロックする**

5. **[特定のアプリを許可**する] を選んで他のアプリをブロックする場合は、許可するアプリを追加します。

    1. [**アプリの許可**] を選びます。
    1. 許可するアプリを検索し、[**追加**] をクリックします。 検索結果は、アプリの発行元 (**Microsoft アプリ**、**サードパーティ製のアプリ**、**テナントアプリ**) にフィルター処理されます。
    1. アプリの一覧を選択したら、[**許可**] をクリックします。

6. 同様に、[**特定のアプリをブロック**する] を選択した場合は、ブロックするアプリを検索して追加します。
7. **[保存]** をクリックします。

## <a name="edit-an-app-permission-policy"></a>アプリのアクセス許可ポリシーを編集する

Microsoft Teams 管理センターを使用して、作成するグローバルポリシーやカスタムポリシーなどのポリシーを編集できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ** > の**アクセス許可ポリシー**] に移動します。
2. ポリシー名の左側をクリックしてポリシーを選択し、[**編集**] をクリックします。
3. ここで、必要な変更を行います。 アプリの発行元に基づいて設定を管理し、許可/禁止の設定に基づいてアプリを追加および削除することができます。
4. **[保存]** をクリックします。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>ユーザーにカスタムアプリのアクセス許可ポリシーを割り当てる

Microsoft Teams 管理センターを使用して、ユーザー設定のポリシーを1人または複数のユーザーに割り当てたり、Skype for Business PowerShell モジュールを使って、セキュリティグループまたは配布グループ内のすべてのユーザーなど、カスタムポリシーをユーザーのグループに割り当てることができます。

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a>ユーザーにカスタムアプリのアクセス許可ポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. [**アプリのアクセス許可ポリシー**] で、割り当てるアプリのアクセス許可ポリシーを選択し、[**適用**] をクリックします。

一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。

または、次の操作も実行できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ** > の**アクセス許可ポリシー**] に移動します。
2. ポリシー名の左側をクリックしてポリシーを選びます。
3. [**ユーザーを管理する**] を選択します。
4. [**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、[**保存**] をクリックします。

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>カスタムアプリのアクセス許可ポリシーをグループ内のユーザーに割り当てる

カスタムアプリのアクセス許可ポリシーは、既に指定した複数のユーザーに割り当てることができます。 たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。 これを行うには、Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続します。 PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。

この例では、Contoso 製薬 HR プロジェクトグループ内のすべてのユーザーに HR アプリのアクセス許可ポリシーと呼ばれるカスタムアプリのアクセス許可ポリシーを割り当てます。  

> [!NOTE]
> 「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。

特定のグループの GroupObjectId を取得します。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
指定したグループのメンバーを取得します。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
グループ内のすべてのユーザーに特定のアプリのアクセス許可ポリシーを割り当てます。 この例では、HR アプリのアクセス許可ポリシーです。
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="app-permission-policies-for-gcc"></a>GCC のアプリアクセス許可ポリシー

Microsoft 365 Government-GCC によるチームの展開では、GCC に固有のサードパーティのアプリ設定について、次の点を理解しておくことが重要です。

GCC では、すべてのサードパーティ製アプリが既定でブロックされます。 さらに、Microsoft Teams 管理センターの [アプリのアクセス許可ポリシー] ページでサードパーティ製のアプリを管理する方法について、次のメモが表示されます。

![GCC のアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-gcc.png)

ユーザーまたは組織内のユーザーのセットに対してサードパーティ製のアプリを有効にするには、次の操作を行います。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ** > の**管理**] に移動し、アプリの一覧で、ユーザーのセットに対して許可するサードパーティ製のアプリが組織レベルで**ブロック**されるように設定されていることを確認します。

2. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**アクセス許可ポリシー**] に移動し、グローバルポリシーを編集して、サードパーティ製のアプリをブロックします。 その手順は次のとおりです。
    1. [アプリのアクセス許可ポリシー] ページで、[**グローバル (組織全体の既定)**] をクリックし、[**編集**] をクリックします。
    2. [**サードパーティのアプリ**] で、[**特定のアプリをブロックする**] を選択し、[その他のすべてのアプリを許可する] を選び、[**保存**] をクリックします。

    > [!NOTE]
    > 組織レベルでアプリを許可するために、次の手順に進む前にこの操作を行うことが重要です。 これは、サードパーティのアプリがグローバルアプリのアクセス許可ポリシーでブロックされていない場合に、グローバルポリシーで適用されるすべてのユーザーが、組織レベルで許可したときにサードパーティ製のアプリにアクセスできるためです。

3. 組織レベルでサードパーティ製のアプリを許可します。 これを行うには、左側のナビゲーションで、[ **Teams アプリ** > の**管理**] に移動します。 アプリの一覧で、アプリ名の左側をクリックしてアプリを選択し、[**許可**] を選択します。
4. アプリを許可する[カスタムアプリのアクセス許可ポリシーを作成](#create-a-custom-app-permission-policy)し、そのポリシーを目的のユーザーに[割り当て](#assign-a-custom-app-permission-policy-to-users)ます。

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>アプリのアクセス許可ポリシーを使用する

#### <a name="can-i-control-line-of-business-lob-apps"></a>基幹業務 (LOB) アプリを制御することはできますか?
はい、アプリのアクセス許可ポリシーを使って、カスタム (LOB) アプリのロールアウトと配布を制御することができます。 ユーザー設定のポリシーを作成するか、またはグローバルポリシーを編集して、組織のニーズに基づいてカスタムアプリを許可またはブロックすることができます。

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>アプリのアクセス許可ポリシーは、固定されたアプリとアプリのセットアップポリシーにどのように関連していますか?

アプリのセットアップポリシーは、アプリのアクセス許可ポリシーと一緒に使うことができます。 事前にピン留めされたアプリは、ユーザーに対して有効になっているアプリのセットから選択されます。 さらに、ユーザーがアプリのセットアップポリシーでアプリをブロックするアプリのアクセス許可ポリシーを持っている場合、そのアプリは Teams に表示されません。

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>アプリのアクセス許可ポリシーを使って、カスタムアプリのアップロードを制限することはできますか?

[**アプリの管理**] ページまたはアプリのセットアップポリシーで、組織全体の設定を使用して、組織のカスタムアプリのアップロードを制限することができます。  

特定のユーザーによるカスタムアプリのアップロードを制限するには、カスタムアプリポリシーを使用します。 詳細については、「 [Teams でカスタムアプリポリシーと設定を管理](teams-custom-app-policies-and-settings.md)する」を参照してください。

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>アプリのブロックは Teams のモバイルクライアントに適用されますか?

はい。アプリをブロックすると、そのアプリはすべてのチームクライアントでブロックされます。  

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>アプリがブロックされると、ユーザーエクスペリエンスはどうなりますか?

ブロックされたアプリやその機能 (ボット、タブ、メッセージング拡張機能など) をユーザーが操作することはできません。 チームやグループチャットなどの共有コンテキストでも、ボットはそのコンテキストの参加者全員にメッセージを送信できます。 アプリがブロックされると、Teams によってユーザーにユーザーが示されます。

たとえば、アプリがブロックされると、ユーザーは次のいずれも実行できません。

- アプリを個人的に、またはチャットやチームに追加する
- アプリのボットにメッセージを送信する
- 操作可能なメッセージなど、情報をアプリに送り戻すボタンアクションを実行します。  
- アプリのタブを表示する
- 通知を受信するためのコネクタを設定する
- アプリのメッセージング拡張機能を使用する

従来のポータルでは、組織レベルでのアプリの制御が許可されています。つまり、アプリがブロックされると、組織内のすべてのユーザーに対してブロックされます。 [[アプリの管理](manage-apps.md)] ページでのアプリのブロックは、まったく同じように動作します。

特定のユーザーに割り当てられているアプリのアクセス許可ポリシーについては、ボットまたはコネクタ機能を備えたアプリが許可され、その後ブロックされた場合に、共有コンテキストの一部のユーザーのみがアプリを許可した場合、そのアプリに対するアクセス許可を持たないグループチャットまたはチャネルのメンバー ボットまたはコネクタによって投稿されたが、操作できないメッセージ履歴とメッセージを表示できます。

## <a name="related-topics"></a>関連項目

- [Teams でのアプリの管理設定](admin-settings.md)
