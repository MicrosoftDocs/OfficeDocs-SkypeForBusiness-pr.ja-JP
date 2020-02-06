---
title: Skype for Business Server 2015 での常設チャット ルームのアドインの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '概要: Skype for Business Server 2015 で常設チャットサーバーチャットルーム用のアドインを構成する方法について説明します。'
ms.openlocfilehash: 01e58422f28d0027114f5bc424f01eb9ef3d9e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817293"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット ルームのアドインの構成
 
**概要:** Skype for Business Server 2015 の常設チャットサーバーチャットルーム用のアドインを構成する方法について説明します。
  
アドインは、URL をチャット ルームと関連付けることでルーム内でのエクスペリエンスを拡張するために使用されます。 これらの URL は、クライアントの会話拡張機能ウィンドウに表示されます。 一般的なアドインには、株式のティッカーがチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれている場合があります。また、拡張機能ウィンドウには、株式履歴が表示されます。 チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。
  
 クライアントでアドインを確認できるようにするには、そのアドインを登録済みアドインのリストに追加する必要があります。さらに、チャット ルームのマネージャーまたは作成者がルームとアドインを関連付ける必要があります。
  
> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>コントロール パネルを使用してチャット ルームのアドインを構成する

コントロール パネルを使用してチャット ルームのアドインを構成するには
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。
    
3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。
    
    複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。
    
4. [**アドイン**] ページで、[**新規**] をクリックします。
    
5. [**サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選びます。 アドインは、プール間で移動したり、異なるプール間で共有したりできません。
    
6. [**新しいアドイン**] で、次の操作を実行します。
    
   - [**名前**] に、新しいアドインの名前を指定します。
    
   - [**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。
    
7. [**確定**] をクリックします。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Windows PowerShell を使用してアドインを構成する

次の Windows PowerShell コマンドレットを使用すると、チャット ルームのアドインを構成できます。使用できるすべてのパラメーターを含む構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |新しいアドインを作成する  <br/> |
|Set-CsPersistentChatAddin  <br/> |既存のアドインの設定を構成する  <br/> |
|Get-CsPersistentChatAddin  <br/> |アドインに関する情報を取得する  <br/> |
|Remove-CsPersistentChatAddin  <br/> |アドインを削除する  <br/> |
   
### <a name="create-a-new-add-in"></a>新しいアドインを作成する

新しいアドインを作成するには、 **CsPersistentChatAddin**コマンドレットを使用します。
  
たとえば、次のコマンドは、プール atl-cs-001.contoso.com の新しいアドイン (name ITPersistentChatAddin) を作成します。 URL パラメーターとパラメーター値http://atl-cs-001.contoso.com/itchatは、アドインの web ページの場所を指定します。
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>既存のアドインの設定を構成する

**Set-CsPersistentChatAddIn** コマンドレットを使用すると、既存のアドインの設定を構成できます。 たとえば、以下のコマンドを実行すると、常設チャット アドイン ITPersistentChatAddin に割り当てられている URL が変更されます。 この場合、URL は次のように変更されます。http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>アドインに関する情報を取得する

**Get-CsPersistentChatAddin** コマンドレットを使用すると、アドインに関する情報を取得できます。たとえば、以下のコマンドを実行すると、組織で使用するために構成されているすべての常設チャット アドインに関する情報が戻されます。
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>アドインを削除する

アドインを削除するには、 **CsPersistentChatAddIn**コマンドレットを使用します。 たとえば、以下のコマンドを実行すると、atl-cs-001.contoso.com 上にある常設チャット アドイン ITChatAddin が削除されます。
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


