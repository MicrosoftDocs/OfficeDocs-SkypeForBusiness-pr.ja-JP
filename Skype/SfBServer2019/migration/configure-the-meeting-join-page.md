---
title: 会議参加ページの構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページによって、ユーザーのコンピューターに既にインストールされているクライアントが検出されます。 クライアントがすでにインストールされている場合、そのクライアントが会議を開き、参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
ms.openlocfilehash: c90e8afa95a73618eb1aa95b3d8d174e950e7e92a49988cb6146209f49cc0e58
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295124"
---
# <a name="configure-the-meeting-join-page"></a>会議参加ページの構成

ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページによって、ユーザーのコンピューターに既にインストールされているクライアントが検出されます。 クライアントがすでにインストールされている場合、そのクライアントが会議を開き、参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
  
ユーザーに会議への参加を許可する場合は、会議参加ページの動作を変更できます。 これらの構成オプションはコントロール パネルから削除されましたが、CsWebServiceConfiguration コマンドレットを使用して構成します。
  
**会議参加ページの CsWebServiceConfiguration のパラメーター**

|**CsWebServiceConfiguration のパラメーター**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |True に設定すると、Lync 以外のクライアント アプリケーションを使用して会議に参加するユーザーには、会議に参加する機会が与えられる。 既定値は False です。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。 False (既定値) に設定すると、これらのオプションを使用できますが、ユーザーはオプションの一覧を表示する必要があります。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>2019 管理シェルを使用して会議参加Skype for Business Server構成するには

1. 2019 Skype for Business Server管理シェルを起動する: [スタート]をクリックし、[すべてのプログラム] をクリックし **、[Microsoft Skype for Business Server 2019]** をクリックし、[管理シェルSkype for Business Server]**をクリックします**。
    
2. 次のコマンドレットを実行します。 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    このコマンドレットは、Web サービス構成設定を返します。
    
3. 基本設定に応じて、パラメーターを True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、「Skype for Business Server 管理シェル」のドキュメントを[参照](../../SfbServer/manage/management-shell.md)してください。
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


