---
title: Skype のサービスをビジネス サーバーを管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: サービスの状態を表示、起動し、サービスを停止し、サービスのセッションを防止する方法を説明します。
ms.openlocfilehash: 6913ce2cbef6c12a61d7d4751b35a71371ffb991
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875061"
---
# <a name="manage-services-in-skype-for-business-server"></a>Skype のサービスをビジネス サーバーを管理します。

ビジネス サーバーのコントロール パネルの Skype を使用するにはビジネスのサーバー トポロジでは、Skype を実行しているすべてのコンピューターの一覧を表示、サービスの状態を表示、開始またはサービスを停止およびサービスのセッションを防止します。

- [Skype をビジネスのサーバーを実行しているコンピューターの一覧を表示します。](#view-a-list-of-computers-running-skype-for-business-server)
- [ビジネス用の Skype でのコンピューターで実行されているサービスの状態を表示します。](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [開始または Skype をビジネス ・ サービスの停止](#start-or-stop-skype-for-business-services)
- [サービスのセッションの禁止](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Skype をビジネスのサーバーを実行しているコンピューターの一覧を表示します。

ビジネス サーバーのコントロール パネルの Skype を使用して、トポロジでは、ビジネス用の Skype を実行しているし、それぞれのサービスの状態を表示するすべてのコンピューターの一覧を表示します。 コンピューター、プール、またはサイトでリストを並べ替えることができます。 

1. 、Skype のビジネス サーバーの定義済みの管理者の役割のいずれかに割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 詳細については、 [Skype のビジネス サーバーの役割に基づくアクセス制御 (RBAC)](../../plan-your-deployment/security/role-based-access-control-rbac.md)を参照してください。
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. [状態] ページで、必要に応じて次のいずれかの操作を行います。
    - **コンピューター**、**プール**、または**サイト**列の見出しをクリックし、上向き矢印または下向きの矢印をクリックし、リストを並べ替えます。
    - 最新のリストを表示するのには**更新**をクリックします。
    - 検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>ビジネス用の Skype でのコンピューターで実行されているサービスの状態を表示します。

ビジネス サーバーのコントロール パネルの Skype を使用すると、ビジネスのサーバー トポロジの場合、Skype で特定のコンピューター上で実行され、各サービスの状態を確認するすべてのサービスを表示します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. 、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。 ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。
3. 左側のナビゲーション ・ バーでは、**トポロジー**をクリックします。
4. [状態] ページで、並べ替えやを知り、コンピューターを検索するのには、必要に応じて、リストを検索、[コンピューター名] をクリックします。
5. 次のいずれかの操作を行います。
    - コンピューター上で実行されているサービスの最新の状態を表示するには、**サービスのステータスを取得する**をクリックします。
    - コンピューターと各サービスの状態で実行されている特定のサービスの一覧を表示するには、**プロパティ**] をクリックし、**閉じる**一覧に戻る] をクリックします。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してサービスの状態を表示します。

Windows PowerShell と Get CsWindowsService コマンドレットを使用してサービスの状態を表示することもできます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。 詳細については、 [Skype ビジネス サーバー管理シェル](../management-shell.md)を参照してください。

**サービスの状態を表示するのには**

コンピューターでサービスの状態を表示するのには、Skype のビジネス サーバー管理シェルには、次のようなコマンドを入力し、Enter キーを押します。

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

このコマンドは、次のような情報を返します。

```
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

詳細については、 [Get CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)を参照してください。

## <a name="start-or-stop-skype-for-business-services"></a>開始または Skype をビジネス ・ サービスの停止

開始または停止する特定のコンピューターで実行されているビジネスのサーバー サービスのすべての Skype または開始または特定のサービスを停止するには、ビジネス サーバーのコントロール パネルの Skype を使用します。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>開始またはコンピューターでビジネス サービスのすべての Skype を停止します。

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは. かどうかが割り当てられている、CsServerAdministrator または CsAdministrator の RBAC の役割には、次のようなコマンドを実行することによって判断できます。

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. 状態のページ、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。
5. [**アクション**] をクリックします。
6. **開始のすべてのサービス**または**サービスをすべて停止**] をクリックします。

### <a name="start-or-stop-a-specific-service"></a>開始または特定のサービスを停止します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. 、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。 ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. 状態のページ、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。
5. [**プロパティ**] をクリックします。
6. 必要に応じて、サービスの一覧を並べ替えるし、サービスを開始または停止する] をクリックします。
7. [**アクション**] をクリックします。
8. **サービスを開始**または**停止するサービス**をクリックします。
9. [**閉じる**] をクリックします。


## <a name="prevent-sessions-for-services"></a>サービスのセッションの禁止

ビジネス サーバー サービスが特定のコンピューターで実行されているすべての Skype の新しいセッションを禁止したり、特定のサービスの新しいセッションを防ぐためには、ビジネス コントロール パネルの Skype を使用します。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>ビジネス サービスのコンピューター上のすべての Skype の新しいセッションを禁止します。

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
2. 、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。 ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。
3. 左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。
4. [状態] ページで、並べ替えまたはとしてリストを検索は、新しいセッションを禁止し、クリックするサービスを実行しているコンピューターを検索するのには必要です。
5. [**アクション**] をクリックします。
6. **すべてのサービスの新しいセッションを禁止**] をクリックします。

### <a name="prevent-new-sessions-for-a-specific-service"></a>特定のサービスの新しいセッションを防止します。

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
2. 、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。 ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。
3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。
4. [**プロパティ**] をクリックします。
5. 必要に応じて、サービスの一覧を並べ替えるし、サービスの新しいセッションを禁止する] をクリックします。
6. [**アクション**] をクリックします。
7. **サービスの新しいセッションを禁止**] をクリックします。
8. [**閉じる**] をクリックします。
