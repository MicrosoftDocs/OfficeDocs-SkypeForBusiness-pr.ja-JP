---
title: Skype for Business Server 2015 での常設チャット サーバーのチャット ルームの管理
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '概要: ビジネス サーバー 2015 の Skype で永続的なチャット サーバーのチャット ルームを管理する方法を説明します。'
ms.openlocfilehash: 8764b40651c9872393867ced205c405cfc2d4046
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881731"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーのチャット ルームの管理
 
**の概要:** ビジネス サーバー 2015 の Skype で永続的なチャット サーバーのチャット ルームを管理する方法について説明します。
  
カテゴリを適切に使用すると、チャット ルームの作成と管理が非常に簡単になります。 カテゴリを作成したり、チャット ルームに参加するを定義します。 チャット ルームを管理しようとすると、前に、[永続的なチャット カテゴリ、チャット ルーム、およびビジネス サーバー 2015 の Skype のユーザーの役割](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)と[業務サーバー 2015 の Skype での永続的なチャット サーバーの管理カテゴリ](categories.md)を読み取ることを確認してください。
  
> [!NOTE]
> 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。 

構成し、Windows PowerShell のコマンド ライン インターフェイスを使用するか、ビジネス クライアントのチャット ルームのメンバーである場合、Skype を使用して、チャット ルームを管理できます。 ここでは、Windows PowerShell コマンド ライン インターフェイスを使用してチャット ルームを管理する方法について説明します。 ビジネス クライアント用の Skype を使用してチャット ルームを管理する場合は、クライアントのヘルプを参照してください。 
  
チャット ルームには、次の 2 種類のいずれかを指定できます: 標準および聴衆。 標準チャット ルームでは、すべてのメンバーがメッセージを投稿および閲覧できます。 種類が大会議室のチャット ルームでは、投稿できるのは発表者のみですが、すべてのユーザーが閲覧できますす。
  
チャット ルームにアクセスして管理できるユーザーは、次のように、ユーザーの役割に応じて異なります。
  
- ユーザーがメッセージを投稿および閲覧するには、チャット ルームのメンバーである必要があります。
    
- 発表者は、大会議室ルームに投稿することができます。
    
- 管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。 また、管理者は、特定のチャット ルームにとって不適切と判断されるメッセージを削除または置換することもできます。
    
- エンド ユーザーは、メッセージの作成者を含めて、チャット ルームからコンテンツを削除できません。
    
- チャット ルームのマネージャーは、ルームの無効化を含む、チャット ルームのすべてのプロパティを変更することができます。 ただし、マネージャーは、ルームの削除や、ルームのカテゴリの変更を行うことはできません。 
    
- チャット ルームを削除できるのは管理者のみです。
    
次の Windows PowerShell コマンドレットを使用すると、チャット ルームを構成および管理することができます。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成する  <br/> |
|Set-CsPersistentChatRoom  <br/> |既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる  <br/> |
|Get-CsPersistentChatRoom  <br/> |ルームに関する情報を取得します。  <br/> |
|Clear-CsPersistentChatRoom  <br/> |ルームをクリアするか、ルームからメッセージをクリアする  <br/> |
|Remove-CsPersistentChatRoom  <br/> |ルームを削除する  <br/> |
|Remove-CsPersistentChatMessage  <br/> |ルームからメッセージを削除する  <br/> |
   
**新規 CsPersistentChatRoom**コマンドレットを使用するにはチャット ルームとチャット ルームにユーザーを追加するなど、既存のチャット ルームを構成するのには**一連の CsPersistentChatRoom**コマンドレットを作成します。 チャット ルームには、次のパラメーターを構成することができます。
  
- Disabled。 チャット ルームを有効または無効にすることができます。 
    
- Invitations。 チャット ルームのメンバーとして追加されたユーザーに通知するために使用される、チャット ルームへの招待を有効または無効にすることができます。 招待の既定の設定は継承され、チャット ルームではそれが属するカテゴリで構成されている招待の設定が適用されます。 チャット ルーム レベルで招待の設定を False に構成すると、カテゴリの設定よりも優先させることができます。 
    
- Privacy。 チャット ルームを公開、非公開、秘密のいずれにするかを指定できます。 公開ルームは、すべてのユーザーが検索およびアクセスすることができます。 非公開ルームはすべてのユーザーが検索できますが、アクセスできるのはメンバーに限定されます。 秘密ルームはルームのメンバーのみが検索およびアクセスすることができます。 既定では、新しいルームはすべて、最初は非公開として構成されます。
    
- 入力します。 チャット ルームでは、ルームの通常のことで、任意のメンバーまたは大会議室を持ち、発表者だけが投稿されたメッセージを受け取りますが投稿したメッセージを受け入れるかどうかを指定できます。
    
- アドインです。 以前に構成された追加のメンバーが参加しているときに表示する表示するコンテンツの URL を使用する、チャット ルームに関連付けることができます。
    
**セット CsPersistentChatRoom**コマンドレットでは、上のパラメーターだけでなく次のようにチャット ルームにユーザーを割り当てることができます。
  
