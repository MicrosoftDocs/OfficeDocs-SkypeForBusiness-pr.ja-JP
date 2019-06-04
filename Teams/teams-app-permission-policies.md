---
title: Microsoft Teams のアプリのアクセス許可ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Teams のアプリのアクセス許可ポリシーと、それらを使用して、組織内のユーザーが利用できるアプリを制御する方法について説明します。
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: fac559fb492155af9953beb74c2fac1526f01432
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681922"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのアクセス許可ポリシーを管理する

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> Microsoft Teams でアプリを管理するための現在の方法については、「[組織の Microsoft teams の設定を管理](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)する」を参照してください。

管理者は、アプリのアクセス許可ポリシーを使って、組織内の Microsoft Teams ユーザーが利用できるアプリを制御することができます。 Microsoft、サードパーティ、組織によって公開されたすべてのアプリまたは特定のアプリを許可またはブロックすることができます。 アプリをブロックすると、ユーザーは Teams app store からアプリをインストールできなくなります。

アプリのアクセス許可ポリシーは、Microsoft Teams 管理センターで管理します。 組織全体の設定を適用したり、グローバル (組織全体の既定) ポリシーを使用したり、個々のユーザーまたはグループ内のユーザーにカスタムポリシーを作成して割り当てることができます。  

![アプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies.png)

> [!NOTE]
> 組織内のユーザーは、カスタムポリシーを作成して割り当てる場合を除き、自動的にグローバルポリシーを取得します。 組織全体のアプリ設定は、グローバルポリシーや、作成してユーザーに割り当てるカスタムポリシーを上書きします。

たとえば、すべてのサードパーティ製のアプリをブロックして、組織内の HR チーム向けに Microsoft が提供する特定のアプリを許可する必要があるとします。 HR アプリのアクセス許可ポリシーという名前のカスタムポリシーを作成し、必要なアプリをブロックおよび許可するように設定し、人事チームのユーザーに割り当てます。

## <a name="manage-org-wide-app-settings"></a>組織全体のアプリ設定を管理する

組織全体で利用可能なアプリを管理するには、組織全体のアプリ設定を使います。 組織全体のアプリの設定では、すべてのユーザーに対する動作が管理され、ユーザーに割り当てられている他のアプリのアクセス許可ポリシーは上書きされます。 組織全体のアプリの設定はすぐに有効になり、悪意のあるアプリや問題のあるアプリの制御に使用できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**権限ポリシー**] に移動します。
2. [**組織全体の設定**] を選択します。 次に、パネルで設定を構成することができます。 
![組織全体のアプリ設定のスクリーンショット](media/app-permission-policies-org-wide-settings.png)
3. サード**パーティ**製のアプリで、次の設定を有効または無効にして、サードパーティ製のアプリへのアクセスを制御します。

    - **Teams でサードパーティ製アプリを許可する**: ユーザーがサードパーティ製のアプリを使えるかどうかを制御します。
    - **既定でストアに公開**されている新しいサードパーティのアプリを許可します。これは、teams app store に公開された新しいサードパーティアプリが teams で自動的に使用できるようになるかどうかを制御します。 このオプションを設定するには、サードパーティ製のアプリを許可する必要があります。

4. [**カスタムアプリ**] の下で、[**カスタムアプリとの対話を許可する**] をオンまたはオフにします。 この設定は、ユーザーがカスタム (サイドローディング) アプリを操作できるかどうかを制御します。 これは、ユーザーがカスタムアプリを*アップロード*することを許可することとは異なります。
5. [**ブロックするアプリ**] で、組織全体でブロックするアプリを検索して追加します。 テナントアプリカタログまたは Teams app store からアプリを選ぶことができます。
6. 組織全体のアプリ設定を有効にするには、[**保存**] をクリックします。

## <a name="create-a-custom-app-permission-policy"></a>カスタムアプリのアクセス許可ポリシーを作成する

組織内のユーザーグループごとに使用できるアプリを制御する場合は、1つ以上のカスタムアプリのアクセス許可ポリシーを作成して割り当てます。 Microsoft、サードパーティ、または組織によってアプリが公開されるかどうかに基づいて、個別のカスタムポリシーを作成して割り当てることができます。 組織全体の設定でサードパーティ製のアプリが無効になっている場合は、カスタムポリシーを作成した後に変更することはできないことを知っておくことが重要です。 

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**権限ポリシー**] に移動します。
2. [**新しいポリシー**] を選びます。
    ![新しいアプリのアクセス許可ポリシーのスクリーンショット](media/app-permission-policies-new-policy.png)
