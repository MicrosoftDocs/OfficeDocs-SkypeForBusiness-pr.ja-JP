---
title: Skype for Business Server 2015 での常設チャット ルームのアドインの構成
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '概要: は、Skype のビジネス サーバー 2015 の永続的なチャット サーバーのチャット ルームのアドインを構成する方法について説明します。'
ms.openlocfilehash: b43340f44b7ce41a1d77768f10a96bff651afc3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219731"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット ルームのアドインの構成
 
**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのチャット ルームのアドインを構成する方法について説明します。
  
アドインは、URL をチャット ルームと関連付けることでルーム内でのエクスペリエンスを拡張するために使用されます。 これらの URL は、クライアントの会話拡張機能ウィンドウに表示されます。 一般的なアドインでは、株価情報は、チャット ルームがポストされ、拡張機能のウィンドウで株価履歴を表示しますを傍受した Silverlight アプリケーションを指す URL をなどがあります。 チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。
  
 クライアントでアドインを確認できるようにするには、そのアドインを登録済みアドインのリストに追加する必要があります。さらに、チャット ルームのマネージャーまたは作成者がルームとアドインを関連付ける必要があります。
  
> [!NOTE]
> 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>コントロール パネルを使用してチャット ルームのアドインを構成する

コントロール パネルを使用してチャット ルームのアドインを構成するには
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. **[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。
    
3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。
    
    複数の永続的なチャット サーバー プールの展開には、ドロップ ダウン リストから適切なプールを選択します。
    
4. [**アドイン**] ページで、[**新規**] をクリックします。
    
5. [**サービスの選択**] では、アドインを作成する必要がある永続的なチャット サーバー プールに対応するサービスを選択します。 アドインは、プール間で移動したり、異なるプール間で共有したりできません。
    
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

**新規 CsPersistentChatAddin**コマンドレットを使用して、新しいアドインを作成できます。
  
など、新しいアドイン (ITPersistentChatAddin 名) に、プール atl の cs-001.contoso.com の次のコマンドを作成します。 URL パラメーターとパラメーター値http://atl-cs-001.contoso.com/itchatアドインの web ページの場所を指定します。
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>既存のアドインの設定を構成する

**Set-CsPersistentChatAddIn** コマンドレットを使用すると、既存のアドインの設定を構成できます。 たとえば、以下のコマンドを実行すると、常設チャット アドイン ITPersistentChatAddin に割り当てられている URL が変更されます。 URL を変更するこの例では、http://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>アドインに関する情報を取得する

**Get-CsPersistentChatAddin** コマンドレットを使用すると、アドインに関する情報を取得できます。たとえば、以下のコマンドを実行すると、組織で使用するために構成されているすべての常設チャット アドインに関する情報が戻されます。
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>アドインを削除する

**削除 CsPersistentChatAddIn**コマンドレットを使用してアドインを削除できます。 たとえば、以下のコマンドを実行すると、atl-cs-001.contoso.com 上にある常設チャット アドイン ITChatAddin が削除されます。
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


