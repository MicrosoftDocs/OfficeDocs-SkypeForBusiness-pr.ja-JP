---
title: Skype for Business Server のサービスを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: この記事では、Skype for Business Server のトポロジで実行されているサービスを管理する方法について説明します。
ms.openlocfilehash: 9d1a79226422da57eee36e27590769f76b89b560
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279621"
---
# <a name="manage-services-for-skype-for-business-server"></a>Skype for Business Server のサービスを管理する

この記事では、Skype for Business Server のトポロジで実行されているサービスを管理する方法について説明します。
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Skype for Business Server を実行しているコンピューターの一覧を表示する
<a name="view_list"> </a>

Skype for Business Server コントロールパネルを使用して、トポロジで Skype for Business Server を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認することができます。 リストは、コンピューター、プール、またはサイトによって並べ替えることができます。 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Skype for Business Server を実行しているコンピューターの一覧を表示するには

1. Skype for Business Server の事前定義された管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。 Skype for Business Server で利用可能な定義済みの管理者ロールの詳細については、「**ロールベースのアクセス制御の計画**」を参照してください。   
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。   
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。   
4. [**状態**] ページで、必要に応じて次のいずれかの操作を行います。
   - **コンピューター**、**プール**、または**サイト**の列見出しをクリックし、上矢印または下矢印をクリックして、リストを並べ替えます。 
   - 最新のリストを表示するには、[**更新**] をクリックします。  
   - 検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Skype for Business server で実行されているサービスの状態を表示する
<a name="view-status"> </a>

Skype for Business Server コントロールパネルを使用して、Skype for Business Server のトポロジに含まれる特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認することができます。
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>コンピューターで実行されているサービスの状態を表示するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックします。 
4. [**状態**] ページで、必要に応じてリストを並べ替えるか検索して、目的のコンピューターを見つけ、コンピューター名をクリックします。
5. 次のいずれかの操作を実行します。
   - コンピューター上で実行されているサービスの最新の状態を表示するには、[**サービスの状態を取得**する] をクリックします。
   - コンピューター上で実行されている特定のサービスの一覧と各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックしてリストに戻ります。
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Windows Powershell コマンドレットを使用してサービスの状態を表示する

また、Windows PowerShell と、ユーザーの**取得-CsWindowsService**コマンドレットを使用して、サービスの状態を表示することもできます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-view-service-status"></a>サービスの状態を表示するには

コンピューターでサービスの状態を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、enter キーを押します。
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

このコマンドは、次のような情報を返します。
  
|**RoleName**|**状態**|
|:-----|:-----|
|W3SVC  <br/> |実行  <br/> |
|{CentralManagement}  <br/> | 実行 <br/> |
|{ClsAgent}  <br/> |実行  <br/> |
|{レジストラー、UserServer、EdgeServer}  <br/> |実行  <br/> |
|{ApplicationServer}  <br/> |実行  <br/> |
|{ConferencingServer}  <br/> |実行  <br/> |
|{MediationServer}  <br/> |実行  <br/> |
   
詳細については、「 [CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)」を参照してください。
  
## <a name="view-details-about-a-service"></a>サービスについての詳細を表示する
<a name="view_details"> </a>

Skype for Business Server コントロールパネルを使うと、トポロジ内の特定のコンピューターで実行されている各サービスの詳細を表示できます。 各サービスの状態と、関連するデータベース、ポート、依存サービスなどの詳細を表示できます。
  
### <a name="to-view-details-for-a-service"></a>サービスの詳細を表示するには

1. Skype for Business Server の事前定義された管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。 Skype for Business Server で利用可能な定義済みの管理者ロールの詳細については、「**ロールベースのアクセス制御の計画**」を参照してください。
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、リストを並べ替えるか検索して、表示するコンピューターをクリックします。
5. [**プロパティ**] をクリックします。
6. [**コンピューターの詳細の表示**] ウィンドウで、必要に応じてサービスの一覧を並べ替えて、表示するサービスをクリックします。
7. 必要に応じて、次のいずれかの操作を行います。
   - 特定のサービスの最新の状態を表示するには、[**サービスの状態を取得**する] をクリックします。
   - 特定のサービスの詳細を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックします。
   - トポロジに含まれるすべてのコンピューターの一覧に戻るには、[**閉じる**] をクリックします。
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Skype for Business Server サービスを開始または停止する
<a name="StartStop"> </a>

Skype for Business Server コントロールパネルを使用すると、特定のコンピューターで実行されているすべての Skype for Business Server サービスを開始または停止することができます。また、特定のサービスを開始または停止することもできます。
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>コンピューター上のすべての Skype for Business サービスを開始または停止するには

1. RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。. 次のようなコマンドを実行すると、CsServerAdministrator または CsAdministrator の RBAC 役割が割り当てられているかどうかを確認できます。
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、必要に応じて一覧を並べ替えて検索するか、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。
5. [**アクション**] をクリックします。
6. [**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。
    
### <a name="to-start-or-stop-a-specific-service"></a>特定のサービスを開始または停止するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。
5. [**プロパティ**] をクリックします。
6. 必要に応じてサービスの一覧を並べ替え、開始または停止するサービスをクリックします。
7. [**アクション**] をクリックします。
8. [**サービスの開始**] または [**サービスの停止**] をクリックします。
9. [**閉じる**] をクリックします。
    
## <a name="prevent-sessions-for-services"></a>サービスのセッションの禁止
<a name="prevent_session"> </a>

Skype for Business Server コントロールパネルを使用すると、特定のコンピューターで実行されているすべての Skype for Business Server サービスの新しいセッションを禁止したり、特定の Skype for Business Server サービスの新しいセッションを禁止したりすることができます。
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>コンピューター上のすべての Skype for Business サービスの新しいセッションを禁止するには

1. RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、必要に応じて一覧を並べ替えます。または、新しいセッションを禁止するサービスを実行しているコンピューターを検索して、それをクリックします。
5. [**アクション**] をクリックします。
6. [**すべてのサービスに対して新規セッションを**許可しない] をクリックします。
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>特定のサービスの新しいセッションを禁止するには

1. RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3. 左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。
4. [**状態**] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。 
5. [**プロパティ**] をクリックします。
6. 必要に応じてサービスの一覧を並べ替えて、新しいセッションを禁止するサービスをクリックします。
7. [**アクション**] をクリックします。
8. [**サービスの新規セッションを**許可しない] をクリックします。
9. [**閉じる**] をクリックします。
    

