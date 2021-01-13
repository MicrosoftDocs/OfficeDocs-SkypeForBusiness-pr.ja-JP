---
title: Skype for Business Server でサービスを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: サービスの状態の表示、サービスの開始と停止、およびサービスのセッションの防止を行う方法について学習します。
ms.openlocfilehash: 6071526febcd3a4c1cb925ae3fb704eca6db575c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826317"
---
# <a name="manage-services-in-skype-for-business-server"></a>Skype for Business Server でサービスを管理する

Skype for Business Server コントロール パネルを使用すると、トポロジ内で Skype for Business Server を実行しているすべてのコンピューターの一覧の表示、サービスの状態の表示、サービスの開始または停止、およびサービスのセッションの防止を行えます。

- [Skype for Business Server を実行しているコンピューターの一覧を表示する](#view-a-list-of-computers-running-skype-for-business-server)
- [Skype for Business のコンピューターで実行されているサービスの状態を表示する](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Skype for Business サービスを開始または停止する](#start-or-stop-skype-for-business-services)
- [サービスのセッションの禁止](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Skype for Business Server を実行しているコンピューターの一覧を表示する

Skype for Business Server コントロール パネルを使用して、トポロジ内で Skype for Business を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認します。 この一覧は、コンピューター、プール、またはサイトごとに並べ替えることができます。 

1. Skype for Business Server の定義済みの管理者の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 詳細については [、Skype for Business Server の役割ベースのアクセス制御 (RBAC) を参照してください](../../plan-your-deployment/security/role-based-access-control-rbac.md)。
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じて次のどちらかの操作を行います。
    - [**コンピューター**]、[**プール**]、または [**サイト**] 列の見出しをクリックし、上矢印または下矢印をクリックして、一覧を並べ変えます。
    - [**更新**] をクリックして、最新の一覧を表示します。
    - 検索フィールドにコンピューター名を入力することで、特定のコンピューターを検索します。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Skype for Business のコンピューターで実行されているサービスの状態を表示する

Skype for Business Server のコントロール パネルを使用して、Skype for Business Server トポロジ内の特定のコンピューターで実行しているすべてのサービスを表示し、各サービスの状態を確認します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックします。
4. [状態] ページで、必要に応じてリストを並べ替えまたは検索して対象のコンピューターを見つけ、そのコンピューター名をクリックします。
5. 次のどちらかの操作を行います。
    - コンピューターで実行されているサービスの最新状態を表示するには、[**サービス状態の取得**] をクリックします。
    - コンピューターで実行されている特定のサービスの一覧および各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックして一覧に戻ります。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してサービスの状態を表示する

また、サービスの状態を表示するには、Windows PowerShellコマンドレットをGet-CsWindowsServiceします。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 詳細については [、Skype for Business Server 管理シェル を参照してください](../management-shell.md)。

**サービス状態を表示するには**

コンピューターのサービスの状態を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、Enter キーを押します。

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

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

詳細については [、「Get-CsWindowsService」を参照してください](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。

## <a name="start-or-stop-skype-for-business-services"></a>Skype for Business サービスを開始または停止する

Skype for Business Server コントロール パネルを使用して、特定のコンピューターで実行しているすべての Skype for Business Server サービスを開始または停止したり、特定のサービスを開始または停止したりします。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>コンピューター上のすべての Skype for Business Server サービスを開始または停止する

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。 CsServerAdministrator または CsAdministrator RBAC の役割が割り当てられているかどうかを確認するには、次のようなコマンドを実行します。

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。
5. [**アクション**] をクリックします。
6. [**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。

### <a name="start-or-stop-a-specific-service"></a>特定のサービスを開始または停止する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。
5. [**プロパティ**] をクリックします。
6. 必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。
7. [**アクション**] をクリックします。
8. [**サービスの開始**] または [**サービスの停止**] をクリックします。
9. [**閉じる**] をクリックします。


## <a name="prevent-sessions-for-services"></a>サービスのセッションの禁止

Skype for Business コントロール パネルを使用して、特定のコンピューターで実行しているすべての Skype for Business Server サービスの新しいセッションを回避したり、特定のサービスの新しいセッションを回避したりします。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>コンピューター上のすべての Skype for Business Server サービスに対して新しいセッションを回避する

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じて一覧を並べ替えまたは検索し、新しいセッションを回避するサービスを実行しているコンピューターを見つけてクリックします。
5. [**アクション**] をクリックします。
6. [すべての **サービスに対して新しいセッションを使用できない] をクリックします**。

### <a name="prevent-new-sessions-for-a-specific-service"></a>特定のサービスに対して新しいセッションを回避する

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. **[プロパティ]** をクリックします。
5. 必要に応じてサービスの一覧を並べ替え、新しいセッションを回避するサービスをクリックします。
6. [**アクション**] をクリックします。
7. [サービス **の新しいセッションを回避する] をクリックします**。
8. **[閉じる]** をクリックします。
