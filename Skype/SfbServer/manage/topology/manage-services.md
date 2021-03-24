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
description: サービスの状態を表示し、サービスを開始および停止し、サービスのセッションを防止する方法について学習します。
ms.openlocfilehash: 34228a7e1b8cf9ef044d2f1f15c4b1219f795d79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103183"
---
# <a name="manage-services-in-skype-for-business-server"></a>Skype for Business Server でサービスを管理する

Skype for Business Server コントロール パネルを使用して、トポロジで Skype for Business Server を実行しているすべてのコンピューターの一覧を表示し、サービスの状態を表示し、サービスを開始または停止し、サービスのセッションを防止できます。

- [Skype for Business Server を実行しているコンピューターの一覧を表示する](#view-a-list-of-computers-running-skype-for-business-server)
- [Skype for Business のコンピューターで実行されているサービスの状態を表示する](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Skype for Business サービスを開始または停止する](#start-or-stop-skype-for-business-services)
- [サービスのセッションの禁止](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Skype for Business Server を実行しているコンピューターの一覧を表示する

Skype for Business Server コントロール パネルを使用して、トポロジで Skype for Business を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービス状態を確認します。 この一覧は、コンピューター、プール、またはサイトごとに並べ替えることができます。 

1. Skype for Business Server の定義済みの管理役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。 詳細については、「役割ベースのアクセス制御 [(RBAC) for Skype for Business Server」を参照してください](../../plan-your-deployment/security/role-based-access-control-rbac.md)。
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 Skype for Business Server コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じて次のいずれかを実行します。
    - [**コンピューター**]、[**プール**]、または [**サイト**] 列の見出しをクリックし、上矢印または下矢印をクリックして、一覧を並べ変えます。
    - [**更新**] をクリックして、最新の一覧を表示します。
    - 検索フィールドにコンピューター名を入力することで、特定のコンピューターを検索します。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Skype for Business のコンピューターで実行されているサービスの状態を表示する

Skype for Business Server コントロール パネルを使用して、Skype for Business Server トポロジ内の特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックします。
4. [状態] ページで、必要に応じてリストを並べ替えまたは検索して対象のコンピューターを見つけ、そのコンピューター名をクリックします。
5. 次のいずれかの操作を行います。
    - コンピューターで実行されているサービスの最新状態を表示するには、[**サービス状態の取得**] をクリックします。
    - コンピューターで実行されている特定のサービスの一覧および各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックして一覧に戻ります。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用してサービスの状態Windows PowerShell表示する

また、サービスの状態を表示するには、Windows PowerShellコマンドレットをGet-CsWindowsServiceします。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 詳細については [、「Skype for Business Server Management Shell」を参照してください](../management-shell.md)。

**サービス状態を表示するには**

コンピューターでサービスの状態を表示するには、Skype for Business Server 管理シェルに次のようなコマンドを入力し、Enter キーを押します。

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

詳細については [、「Get-CsWindowsService」を参照してください](/powershell/module/skype/Get-CsWindowsService)。

## <a name="start-or-stop-skype-for-business-services"></a>Skype for Business サービスを開始または停止する

Skype for Business Server コントロール パネルを使用して、特定のコンピューターで実行されている Skype for Business Server サービスの開始または停止、または特定のサービスの開始または停止を行います。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>コンピューター上のすべての Skype for Business Server サービスを開始または停止する

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。 CsServerAdministrator または CsAdministrator RBAC の役割が割り当てられているかどうかを確認するには、次のようなコマンドを実行します。

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 Skype for Business Server コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。
5. [**アクション**] をクリックします。
6. [**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。

### <a name="start-or-stop-a-specific-service"></a>特定のサービスを開始または停止する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。
5. [**プロパティ**] をクリックします。
6. 必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。
7. [**アクション**] をクリックします。
8. [**サービスの開始**] または [**サービスの停止**] をクリックします。
9. [**閉じる**] をクリックします。


## <a name="prevent-sessions-for-services"></a>サービスのセッションの禁止

特定のコンピューターで実行されているすべての Skype for Business Server サービスの新しいセッションを防止したり、特定のサービスの新しいセッションを防止したりするには、Skype for Business コントロール パネルを使用します。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>コンピューター上のすべての Skype for Business Server サービスの新しいセッションを防止する

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態] ページで、必要に応じて一覧を並べ替えまたは検索して、新しいセッションを防止するサービスを実行しているコンピューターを検索し、それをクリックします。
5. [**アクション**] をクリックします。
6. [すべての **サービスの新しいセッションを防止する] をクリックします**。

### <a name="prevent-new-sessions-for-a-specific-service"></a>特定のサービスの新しいセッションを防止する

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business Server コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. **[プロパティ]** をクリックします。
5. 必要に応じてサービスの一覧を並べ替え、新しいセッションを防止するサービスをクリックします。
6. [**アクション**] をクリックします。
7. [サービス **の新しいセッションを防止する] をクリックします**。
8. **[閉じる]** をクリックします。