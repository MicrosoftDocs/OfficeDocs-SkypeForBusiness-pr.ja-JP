---
title: 会議参加ページの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに既にインストールされているクライアントが検出されます。 クライアントが既にインストールされている場合は、そのクライアントが開き、会議に参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
ms.openlocfilehash: 35b8b816d5c01f3061dc697cf7f37a4314a5f083
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813795"
---
# <a name="configure-the-meeting-join-page"></a>会議参加ページの構成

ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに既にインストールされているクライアントが検出されます。 クライアントが既にインストールされている場合は、そのクライアントが開き、会議に参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
  
ユーザーが会議に参加できるようにする場合は、[会議参加] ページの動作を変更することができます。 これらの構成オプションはコントロールパネルから削除されていますが、CsWebServiceConfiguration コマンドレットを使用して設定します。
  
**会議の参加ページの CsWebServiceConfiguration パラメーター**

|**CsWebServiceConfiguration パラメーター**|**説明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加するユーザーには、会議への参加の機会が与えられます。 既定値は False です。  <br/> |
|Showalternatejoinoptionている  <br/> |True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。 False (既定値) に設定した場合、これらのオプションは使用できますが、ユーザーは独自のオプションの一覧を表示する必要があります。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用して会議の参加ページを構成するには

1. Skype for Business Server 2019 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを実行します。 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    このコマンドレットは、web サービスの構成設定を返します。
    
3. 次のコマンドを実行します。設定に応じてパラメーターが True または False に設定されています (このコマンドレットのパラメーターの詳細については、「 [Skype For Business Server 管理シェル](../../SfbServer/manage/management-shell.md)のドキュメント」を参照してください)。
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


