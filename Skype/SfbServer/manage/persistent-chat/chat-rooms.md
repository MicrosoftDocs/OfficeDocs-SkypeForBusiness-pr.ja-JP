---
title: Skype for Business Server 2015 での常設チャット サーバーでのチャット ルームの管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '概要: Skype for Business Server 2015 で常設チャット サーバーのチャット ルームを管理する方法について学習します。'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815107"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーでのチャット ルームの管理
 
**概要:** Skype for Business Server 2015 で常設チャット サーバーのチャット ルームを管理する方法について学習します。
  
カテゴリを正しく使用すると、チャット ルームの作成と管理がはるかに簡単になります。 カテゴリは、チャット ルームを作成または参加できるユーザーを定義します。 チャット ルームを管理する前に [、Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) の常設チャット カテゴリ、チャット ルーム、およびユーザーの役割と [、Skype for Business Server 2015](categories.md)の常設チャット サーバーのカテゴリの管理を必ずお読みください。
  
> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 

Windows PowerShell コマンドライン インターフェイスを使用するか、チャット ルームのメンバーである場合は Skype for Business クライアントを使用して、チャット ルームを構成および管理できます。 このトピックでは、カスタム コマンド ライン インターフェイスを使用してチャット ルームをWindows PowerShell方法について説明します。 Skype for Business クライアントを使用してチャット ルームを管理する場合は、クライアントのヘルプを参照してください。 
  
チャット ルームには、標準と大会議室の 2 種類のいずれかを使用できます。 標準チャット ルームでは、すべてのメンバーがメッセージを投稿および読み取りできます。 大講堂は、発表者だけが投稿できるが、すべてのユーザーが読み取り可能なチャット ルームの一種です。
  
チャット ルームにアクセスして管理できるユーザーは、次のようにユーザーロールによって異なります。
  
- ユーザーがメッセージを投稿および読み取りするには、チャット ルームのメンバーである必要があります。
    
- 発表者は大会議室に投稿できます。
    
- 管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。 管理者は、特定のチャット ルームに対して不適切と見なされるメッセージを削除または置換することもできます。
    
- エンドユーザー (メッセージの作成者を含む) は、チャット ルームのコンテンツを削除できません。
    
- チャット ルームマネージャーは、ルームの無効化を含め、すべてのチャット ルームのプロパティを変更できます。 ただし、マネージャーは、ルームを削除したり、ルームのカテゴリを変更したりすることはできません。 
    
- チャット ルームの作成後に削除できるのは管理者のみです。
    
次のコマンドレットを使用して、チャット ルームをWindows PowerShellできます。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成する  <br/> |
|Set-CsPersistentChatRoom  <br/> |既存のルームの設定を構成します。ユーザーとユーザー グループをルームに割り当てる  <br/> |
|Get-CsPersistentChatRoom  <br/> |ルームに関する情報を取得する  <br/> |
|Clear-CsPersistentChatRoom  <br/> |ルームまたはメッセージをルームから消去する  <br/> |
|Remove-CsPersistentChatRoom  <br/> |ルームを削除する  <br/> |
|Remove-CsPersistentChatMessage  <br/> |ルームからメッセージを削除する  <br/> |
   
**New-CsPersistentChatRoom** コマンドレットを使用してチャット ルームを作成し **、Set-CsPersistentChatRoom** コマンドレットを使用して、チャット ルームへのユーザーの追加など、既存のチャット ルームを構成します。 チャット ルームには、次のパラメーターを構成できます。
  
- 無効。 チャット ルームを無効または有効にできます。 
    
- 招待。 チャット ルームへの招待を有効または無効にできます。チャット ルームの招待は、チャット ルームのメンバーとして追加されたユーザーに通知するために使用されます。 継承された招待の既定の設定。チャット ルームは、所属するカテゴリで構成された招待設定を採用します。 チャット ルーム レベルで招待の設定を false に構成すると、カテゴリ設定を上書きできます。 
    
- プライバシー。 チャット ルームを開く、閉じている、またはシークレットにするかどうかを指定できます。 オープン ルームは、だれでも検索およびアクセスできます。 クローズ ルームは、だれでも検索できますが、メンバーだけがアクセスできます。 秘密ルームは、ルームのメンバーだけが検索およびアクセスできます。 既定では、新しい各ルームは最初は Closed として構成されています。
    
- 型。 チャット ルームが、任意のメンバーによって投稿されたメッセージを受け入れる通常のルームか、発表者だけが投稿したメッセージを受け入れる講堂ルームかを指定できます。
    
- アドイン。 以前に構成したアドインをチャット ルームに関連付け、参加中にメンバーが URL コンテンツを表示できます。
    
上記のパラメーターに加えて **、Set-CsPersistentChatRoom** コマンドレットを使用すると、次のようにチャット ルームにユーザーを割り当てできます。
  
- メンバー。 チャット ルームのメンバーシップを構成します。 ユーザーの SIP アドレスを指定することで、1 つのコマンドレットを使用して、個々のメンバーまたは複数のメンバーを追加または削除できます。 ユーザーを一括で追加するために、Active Directory 組織単位または配布グループを指定することもできます。
    