3. ポリシーのわかりやすい名前を入力します。
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
7. [**保存**] をクリックします。

## <a name="edit-an-app-permission-policy"></a>アプリのアクセス許可ポリシーを編集する

Microsoft Teams 管理センターを使って、作成するグローバル (組織全体の既定) ポリシーやカスタムポリシーなどのポリシーを編集できます。 

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** > の**権限ポリシー**] に移動します。
2. 編集するポリシーを選択します。
3. ここで、必要な変更を行います。 アプリの発行元に基づいて設定を管理し、許可/禁止の設定に基づいてアプリを追加および削除することができます。
4. [**保存**] をクリックします。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>ユーザーにカスタムアプリのアクセス許可ポリシーを割り当てる

Microsoft Teams 管理センターを使用して、カスタムポリシーを個々のユーザーに割り当てるか、Skype for Business PowerShell モジュールを使用して、セキュリティグループまたは配布グループ内のすべてのユーザーなどのカスタムポリシーを複数のユーザーに割り当てることができます。

> [!IMPORTANT]
> ユーザーにポリシーを割り当てるには、PowerShell を使用することをお勧めします。 Microsoft Teams 管理センターを使って、ポリシーを作成、編集、管理します。

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a>カスタムアプリのアクセス許可ポリシーを個々のユーザーに割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[割り当てられているポリシー]** の隣にある **[編集]** を選択します。
3. [**アプリのアクセス許可ポリシー**] で、割り当てるアプリのアクセス許可ポリシーを選択し、[**保存**] を選択します。

    ![app-setup-permission-assign-policy](media/app-permission-policies-assign-policy.png)

また、次のように、1人または複数のユーザーにアプリのアクセス許可ポリシーを割り当てることもできます。

1. **Microsoft teams 管理センター** > の**teams アプリ** > の**アクセス許可ポリシー**に移動します。
2. ポリシー名の左側をクリックして、ポリシーを選択します。
3. [**ユーザーの管理**] を選びます。
4. [**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、[**保存**] を選択します。
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>カスタムアプリのアクセス許可ポリシーをグループ内のユーザーに割り当てる

カスタムアプリのアクセス許可ポリシーは、既に指定した複数のユーザーに割り当てることができます。 たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。 これを行うには、Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続します。 PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。

この例では、Contoso 製薬 HR プロジェクトグループ内のすべてのユーザーに HR アプリのアクセス許可ポリシーと呼ばれるカスタムアプリのアクセス許可ポリシーを割り当てます。  

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
グループ内のすべてのユーザーに特定のアプリのアクセス許可ポリシーを割り当てます。 この例では、HR アプリのアクセス許可ポリシーです。
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>アプリのアクセス許可ポリシーを使用する

#### <a name="can-i-control-line-of-business-lob-apps"></a>基幹業務 (LOB) アプリを制御することはできますか?

はい、アプリのアクセス許可ポリシーを使って、カスタム (LOB) アプリのロールアウトと配布を制御することができます。

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>アプリのアクセス許可ポリシーは、固定されたアプリとアプリのセットアップポリシーにどのように関連していますか?

アプリのセットアップポリシーは、アプリのアクセス許可ポリシーと一緒に使うことができます。 事前にピン留めされたアプリは、ユーザーに対して有効になっているアプリのセットから選択されます。 さらに、ユーザーがアプリのセットアップポリシーでアプリをブロックするアプリのアクセス許可ポリシーを持っている場合、そのアプリは Teams に表示されません。

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>アプリのアクセス許可ポリシーを使って、(サイドローディングとも呼ばれる) カスタムアプリのアップロードを制限することはできますか?

カスタムアプリのアップロードを制限する方法の詳細については、「 [Teams でカスタムアプリポリシーと設定を管理](teams-custom-app-policies-and-settings.md)する」を参照してください。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>ポリシーの変更が有効になるまでにはどのくらいの時間がかかりますか?

グローバルポリシーを編集するか、ポリシーをユーザーに割り当てると、変更が有効になるまで最大24時間かかることがあります。 組織全体のアプリの設定はすぐに有効になります。

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

 ## <a name="related-topics"></a>関連トピック
- [Teams でのアプリの管理設定](admin-settings.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
- [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
