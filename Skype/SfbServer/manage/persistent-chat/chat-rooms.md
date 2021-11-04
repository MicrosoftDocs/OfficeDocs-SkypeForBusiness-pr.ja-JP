---
title: 常設チャット サーバーのチャット ルームを 2015 年Skype for Business Serverする
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '概要: 2015 年に常設チャット サーバー のチャット ルームを管理するSkype for Business Serverします。'
ms.openlocfilehash: 5eb69b3f852ce8e093947cdd04cc00b6bfdc19e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746883"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>常設チャット サーバーのチャット ルームを 2015 年Skype for Business Serverする
 
**概要:** 2015 年に常設チャット サーバー のチャット ルームを管理するSkype for Business Serverします。
  
カテゴリを正しく使用すると、チャット ルームの作成と管理がはるかに簡単になります。 カテゴリは、チャット ルームを作成または参加できるユーザーを定義します。 チャット ルームの管理を試みる前に[、Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)の常設チャット カテゴリ、チャット ルーム、およびユーザーロールを読み、Skype for Business Server [2015](categories.md)の常設チャット サーバーでカテゴリを管理してください。
  
> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 

Windows PowerShell コマンド ライン インターフェイスを使用して、またはチャット ルームのメンバーである場合は Skype for Business クライアントを使用して、チャット ルームを構成および管理できます。 このトピックでは、コマンド ライン インターフェイスを使用してチャット ルームを管理Windows PowerShell説明します。 クライアントを使用してチャット ルームを管理する場合は、Skype for Businessヘルプを参照してください。 
  
チャット ルームには、標準とオーディトリアムの 2 種類のいずれかを指定できます。 通常のチャット ルームでは、すべてのメンバーがメッセージを投稿および読み取りできます。 オーディトリアムは、発表者だけが投稿できるチャット ルームの一種ですが、すべてのユーザーが読み取り可能です。
  
Whoチャット ルームにアクセスおよび管理できる機能は、次のようにユーザーの役割によって異なります。
  
- メッセージを投稿および読み取りするには、ユーザーがチャット ルームのメンバーである必要があります。
    
- 発表者は、講堂の部屋に投稿できます。
    
- 管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。 管理者は、特定のチャット ルームに不適切と見なされるメッセージを削除または置換することもできます。
    
- エンドユーザー (メッセージの作成者を含む) は、チャット ルームのコンテンツを削除できません。
    
- チャット ルームの管理者は、会議室の無効化など、すべてのチャット ルームのプロパティを変更できます。 ただし、管理者はルームを削除したり、ルームのカテゴリを変更したりすることはできません。 
    
- チャット ルームの作成後に削除できるのは、管理者のみです。
    
次のコマンドレットを使用して、チャット ルームを構成Windows PowerShellできます。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成する  <br/> |
|Set-CsPersistentChatRoom  <br/> |既存のルームの設定を構成する。ユーザーとユーザー グループをルームに割り当てる  <br/> |
|Get-CsPersistentChatRoom  <br/> |会議室に関する情報を取得する  <br/> |
|Clear-CsPersistentChatRoom  <br/> |ルームまたはメッセージをルームから消去する  <br/> |
|Remove-CsPersistentChatRoom  <br/> |ルームを削除する  <br/> |
|Remove-CsPersistentChatMessage  <br/> |ルームからメッセージを削除する  <br/> |
   
**New-CsPersistentChatRoom** コマンドレットを使用して、チャット ルームを作成し **、Set-CsPersistentChatRoom** コマンドレットを使用して、ユーザーをチャット ルームに追加するなどの既存のチャット ルームを構成します。 チャット ルームには、次のパラメーターを構成できます。
  
- 無効です。 チャット ルームを無効または有効にできます。 
    
- 招待状。 チャット ルームの招待を有効または無効にできます。これは、チャット ルームのメンバーとして追加されたユーザーに通知するために使用されます。 継承の招待の既定の設定で、チャット ルームが所属するカテゴリに構成された招待設定を採用しました。 チャット ルーム レベルで招待設定を false に構成すると、カテゴリ設定を上書きできます。 
    
- プライバシー。 チャット ルームが Open、Closed、または Secret かどうかを指定できます。 オープン ルームは、誰でも検索してアクセスできます。 閉じた部屋は誰でも検索できますが、メンバーだけがアクセスできます。 シークレット ルームは、ルームのメンバーだけが検索してアクセスできます。 既定では、新しい各ルームは最初は [閉じた] として構成されます。
    
- 型を指定します。 チャット ルームが、メンバーによって投稿されたメッセージを受け入れる標準ルームか、発表者だけが投稿したメッセージを受け入れるオーディトリアム ルームかを指定できます。
    
- Addin。 以前に構成したアドインをチャット ルームに関連付け、参加中にメンバーが URL コンテンツを表示できます。
    
上記のパラメーターに加えて **、Set-CsPersistentChatRoom** コマンドレットを使用すると、次のようにチャット ルームにユーザーを割り当てできます。
  