- マネージャー。 チャット ルームにマネージャーを割り当てできます。 マネージャーは、他の設定と共にチャット ルームのメンバーシップを定義するアクセス許可を持っています。
    
- 発表者。 発表者を大室のチャット ルームに割り当てできます。 
    
  すべてのパラメーターを含む構文の詳細については [、Skype for Business Server 2015 管理シェルを参照してください](../management-shell.md)。
  
## <a name="create-a-new-room"></a>新しいルームを作成する

**New-CsPersistentChatRoom** コマンドレットを使用して、新しいルームを作成できます。 たとえば、次のコマンドを実行すると、ITChatRoom という名前の新しいチャット ルームがプール に作成atl-cs-001.contoso.com。 この例では、チャット ルームが IT カテゴリに追加されます。
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**注:** 次のいずれかの条件に当てはまる場合、PersistentChatPoolFqdn は必要ではありません。 
  
- 常設チャット サーバー プールは 1 つのみです。
    
- カテゴリにプール FQDN を提供する。
    
- ルームの追加にプール FQDN を提供する。
    
## <a name="configure-an-existing-room"></a>既存のルームを構成する

**Set-CsPersistentChatRoom** コマンドレットを使用して、既存のルームを構成できます。 たとえば、次のコマンドは、user1 をメンバーおよび発表者として割り当て、user2 を管理者として testCat 講堂ルームに割り当てるとします。
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 次の例では、Active Directory の NorthAmericaUsers OU のすべてのユーザーを NorthAmerica チャット ルームに追加します。
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

次の例では、Finance 配布グループのすべてのメンバーを同じチャット ルームに追加します。
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>ルームを無効または有効にする

常設チャット ルームのトピックが不要になった場合は、チャット ルームを無効にすることで、ユーザーがチャット ルームを使用不能にできます。 チャット ルームが無効になっていると、すべてのメンバーは直ちにルームから切断されます。 チャット ルームを無効にすると、ユーザーはチャット ルームに再び参加したり、チャット ルームの検索でチャット ルームを見つけたりできなくなります。
  
チャット ルームの履歴が保持される場合、チャット ルームが無効な場合、コンテンツは保持されます。 ただし、チャット ルームが無効な状態の間、そのコンテンツは検索に表示されません。 後でチャット ルームを有効にした場合、ユーザーはチャット ルームが無効にされる前に投稿されたメッセージを検索できます。 チャット ルーム履歴の構成の詳細については [、「Manage categories in Persistent Chat Server in Skype for Business Server 2015」](categories.md)を参照してください。 
  
チャット ルームを無効にすると、メンバーシップ リストとその他の設定が保持されます。 管理者は、無効になっているルームを有効にできます。設定を手動で作成し変える必要はありません。
  
**Set-CsPersistentChatRoom** コマンドレットを使用し、Disabled パラメーターを True に設定することで、ルームを無効にできます。
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

チャット ルームを有効にするには、Disabled パラメーターを False に設定します。
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>ルームに関する情報を取得する

組織で使用するように構成されたルームに関する情報を取得するには **、Get-CsPersistentChatRoom コマンドレットを使用** できます。
  
次のコマンドは、組織で使用するように構成されたチャット ルームすべてに関する情報を戻します。
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>ルームからすべてのコンテンツを削除する

**Clear-CsPersistentChatRoom** コマンドレットを使用して、ルームからコンテンツを削除できます。 たとえば、次のコマンドは、2015 年 3 月 1 日以前にルームに追加された常設チャット ルーム ITChatRoom からすべてのコンテンツを削除します。
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>ルームからメッセージを削除する

**Remove-CsPersistentChatMessage** コマンドレットを使用して、常設チャット データベース内の 1 つ以上のメッセージを削除し、必要に応じてそのメッセージを既定のメッセージまたは管理者が指定したメッセージに置き換える方法があります。 たとえば、次のコマンドは、ユーザーが投稿した ITChatRoom チャット ルームからすべてのメッセージを削除kenmyer@contoso.com。
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

次の例では、削除されたメッセージを、メッセージが使用できなくなったというメモに置き換える。
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>ルームを削除する

**Remove-CsPersistentChatRoom** コマンドレットを使用して、ルームを削除できます。
  
たとえば、次のコマンドを実行すると、チャット ルーム RedmondChatRoom が削除されます。
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>あるカテゴリから別のカテゴリにルームを移動する

チャット ルーム マネージャーが別のカテゴリの作成者特権を持っている場合、ルームをカテゴリ間で移動できます。 ルームは削除されるのではなく、再作成されます。 データベース内での関連付けの変更です。
  
チャット ルームのカテゴリの変更は、ほとんど行わず、慎重に行う必要があります。 カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。 たとえば、ユーザーがルームのメンバーであり、新しいカテゴリで許可されなくなったメンバーである場合、ルームのメンバーシップが変更され、ユーザーはルームから削除されます。
  

