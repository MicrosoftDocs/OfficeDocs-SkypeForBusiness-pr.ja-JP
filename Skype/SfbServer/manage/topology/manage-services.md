---
title: Skype for Business Server でサービスを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: サービスの状態の表示、サービスの開始と停止、サービスのセッションの無効化などの方法について説明します。
ms.openlocfilehash: 154c7b2d5ff858e22be4159ec1797ef6a6724445
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817118"
---
# <a name="manage-services-in-skype-for-business-server"></a>Skype for Business Server でサービスを管理する

Skype for Business Server コントロールパネルを使用して、トポロジでの Skype for Business Server を実行しているすべてのコンピューターの一覧を表示したり、サービスの状態を表示したり、サービスを開始または停止したり、サービスのセッションを禁止したりすることができます。

- [Skype for Business Server を実行しているコンピューターの一覧を表示する](#view-a-list-of-computers-running-skype-for-business-server)
- [Skype for Business のコンピューターで実行されているサービスの状態を表示する](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Skype for Business サービスを開始または停止する](#start-or-stop-skype-for-business-services)
- [サービスのセッションの禁止](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Skype for Business Server を実行しているコンピューターの一覧を表示する

Skype for Business Server コントロールパネルを使用して、トポロジで Skype for Business を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認します。 リストは、コンピューター、プール、またはサイトによって並べ替えることができます。 

1. Skype for Business Server の事前定義された管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。 詳細については、「 [Skype For Business Server の役割ベースのアクセス制御 (RBAC)](../../plan-your-deployment/security/role-based-access-control-rbac.md)」を参照してください。
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. [状態] ページで、必要に応じて次のいずれかの操作を行います。
    - **コンピューター**、**プール**、または**サイト**の列見出しをクリックし、上矢印または下矢印をクリックして、リストを並べ替えます。
    - 最新のリストを表示するには、[**更新**] をクリックします。
    - 検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Skype for Business のコンピューターで実行されているサービスの状態を表示する

Skype for Business Server コントロールパネルを使用して、Skype for Business Server トポロジの特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックします。
4. [状態] ページで、必要に応じてリストを並べ替えるか検索して、目的のコンピューターを見つけ、コンピューター名をクリックします。
5. 次のいずれかの操作を行います。
    - コンピューター上で実行されているサービスの最新の状態を表示するには、[**サービスの状態を取得**する] をクリックします。
    - コンピューター上で実行されている特定のサービスの一覧と各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックしてリストに戻ります。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してサービスの状態を表示する

また、Windows PowerShell と、ユーザーの取得-CsWindowsService コマンドレットを使用して、サービスの状態を表示することもできます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。

**サービスの状態を表示するには**

コンピューターでサービスの状態を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、enter キーを押します。

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

このコマンドは、次のような情報を返します。

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

詳細については、「 [CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)」を参照してください。

## <a name="start-or-stop-skype-for-business-services"></a>Skype for Business サービスを開始または停止する

Skype for Business Server コントロールパネルを使用して、特定のコンピューターで実行されているすべての Skype for Business Server サービスを開始または停止するか、特定のサービスを開始または終了します。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>コンピューター上のすべての Skype for Business Server サービスを開始または停止する

1. RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。. 次のようなコマンドを実行すると、CsServerAdministrator または CsAdministrator の RBAC 役割が割り当てられているかどうかを確認できます。

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. [状態] ページで、必要に応じて一覧を並べ替えて検索するか、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。
5. [**アクション**] をクリックします。
6. [**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。

### <a name="start-or-stop-a-specific-service"></a>特定のサービスを開始または停止する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. [状態] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。
5. [**プロパティ**] をクリックします。
6. 必要に応じてサービスの一覧を並べ替え、開始または停止するサービスをクリックします。
7. [**アクション**] をクリックします。
8. [**サービスの開始**] または [**サービスの停止**] をクリックします。
9. [**閉じる**] をクリックします。


## <a name="prevent-sessions-for-services"></a>サービスのセッションの禁止

Skype for Business コントロールパネルを使用して、特定のコンピューターで実行されているすべての Skype for Business Server サービスの新しいセッションを禁止するか、特定のサービスの新しいセッションを禁止します。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>コンピューター上のすべての Skype for Business Server サービスの新しいセッションを禁止する

1. RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
2. ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じて一覧を並べ替えます。または、新しいセッションを禁止するサービスを実行しているコンピューターを検索して、それをクリックします。
5. [**アクション**] をクリックします。
6. [**すべてのサービスに対して新規セッションを**許可しない] をクリックします。

### <a name="prevent-new-sessions-for-a-specific-service"></a>特定のサービスの新しいセッションを禁止する

1. RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
2. ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. [**プロパティ**] をクリックします。
5. 必要に応じてサービスの一覧を並べ替えて、新しいセッションを禁止するサービスをクリックします。
6. [**アクション**] をクリックします。
7. [**サービスの新規セッションを**許可しない] をクリックします。
8. [**閉じる**] をクリックします。