- メンバー。 チャット ルームのメンバーシップを構成します。 ユーザーの SIP アドレスを指定することで、1 つのコマンドレットを使用して個々のメンバーまたは複数のメンバーを追加または削除できます。 ユーザーを一括で追加するには、Active Directory 組織単位または配布グループを指定することもできます。
    
- マネージャー。 管理者をチャット ルームに割り当てできます。 管理者は、他の設定と共にチャット ルームのメンバーシップを定義する権限を持っています。
    
- 発表者。 発表者をオーディトリアム チャット ルームに割り当てできます。 
    
  すべてのパラメーターを含む構文の詳細については[、「Skype for Business Server 2015 管理シェル」を参照してください](../management-shell.md)。
  
## <a name="create-a-new-room"></a>新しいルームを作成する

**New-CsPersistentChatRoom** コマンドレットを使用して、新しいルームを作成できます。 たとえば、次のコマンドを実行すると、ITChatRoom という名前の新しいチャット ルームがプールに作成 atl-cs-001.contoso.com。 この例では、チャット ルームが IT カテゴリに追加されます。
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**注:** 次のいずれかの条件に当てはまる場合、PersistentChatPoolFqdn は必要ではありません。 
  
- 常設チャット サーバー プールは 1 つのみです。
    
- カテゴリにプール FQDN を提供する。
    
- ルームの追加にプール FQDN を提供する。
    
## <a name="configure-an-existing-room"></a>既存のルームを構成する

**Set-CsPersistentChatRoom** コマンドレットを使用して、既存のルームを構成できます。 たとえば、次のコマンドは、user1 をメンバーおよび発表者として割り当て、user2 を testCat オーディトリアム ルームのマネージャーとして割り当てします。
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 次の例では、アクティブ ディレクトリの NorthAmericaUsers OU のすべてのユーザーを NorthAmerica チャット ルームに追加します。
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

次の例では、Finance 配布グループのすべてのメンバーを同じチャット ルームに追加します。
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>ルームを無効または有効にする

常設チャット ルームのトピックが関連しなくなった場合は、チャット ルームを無効にしてユーザーがチャット ルームを使用できなくなりました。 チャット ルームを無効にすると、すべてのメンバーがルームからすぐに切断されます。 チャット ルームを無効にした後、ユーザーはチャット ルームに再参加したり、チャット ルームの検索でチャット ルームを検索したりすることはできません。
  
チャット ルームの履歴が保持されている場合は、チャット ルームが無効になっているときにコンテンツが保持されます。 ただし、チャット ルームが無効な状態のままの間、そのコンテンツは検索に表示されません。 後でチャット ルームを有効にした場合、ユーザーはチャット ルームが無効にされる前に投稿されたメッセージを検索できます。 チャット ルームの履歴の構成の詳細については[、「Manage categories in Persistent Chat Server in Skype for Business Server 2015」を参照](categories.md)してください。 
  
チャット ルームを無効にすると、メンバーシップ リストとその他の設定が保持されます。 管理者は、無効になっているルームを有効にできます。手動で設定を再作成する必要はありません。
  
**Set-CsPersistentChatRoom** コマンドレットを使用し、Disabled パラメーターを True に設定すると、ルームを無効にすることができます。
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

チャット ルームを有効にするには、Disabled パラメーターを False に設定します。
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>会議室に関する情報を取得する

組織で使用するように構成された会議室に関する情報を取得するには **、Get-CsPersistentChatRoom コマンドレットを使用** できます。
  
次のコマンドは、組織内で使用するように構成されたチャット ルームに関する情報を返します。
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>ルームからすべてのコンテンツを削除する

**Clear-CsPersistentChatRoom** コマンドレットを使用して、ルームからコンテンツを削除できます。 たとえば、次のコマンドは、2015 年 3 月 1 日以前にルームに追加された常設チャット ルーム ITChatRoom からすべてのコンテンツを削除します。
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>ルームからメッセージを削除する

**Remove-CsPersistentChatMessage** コマンドレットを使用して、常設チャット データベース内の 1 つ以上のメッセージを削除し、必要に応じてメッセージを既定のメッセージまたは管理者が提供するメッセージに置き換えできます。 たとえば、次のコマンドは、ユーザーが投稿した ITChatRoom チャット ルームからすべてのメッセージを削除 kenmyer@contoso.com。
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

次の例では、削除されたメッセージを、メッセージが使用できなくなったというメモに置き換える。
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>ルームを削除する

**Remove-CsPersistentChatRoom コマンドレット** を使用して、ルームを削除できます。
  
たとえば、次のコマンドを実行すると、チャット ルーム RedmondChatRoom が削除されます。
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>あるカテゴリから別のカテゴリにルームを移動する

チャット ルーム マネージャーが別のカテゴリ **の Creator** 権限を持っている場合は、あるカテゴリから別のカテゴリにルームを移動できます。 ルームは削除されるのではなく、再作成されます。 データベース内での関連付けの変更です。
  
チャット ルームのカテゴリを変更することはまれに行う必要があります。注意が必要です。 カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。 たとえば、ユーザーがルームのメンバーであり、新しいカテゴリで許可されたメンバーでなくなった場合、ルームメンバーシップが変更され、ユーザーはルームから削除されます。
  

