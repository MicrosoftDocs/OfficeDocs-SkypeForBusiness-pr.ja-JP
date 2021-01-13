---
title: Skype for Business Server 2015 での常設チャット サーバーのカテゴリの管理
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
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '概要: Skype for Business Server 2015 で常設チャット サーバーのカテゴリを管理する方法について学習します。'
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815127"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーのカテゴリの管理
 
**概要:** Skype for Business Server 2015 で常設チャット サーバーのカテゴリを管理する方法について学習します。
  
カテゴリは、チャット ルームを整理する論理構造です。 カテゴリは、チャット ルームを作成またはチャット ルームに参加できるユーザーおよびユーザー グループを制御するためのアクセス制御リスト (ACL) の既定のセットを定義します。 チャット ルームカテゴリにはチャット ルームが含まれますが、他のカテゴリは含めではありません。 各カテゴリには、名前や説明などのメタデータを使用してカテゴリの内容が記述されます。 カテゴリには、カテゴリに属するチャット ルームの動作を制御するために設定できるプロパティがあります。たとえば、チャット ルームで招待またはファイルのアップロードを許可するか、チャット履歴を含めます。 
  
カテゴリを正しく使用すると、チャット ルームの作成と管理がはるかに簡単になります。 常設チャット サーバー管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作も定義できます。 たとえば、カテゴリの AllowedMembers を contoso.com に設定した場合、Contoso の任意のグループまたはユーザーをそのカテゴリのチャット ルームにメンバーとして追加できます。 カテゴリの許可メンバーを Sales に設定すると、この配布リスト内のグループとユーザーのみをそのカテゴリのチャット ルームにメンバーとして追加できます。 Creators プロパティを使用すると、そのカテゴリにチャット ルームを作成できるユーザーを制御できます。 チャット ルームが作成されると、AllowedMembers グループのユーザーは、ルームで進行中の管理操作 (メンバーシップの変更や承認など) のマネージャーとして指定できます。
  
カテゴリの AllowedMembers と Creators を定義すると、次の利点が得られます。
  
- カテゴリ内のすべてのチャット ルームがカテゴリ レベルの制限のセットにバインドされます。これにより、業務ニーズとアクセス ポリシーに基づいてチャット ルームを分離できます。
    
- Creators の一覧に含まれるユーザーが、カテゴリ内に新しいチャット ルームを作成できます。 制限された数の組織内の担当者がチャット ルームを作成できるシステムを実装する場合、このコントロールを使用してその要件を満たします。 
    
カテゴリの作成者として識別されるユーザー、組織単位 (US)、およびユーザー グループは、カテゴリにルームを作成できる唯一の個人およびグループです。 カテゴリを作成したら、カテゴリの AllowedMembers リストからユーザー、US、およびユーザー グループをチャット ルームのマネージャーおよびメンバーとして選択し、ルームを管理および参加できます。 
  
カテゴリを構成する前に [、Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)の常設チャットカテゴリ、チャット ルーム、およびユーザーロールを必ずお読みください。
  
コントロール パネルを使用するか、次のコマンドレットを使用して、カテゴリをWindows PowerShellできます。

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 
  
## <a name="configure-categories-by-using-the-control-panel"></a>コントロール パネルを使用してカテゴリを構成する

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。
    
3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。
    
    複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。
    
4. [**分類**] ページで、[**新規**] または [**編集**] をクリックします。
    
5. [ **サービスの選択]** で、カテゴリを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。 このサービスは、常設チャット クライアントがカテゴリが属するプールを識別するために使用する常設チャット サーバー プールです。 カテゴリは 1 つの常設チャット サーバー プールにのみ属し、別のプールに移動したり、別のプールと共有したりすることはできません。
    
