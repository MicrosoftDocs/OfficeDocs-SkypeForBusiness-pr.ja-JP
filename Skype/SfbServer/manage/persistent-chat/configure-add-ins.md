---
title: Skype for Business Server 2015 での常設チャット ルームのアドインの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '概要: Skype for Business Server 2015 で常設チャット サーバーのチャット ルーム用のアドインを構成する方法について学習します。'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815083"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット ルームのアドインの構成
 
**概要:** Skype for Business Server 2015 で常設チャット サーバーのチャット ルーム用のアドインを構成する方法について学習します。
  
アドインは、URL をチャット ルームに関連付け、ルーム内のエクスペリエンスを拡張するために使用されます。 これらの URL は、クライアントの会話機能拡張ウィンドウに表示されます。 一般的なアドインには、株価情報がチャット ルームに投稿され、拡張ウィンドウに株価履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。 また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。
  
 ユーザーがクライアントでアドインを表示するには、登録されているアドインの一覧にアドインを追加する必要があります。チャット ルームのマネージャーまたは作成者はルームをアドインに関連付ける必要があります。
  
> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>コントロール パネルを使用してチャット ルームのアドインを構成する

コントロール パネルを使用してチャット ルームのアドインを構成するには:
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。
    
3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。
    
    複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。
    
4. [**アドイン**] ページで、[**新規**] をクリックします。
    
5. [ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。 アドインをプール間で移動したり、複数のプールで共有したりすることはできません。
    
6. [**新規 アドイン**] で、次の操作を実行します。
    
   - [**名前**] に、新しいアドインの名前を指定します。
    
   - [**URL**] で、アドインに関連付ける URL を指定します。 URL は http プロトコルと https プロトコルに制限されます。
    
7. [**確定**] をクリックします。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>アドインを使用してアドインを構成Windows PowerShell

次のコマンドレットを使用して、チャット ルームのアドインWindows PowerShellできます。 使用可能なすべてのパラメーターを含む構文の詳細については [、Skype for Business Server 2015 管理シェルを参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |新しいアドインを作成する  <br/> |
|Set-CsPersistentChatAddin  <br/> |既存のアドインの設定を構成する  <br/> |
|Get-CsPersistentChatAddin  <br/> |アドインに関する情報を取得する  <br/> |
|Remove-CsPersistentChatAddin  <br/> |アドインを削除する  <br/> |
   
### <a name="create-a-new-add-in"></a>新しいアドインを作成する

**New-CsPersistentChatAddin** コマンドレットを使用して、新しいアドインを作成できます。
  
たとえば、次のコマンドを実行すると、プール プールの新しいアドイン (ITPersistentChatAddin という名前) が作成atl-cs-001.contoso.com。 URL パラメーターとパラメーター値は http://atl-cs-001.contoso.com/itchat 、アドインの Web ページの場所を指定します。
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>既存のアドインの設定を構成する

**Set-CsPersistentChatAddIn** コマンドレットを使用して、既存のアドインの設定を構成できます。 たとえば、次のコマンドは、常設チャット アドイン ITPersistentChatAddin に割り当てられている URL を変更します。 この場合、URL は次の値に変更されます。 http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>アドインに関する情報を取得する

**Get-CsPersistentChatAddin** コマンドレットを使用して、アドインに関する情報を取得できます。 たとえば、次のコマンドを実行すると、組織で使用するように構成された常設チャット アドインに関する情報が戻されます。
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>アドインを削除する

**Remove-CsPersistentChatAddIn** コマンドレットを使用してアドインを削除できます。 たとえば、次のコマンドを実行すると、プール プールにある常設チャット アドイン ITChatAddin が削除atl-cs-001.contoso.com。
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


