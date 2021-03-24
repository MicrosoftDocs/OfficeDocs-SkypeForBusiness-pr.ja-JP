---
title: Skype for Business Server のサービスを管理する
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: この記事では、Skype for Business Server トポロジで実行されているサービスを管理する方法について説明します。
ms.openlocfilehash: d0669eab34795de3241c954f2eda593eda474193
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104383"
---
# <a name="manage-services-for-skype-for-business-server"></a>Skype for Business Server のサービスを管理する

この記事では、Skype for Business Server トポロジで実行されているサービスを管理する方法について説明します。
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Skype for Business Server を実行しているコンピューターの一覧を表示する
<a name="view_list"> </a>

Skype for Business Server コントロール パネルを使用すると、トポロジで Skype for Business Server を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービス状態を確認できます。 この一覧は、コンピューター、プール、またはサイトごとに並べ替えることができます。 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Skype for Business Server を実行しているコンピューターの一覧を表示するには

1. Skype for Business Server の定義済みの管理役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。 Skype for Business Server で使用できる定義済みの管理役割の詳細については、「Planning for Role-Based **アクセス制御」を参照してください**。   
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。   
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。   
4. [**状態**] ページで、必要に応じて、次のいずれかの操作を実行します。
   - [**コンピューター**]、[**プール**]、または [**サイト**] 列の見出しをクリックし、上矢印または下矢印をクリックして、一覧を並べ変えます。 
   - [**更新**] をクリックして、最新の一覧を表示します。  
   - 検索フィールドにコンピューター名を入力することで、特定のコンピューターを検索します。
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Skype for Business サーバーで実行されているサービスの状態を表示する
<a name="view-status"> </a>

Skype for Business Server コントロール パネルを使用すると、Skype for Business Server トポロジ内の特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認できます。
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>コンピューターで実行されているサービスの状態を表示するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3. 左側のナビゲーション バーで [**トポロジ**] をクリックします。 
4. [状態 **] ページで** 、必要に応じてリストを並べ替えまたは検索して、必要なコンピューターを検索し、コンピューター名をクリックします。
5. 次のいずれかの操作を行います。
   - コンピューターで実行されているサービスの最新状態を表示するには、[**サービス状態の取得**] をクリックします。
   - コンピューターで実行されている特定のサービスの一覧および各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックして一覧に戻ります。
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Windows Powershell コマンドレットを使用してサービスの状態を表示する

また、サービスの状態を表示するには、Windows PowerShell **Get-CsWindowsService コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-view-service-status"></a>サービス状態を表示するには

コンピューターでサービスの状態を表示するには、Skype for Business Server 管理シェルに次のようなコマンドを入力し、Enter キーを押します。
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

このコマンドは、次のような情報を返します。
  
|**RoleName**|**状態**|
|:-----|:-----|
|{W3SVC}  <br/> |実行中  <br/> |
|{CentralManagement}  <br/> | 実行中 <br/> |
|{ClsAgent}  <br/> |実行中  <br/> |
|{レジストラー, UserServer, EdgeServer}  <br/> |実行中  <br/> |
|{ApplicationServer}  <br/> |実行中  <br/> |
|{ConferencingServer}  <br/> |実行中  <br/> |
|{MediationServer}  <br/> |実行中  <br/> |
   
詳細については [、「Get-CsWindowsService」を参照してください](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。
  
## <a name="view-details-about-a-service"></a>サービスの詳細を表示する
<a name="view_details"> </a>

Skype for Business Server コントロール パネルを使用して、トポロジ内の特定のコンピューターで実行されている各サービスの詳細を表示できます。 各サービスの状態と、関連付けられたデータベース、ポート、依存サービスなどの詳細を表示できます。
  
### <a name="to-view-details-for-a-service"></a>サービスの詳細を表示するには

1. Skype for Business Server の定義済みの管理役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。 Skype for Business Server で使用できる定義済みの管理役割の詳細については、「Planning for Role-Based **アクセス制御」を参照してください**。
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、一覧を並べ替えるか検索して、表示するコンピューターをクリックします。
5. [**プロパティ**] をクリックします。
6. [**コンピューター詳細の表示**] ウィンドウで、必要な場合はサービスの一覧を並べ替えてから、表示するサービスをクリックします。
7. 必要に応じて、次の操作を実行します。
   - 指定したサービスの最新の状態を表示するには、[**サービスの状態の取得**] をクリックします。
   - 指定したサービスの詳細を表示するには、[**プロパティ**] をクリックしてから、[**閉じる**] をクリックします。
   - トポロジ内のすべてのコンピューターの一覧を返すには、[**閉じる**] をクリックします。
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Skype for Business Server サービスを開始または停止する
<a name="StartStop"> </a>

Skype for Business Server コントロール パネルを使用すると、特定のコンピューターで実行されている Skype for Business Server サービスの開始または停止、または特定のサービスの開始または停止を行えます。
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>コンピューター上のすべての Skype for Business サービスを開始または停止するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。 CsServerAdministrator または CsAdministrator RBAC の役割が割り当てられているかどうかを確認するには、次のようなコマンドを実行します。
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。
5. [**アクション**] をクリックします。
6. [**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。
    
### <a name="to-start-or-stop-a-specific-service"></a>特定のサービスを開始または停止するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。
5. [**プロパティ**] をクリックします。
6. 必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。
7. [**アクション**] をクリックします。
8. [**サービスの開始**] または [**サービスの停止**] をクリックします。
9. [**閉じる**] をクリックします。
    
## <a name="prevent-sessions-for-services"></a>サービスのセッションの禁止
<a name="prevent_session"> </a>

Skype for Business Server コントロール パネルを使用すると、特定のコンピューターで実行されているすべての Skype for Business Server サービスの新しいセッションを防止したり、特定の Skype for Business Server サービスの新しいセッションを防止したりできます。
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>コンピューター上のすべての Skype for Business サービスの新しいセッションを防止するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [状態 **] ページ** で、必要に応じて一覧を並べ替えまたは検索して、新しいセッションを防止するサービスを実行しているコンピューターを検索し、それをクリックします。
5. [**アクション**] をクリックします。
6. [すべての **サービスの新しいセッションを防止する] をクリックします**。
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>特定のサービスの新しいセッションを防止するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。 
5. [**プロパティ**] をクリックします。
6. 必要に応じてサービスの一覧を並べ替え、新しいセッションを防止するサービスをクリックします。
7. [**アクション**] をクリックします。
8. [サービス **の新しいセッションを防止する] をクリックします**。
9. **[閉じる]** をクリックします。
