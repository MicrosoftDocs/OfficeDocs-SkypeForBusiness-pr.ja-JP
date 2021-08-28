---
title: 2015 年の常設チャット サーバーでSkype for Business Serverする
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
ms.localizationpriority: medium
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '概要: 常設チャット サーバー のカテゴリを 2015 年に管理するSkype for Business Serverします。'
ms.openlocfilehash: a69d8ec3119f9f94f9f5c864ec0e0d2d613b0e20
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622219"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>2015 年の常設チャット サーバーでSkype for Business Serverする
 
**概要:** 2015 年に常設チャット サーバーのカテゴリを管理するSkype for Business Serverします。
  
カテゴリは、チャット ルームを整理する論理的な構造です。 カテゴリは、チャット ルームを作成または参加できるユーザーとユーザー グループを制御するためのアクセス制御リスト (ACL) の既定のセットを定義します。 チャット ルーム のカテゴリにはチャット ルームが含まれますが、他のカテゴリは含めではありません。 各カテゴリには、名前や説明などのメタデータを使用してカテゴリの内容が記述されます。 カテゴリには、そのカテゴリに属するチャット ルームの動作を制御するために設定できるプロパティがあります。たとえば、チャット ルームで招待またはファイルのアップロードを許可するか、チャット履歴を含めます。 
  
カテゴリを正しく使用すると、チャット ルームの作成と管理がはるかに簡単になります。 常設チャット サーバー管理者は、カテゴリごとに AllowedMembers と Creators を定義し、カテゴリ内に作成されたチャット ルームに適用される既定のチャット ルームの設定と動作も定義できます。 たとえば、カテゴリの AllowedMembers を contoso.com に設定した場合、そのカテゴリのチャット ルームにメンバーとして Contoso の任意のグループまたはユーザーを追加できます。 カテゴリの [許可されたメンバー] を [販売] に設定した場合、この配布リストのグループとユーザーのみをそのカテゴリのチャット ルームにメンバーとして追加できます。 Creators プロパティを使用すると、そのカテゴリにチャット ルームを作成できるユーザーを制御できます。 チャット ルームを作成すると、AllowedMembers グループの誰でも、ルームの継続的な管理操作 (メンバーシップの変更や承認など) のマネージャーとして指定できます。
  
カテゴリの AllowedMembers と Creators を定義すると、次の利点が得られます。
  
- カテゴリ内のすべてのチャット ルームがカテゴリ レベルの制限のセットにバインドされます。これにより、業務ニーズとアクセス ポリシーに基づいてチャット ルームを分離できます。
    
- Creators の一覧に含まれるユーザーが、カテゴリ内に新しいチャット ルームを作成できます。 組織内の制限された数の人員がチャット ルームを作成できるシステムを実装する場合は、このコントロールを使用して、その要件を満たします。 
    
カテゴリの作成者として識別されるユーザー、組織単位 (OUs)、およびユーザー グループは、カテゴリ内に会議室を作成できる唯一の個人およびグループです。 カテゴリの作成後、カテゴリの AllowedMembers リストからユーザー、OUs、およびユーザー グループをチャット ルームの管理者およびメンバーとして選択して、ルームを管理および参加できます。 
  
カテゴリを構成する前に[、2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)年の常設チャット カテゴリ、チャット ルーム、およびユーザー の役割Skype for Business Serverしてください。
  
コントロール パネルを使用するか、コントロール パネルのコマンドレットを使用して、カテゴリをWindows PowerShellできます。

> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 
  
## <a name="configure-categories-by-using-the-control-panel"></a>コントロール パネルを使用してカテゴリを構成する

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート **] メニュー** から、[コントロール パネル] Skype for Business Serverを選択するか、ブラウザー ウィンドウを開き、[管理 URL] を入力します。
    
3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。
    
    複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。
    
4. [**分類**] ページで、[**新規**] または [**編集**] をクリックします。
    
5. [ **サービスの選択]** で、カテゴリを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。 サービスは、常設チャット クライアントがカテゴリが属するプールを識別するために使用する常設チャット サーバー プールです。 カテゴリは 1 つの常設チャット サーバー プールにのみ属し、別のプールに移動したり、別のプールと共有したりすることはできません。
    
