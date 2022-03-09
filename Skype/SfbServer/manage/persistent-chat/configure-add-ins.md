---
title: 2015 年に常設チャット ルームのアドインをSkype for Business Serverする
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '概要: 2015 年に常設チャット サーバー チャット ルーム用のアドインを構成するSkype for Business Serverします。'
ms.openlocfilehash: 0020c85b5354738083a213e66cc7cc953e5b7e32
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402891"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>2015 年に常設チャット ルームのアドインをSkype for Business Serverする
 
**概要:** 2015 年に常設チャット サーバー チャット ルーム用のアドインを構成するSkype for Business Serverします。
  
アドインは、URL をチャット ルームに関連付け、ルーム内のエクスペリエンスを拡張するために使用されます。 これらの URL は、クライアントの会話機能拡張ウィンドウに表示されます。 一般的なアドインには、株式ティッカーがチャット ルームに投稿され、拡張ウィンドウに在庫履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。 また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。
  
 ユーザーがクライアントでアドインを見る前に、登録されているアドインの一覧にアドインを追加する必要があります。チャット ルームの管理者またはクリエイターは、ルームをアドインに関連付ける必要があります。
  
> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 をSkype for Business Serverします。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>コントロール パネルを使用してチャット ルームのアドインを構成する

コントロール パネルを使用してチャット ルームのアドインを構成するには、次の手順を実行します。
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート **] メニュー** から、[コントロール パネル] Skype for Business Serverを選択するか、ブラウザー ウィンドウを開き、[管理 URL] を入力します。
    
3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。
    
    複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。
    
4. [**アドイン**] ページで、[**新規**] をクリックします。
    
5. [ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。 アドインをプール間で移動したり、複数のプールで共有したりすることはできません。
    
6. [**新規 アドイン**] で、次の操作を実行します。
    
   - [**名前**] に、新しいアドインの名前を指定します。
    
   - [**URL**] で、アドインに関連付ける URL を指定します。 URL は http プロトコルと https プロトコルに制限されます。
    
7. [**確定**] をクリックします。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>アドインを使用してアドインを構成Windows PowerShell

次のコマンドレットを使用して、チャット ルーム用のアドインをWindows PowerShellできます。 使用可能なすべてのパラメーターを含む構文の詳細については、「Skype for Business Server [2015 管理シェル」を参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |新しいアドインを作成する  <br/> |
|Set-CsPersistentChatAddin  <br/> |既存のアドインの設定を構成する  <br/> |
|Get-CsPersistentChatAddin  <br/> |アドインに関する情報を取得する  <br/> |
|Remove-CsPersistentChatAddin  <br/> |アドインを削除する  <br/> |
   
### <a name="create-a-new-add-in"></a>新しいアドインを作成する

**New-CsPersistentChatAddin** コマンドレットを使用して、新しいアドインを作成できます。
  
たとえば、次のコマンドは、プールの新しいアドイン (ITPersistentChatAddin という名前) を作成します `atl-cs-001.contoso.com`。 URL パラメーターとパラメーター値は `http://atl-cs-001.contoso.com/itchat` 、アドインの Web ページの場所を指定します。
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>既存のアドインの設定を構成する

**Set-CsPersistentChatAddIn** コマンドレットを使用して、既存のアドインの設定を構成できます。 たとえば、次のコマンドは、常設チャット アドイン ITPersistentChatAddin に割り当てられた URL を変更します。 この場合、URL は次に変更されます `http://atl-cs-001.contoso.com/itchat2`。
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>アドインに関する情報を取得する

**Get-CsPersistentChatAddin** コマンドレットを使用して、アドインに関する情報を取得できます。 たとえば、次のコマンドは、組織内で使用するように構成されているすべての常設チャット アドインに関する情報を返します。
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>アドインを削除する

**Remove-CsPersistentChatAddIn** コマンドレットを使用してアドインを削除できます。 たとえば、次のコマンドは、プールで見つかった常設チャット アドイン ITChatAddin を削除します `atl-cs-001.contoso.com`。
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


