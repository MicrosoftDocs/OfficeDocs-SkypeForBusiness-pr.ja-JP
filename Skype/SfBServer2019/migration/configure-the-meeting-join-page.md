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
description: ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページがユーザーのコンピューターに既にインストールされているクライアントを検出します。 クライアントがすでにインストールされている場合、そのクライアントが会議を開き、参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754027"
---
# <a name="configure-the-meeting-join-page"></a>会議参加ページの構成

ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページがユーザーのコンピューターに既にインストールされているクライアントを検出します。 クライアントがすでにインストールされている場合、そのクライアントが会議を開き、参加します。 クライアントがインストールされていない場合は、既定で Web アプリが開きます。
  
ユーザーが会議に参加できるようにする場合は、会議参加ページの動作を変更することができます。 これらの構成オプションは、コントロールパネルから削除されましたが、Set-cswebserviceconfiguration コマンドレットを使用して構成します。
  
**会議参加ページの CsWebServiceConfiguration のパラメーター**

|**CsWebServiceConfiguration のパラメーター**|**説明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加しているユーザーには、会議に参加する機会が与えられます。 既定値は False です。  <br/> |
|Showalternatejoinoptionsexpan  <br/> |True に設定すると、オンライン会議への代替オプションが自動的に展開され、ユーザーに表示されます。 False (既定値) に設定すると、これらのオプションは使用可能になりますが、ユーザーは自分のオプションの一覧を表示する必要があります。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用して会議参加ページを構成するには

1. Skype for Business Server 2019 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを実行します。 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    このコマンドレットは、Web サービス構成設定を返します。
    
3. ユーザーの設定に応じて、パラメーターを True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、「 [Skype For Business Server Management Shell](../../SfbServer/manage/management-shell.md) 」のドキュメントを参照してください)。
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