6. [**新規 分類**] で、次の操作を実行します。
    
   - [**名前**] に、新しいルーム カテゴリの名前を指定します。
    
   - [**説明**] に、ルーム カテゴリの説明 (Contoso 用のルーム カテゴリなど) を詳しく指定します。
    
   - このカテゴリに属するチャット ルームで招待を有効にできるかどうかを制御するには、[招待を有効にする] チェック **ボックス** をオンまたはオフにします。 選択されている場合、このカテゴリの会議室に招待状がオンまたはオフの場合があります。オフにした場合、このカテゴリの会議室は招待を受け付けできません。 ルームに招待が有効な場合、新しいメンバーがルームに追加された場合、常設チャット クライアントで新しいルームの通知を受け取ります。
    
   - このカテゴリに属するチャット ルームでのファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合は、このカテゴリのルームではファイルのアップロードを有効または無効にできます。オフにした場合は、このカテゴリのルームではファイルのアップロードを有効にできません。
    
   - チャット履歴を制御するには、[チャット履歴を有効 **にする] チェック ボックスを** オンまたはオフにします。 選択すると、ルーム チャットは永続的になります。それ以外の場合、チャット メッセージは保持されません。 コンプライアンスが有効になっている場合、ルーム チャットはコンプライアンスに保存されますが、ユーザーは古いメッセージにアクセスできません。 このオプションは、チャット履歴を保持する必要がないリアルタイムのアドホック なコラボレーション用に指定された会議室に使用できます。
    
7. [**編集 分類**] で、次の操作を実行します。
    
   - [**メンバーシップ**] の[許可されたメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。 カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ディレクトリ内で検索できるのは会議室のメンバーのみです)。
    
   - [ **メンバーシップ]** の [ **拒否** されたメンバー] セクションで、ルームから拒否されているメンバーに関連付けられているユーザーや他の Active Directory プリンシパルを追加または削除します。
    
   - [ **メンバーシップ]** の **[Creators]** セクションで、カテゴリの作成者に関連付けられているユーザーや他の Active Directory プリンシパルを追加または削除します。 作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てるためのアクセス許可が与えられているユーザーです。
    
8. [**確定**] をクリックします。
    
## <a name="configure-categories-by-using-windows-powershell"></a>カテゴリを使用してカテゴリを構成Windows PowerShell

次のコマンドレットを使用してカテゴリWindows PowerShellできます。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |新しいカテゴリを作成する  <br/> |
|Set-CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成する  <br/> |
|Get-CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得する  <br/> |
|Remove-CsPersistentChatCategory  <br/> |カテゴリを削除する  <br/> |
   
カテゴリに対して次のパラメーターを構成できます。
  
- EnableFileUpload。 カテゴリ内のチャット ルームへのファイルのアップロードを許可します。
    
- EnableInvitations。 カテゴリの招待を有効にする。 AllowedMembers リストのユーザーは、新しいルームの作成時に新しいチャット ルームに参加する招待を自動的に受信します。
    
- ChatHistory。 チャット履歴機能を有効または無効にします。
    
- 作成者。 カテゴリ内でチャット ルームを作成できるユーザーを指定します。
    
- AllowedMembers。 カテゴリ内のチャット ルームにアクセスできるユーザーを指定します。
    
- DeniedMembers。 カテゴリ内のチャット ルームへのアクセスが許可されないユーザーをリストします。
    
すべてのパラメーターを含むコマンドレットの構文の詳細については、「Skype for Business Server [2015 管理シェル」を参照してください](../management-shell.md)。
  
### <a name="create-a-new-category"></a>新しいカテゴリを作成する

**New-CsPersistentChatCategory** コマンドレットを使用して、新しいカテゴリを作成できます。 たとえば、次のコマンドは、HelpDesk という名前の新しいカテゴリをプール サーバーに作成 atl-cs-001.contoso.com。 この例では、ファイルのアップロードが有効になっています。
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>既存のカテゴリを構成する

**Set-CsPersistentCategory** コマンドレットを使用して、既存のカテゴリを構成できます。
  
たとえば、次のコマンドは、user1 が AllowedMember および Creator であり、user2 がカテゴリ内のルームへのアクセスを拒否された場合を指定します。
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>カテゴリに関する情報を取得する

**Get-CsPersistentChatCategory** コマンドレットを使用して、カテゴリに関する情報を取得できます。 たとえば、次のコマンドは、組織内のすべての常設チャット カテゴリの情報を返します。
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>カテゴリを削除する

**Remove-CsPersistentChatCategory** コマンドレットを使用して、カテゴリを削除できます。 カテゴリを削除する前に、まずその下のすべてのチャット ルームを削除するか、チャット ルームを新しいカテゴリに移動する必要があります。 たとえば、次のコマンドは、Identity "atl-cs-001.contoso.com\helpdesk" を持つカテゴリを削除します。
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