- Members。 チャット ルームのメンバーシップを構成します。 ユーザーの SIP アドレスを指定することで、1 つのコマンドレットを使用して個別または複数のメンバーを追加または削除することができます。 ユーザーを一括して追加するために、Active Directory の組織単位や配布グループを指定することもできます。
    
- Managers。 チャット ルームにマネージャーを割り当てることができます。 マネージャーは、他の設定に加えて、チャット ルームのメンバーシップを定義するアクセス許可を持ちます。
    
- Presenters。大会議室チャット ルームに発表者を割り当てることができます。 
    
  すべてのパラメーターを含む構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。
  
## <a name="create-a-new-room"></a>新しいルームを作成する

**New-CsPersistentChatRoom** コマンドレットを使用すると、新しいルームを作成できます。 たとえば、以下のコマンドを実行すると、プール atl-cs-001.contoso.com に ITChatRoom という名前の新しいチャット ルームが作成されます。 この例では、チャット ルームは IT カテゴリに追加されます。
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**注:** 次のいずれかが true の場合、PersistentChatPoolFqdn は必要ありません。 
  
- 1 つのみの永続的なチャット サーバー プールがあります。
    
- カテゴリにプール FQDN を提供する。
    
- ルームの追加にプール FQDN を提供する。
    
## <a name="configure-an-existing-room"></a>既存のルームを構成する

**セット CsPersistentChatRoom**コマンドレットを使用して、既存の領域を設定できます。 たとえば、メンバー、発表者としての user1 と user2 を testCat 大会議室の管理者は、次のコマンドを割り当てます。
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 次の例では、Active Directory の NorthAmericaUsers OU のすべてのユーザーを NorthAmerica チャット ルームに追加します。
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

次の例では、Finance 配布グループのすべてのメンバーを同じチャット ルームに追加します。
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>ルームを無効または有効にする

永続的なチャット ルームのトピックが関連する不要になった場合は、行うことができますチャット ルーム使用できないユーザーを無効にすることによって。 チャット ルームを無効にすると、すべてのメンバーがチャット ルームから即座に切断されます。 チャット ルームを無効にした後、ユーザーは、そのチャット ルームに再び参加することも、チャット ルームを検索することもできません。
  
チャット ルームの履歴が解決しない場合は、チャット ルームが無効になっているコンテンツが保持されます。 ただし、チャット ルームが無効になっている間、コンテンツは検索に表示されません。 チャット ルームを後で有効にすると、ユーザーは、チャット ルームが無効になる前に投稿されたメッセージを検索できます。 チャットの履歴の構成方法の詳細については、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの管理のカテゴリ](categories.md)を参照してください。 
  
チャット ルームを無効にした場合、[メンバーシップ] ボックスの一覧とその他の設定は保持されます。 、管理者として、無効になっている部屋を有効にすることができ、設定を手動で再作成する必要はありません。
  
**セット CsPersistentChatRoom**コマンドレットを使用して、無効なパラメーターを True に設定してルームを無効にすることができます。
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

チャット ルームを有効にするには、Disabled パラメーターを False に設定します。
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>ルームについての情報を取得します。

組織内で使用するように構成されているルームに関する情報を取得するには、**Get-CsPersistentChatRoom** コマンドレットを使用する方法があります。
  
次のコマンドを実行すると、組織で使用するように構成されたすべてのチャット ルームに関する情報を戻します。
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>ルームからすべてのコンテンツを削除する

**Clear-CsPersistentChatRoom** コマンドレットを使用すると、ルームからコンテンツを削除できます。たとえば、以下のコマンドを実行すると、常設チャット ルーム ITChatRoom から、2015 年 3 月 1 日以前にそのルームに追加されたコンテンツがすべて削除されます。
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>ルームからメッセージを削除する

**Remove-CsPersistentChatMessage** コマンドレットを使用すると、常設チャット データベース内の 1 つ以上のメッセージを削除し、オプションで既定のメッセージまたは管理者が指定したメッセージに置き換えることができます。たとえば、次のコマンドを実行すると、ITChatRoom チャット ルームから、ユーザー kenmyer@contoso.com によって投稿されたすべてのメッセージが削除されます。
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

次の例では、その削除されたすべてのメッセージが「削除されました」という通知で置き換えられます。
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>ルームを削除する

**Remove-CsPersistentChatRoom** コマンドレットを使用すると、ルームを削除できます。
  
たとえば、次のコマンドを実行すると、チャット ルーム RedmondChatRoom が削除されます。
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>あるカテゴリから別のカテゴリにチャット ルームを移動する

チャット ルーム マネージャーが別のカテゴリの**作成者**特権を持っている場合、あるカテゴリから別のカテゴリにルームを移動できます。ルームは削除と再作成が行われるのではなく、データベース内で関連付けが変更されます。
  
チャット ルームのカテゴリの変更は、できるだけ行わないようにする必要があり、変更する場合も注意が必要です。カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。たとえば、移動前のルームのメンバーが、新しいカテゴリに移動することにより許可されるメンバーではなくなると、ルームのメンバーシップが変更されて、そのユーザーはルームから削除されます。
  