6. [**新規 分類**] で、次の操作を実行します。
    
   - [**名前**] に、新しいルーム カテゴリの名前を指定します。
    
   - [**説明**] に、ルーム カテゴリの説明 (Contoso 用のルーム カテゴリなど) を詳しく指定します。
    
   - このカテゴリに属するチャット ルームに対して招待を有効にできるかどうかを制御するには、[招待を有効にする] チェック ボックス **をオンまたは** オフにします。 選択した場合、このカテゴリのルームには招待がオンまたはオフの場合があります。オフにした場合、このカテゴリのルームには招待を許可されません。 ルームに招待がある場合、新しいメンバーがルームに追加された場合、常設チャット クライアントで新しいルームの通知を受け取ります。
    
   - このカテゴリに属するチャット ルームでのファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合は、このカテゴリのルームではファイルのアップロードを有効または無効にできます。オフにした場合は、このカテゴリのルームではファイルのアップロードを有効にできません。
    
   - チャット履歴を制御するには、[チャット履歴を有効にする] **チェック ボックスをオンまたは** オフにします。 オンにした場合、ルーム チャットは永続的になります。それ以外の場合、チャット メッセージは保持されません。 コンプライアンスを有効にすると、ルーム チャットはコンプライアンスに従って保存されますが、ユーザーは古いメッセージにアクセスできません。 このオプションは、チャット履歴を保持する必要がなされない、リアルタイムのアドホック コラボレーション用に指定されたルームに使用できます。
    
7. [**編集 分類**] で、次の操作を実行します。
    
   - [**メンバーシップ**] の[許可されるメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。 カテゴリによって許可されるプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ルームのメンバーだけがディレクトリで検索できます)。
    
   - メンバーシップ **の**[拒否されたメンバー] セクションで、ルームから拒否されているメンバーに関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。
    
   - [ **メンバーシップ]** の **[Creators]** セクションで、カテゴリの作成者に関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。 作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てるためのアクセス許可が与えられているユーザーです。
    
8. [**確定**] をクリックします。
    
## <a name="configure-categories-by-using-windows-powershell"></a>グループを使用してカテゴリをWindows PowerShell

次のコマンドレットを使用して、カテゴリWindows PowerShellできます。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |新しいカテゴリを作成する  <br/> |
|Set-CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成する  <br/> |
|Get-CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得する  <br/> |
|Remove-CsPersistentChatCategory  <br/> |カテゴリを削除する  <br/> |
   
カテゴリに対して次のパラメーターを構成できます。
  
- EnableFileUpload。 カテゴリ内のチャット ルームへのファイルのアップロードを許可します。
    
- EnableInvitations。 カテゴリの招待を有効にする。 AllowedMembers リストのユーザーは、新しいチャット ルームの作成時に、新しいチャット ルームへの参加の招待を自動的に受信します。
    
- ChatHistory。 チャット履歴機能を有効または無効にします。
    
- 作成者。 カテゴリ内でチャット ルームを作成できるユーザーを指定します。
    
- AllowedMembers。 カテゴリ内のチャット ルームへのアクセスを許可するユーザーを指定します。
    
- DeniedMembers。 カテゴリ内のチャット ルームへのアクセスが許可されないユーザーをリストします。
    
すべてのパラメーターを含むコマンドレット構文の詳細については [、「Skype for Business Server 2015 Management Shell」を参照してください](../management-shell.md)。
  
### <a name="create-a-new-category"></a>新しいカテゴリを作成する

**New-CsPersistentChatCategory** コマンドレットを使用して、新しいカテゴリを作成できます。 たとえば、次のコマンドを実行すると、HelpDesk という名前の新しいカテゴリがプール に作成atl-cs-001.contoso.com。 この例では、ファイルのアップロードが有効になっています。
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>既存のカテゴリを構成する

**Set-CsPersistentCategory** コマンドレットを使用して、既存のカテゴリを構成できます。
  
たとえば、次のコマンドは user1 が AllowedMember および Creator であり、user2 はカテゴリ内のルームへのアクセスを拒否されたと指定します。
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>カテゴリに関する情報を取得する

**Get-CsPersistentChatCategory** コマンドレットを使用して、カテゴリに関する情報を取得できます。 たとえば、次のコマンドを実行すると、組織内のすべての常設チャット カテゴリに関する情報が戻されます。
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>カテゴリを削除する

**Remove-CsPersistentChatCategory** コマンドレットを使用して、カテゴリを削除できます。 カテゴリを削除する前に、カテゴリの下のすべてのチャット ルームを削除するか、チャット ルームを新しいカテゴリに移動する必要があります。 たとえば、次のコマンドを実行すると、Identity が "atl-cs-001.contoso.com\helpdesk" のカテゴリが削除されます。
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
