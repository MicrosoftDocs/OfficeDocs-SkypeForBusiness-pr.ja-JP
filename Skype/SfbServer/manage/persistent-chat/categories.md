---
title: Skype for Business Server 2015 の常設チャット サーバーでのカテゴリの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '概要: Skype for Business Server 2015 で常設チャットサーバーのカテゴリを管理する方法について説明します。'
ms.openlocfilehash: 55cd4ef7e89e85bb78c061b05c612d6703c34221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279355"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の常設チャット サーバーでのカテゴリの管理
 
**概要:** Skype for Business Server 2015 で常設チャットサーバーのカテゴリを管理する方法について説明します。
  
カテゴリは、チャット ルームを整理するための論理的な構造です。 カテゴリでは、チャット ルームを作成したり、チャット ルームに参加したりできるユーザーおよびユーザー グループを制御するためのアクセス制御リスト (ACL) の既定のセットを定義します。 チャット ルーム カテゴリには、チャット ルームのカテゴリを含めることができますが、他のカテゴリを含めることはできません。 各カテゴリでは、[名前]、[説明] などのメタデータを使用してカテゴリの内容が記述されます。 また、カテゴリには、チャット ルームで [招待] や [ファイル アップロード] が許可されるかどうか、チャット ルームに [チャットの履歴] が含まれるかどうかなど、そのカテゴリに属するチャット ルームの動作を制御するプロパティを設定できます。 
  
カテゴリを適切に使用すると、チャット ルームの作成と管理が簡単になります。 常設チャット サーバーの管理者は、各カテゴリに対して AllowedMembers と Creators を定義でき、そのカテゴリで作成されるすべてのチャット ルームに適用されるチャット ルームの既定の設定と動作を定義することもできます。 たとえば、カテゴリの AllowedMembers を contoso.com に設定した場合、Contoso の任意のグループまたはユーザーをメンバーとしてそのカテゴリのチャットルームに追加することができます。 カテゴリの Allowed Members を "営業" に設定した場合は、その配布リスト内のグループとユーザーのみを、カテゴリ内のチャット ルームにメンバーとして追加できます。 Creators プロパティを使用すると、カテゴリ内にチャット ルームを作成できるユーザーを制御できます。 チャット ルームが作成されると、AllowedMembers グループのユーザーを、ルームで進行中の管理操作 (メンバーシップの変更や承認など) の管理者として指定できます。
  
カテゴリの AllowedMembers と Creators を定義すると、次の利点が得られます。
  
- カテゴリ内のすべてのチャット ルームがカテゴリ レベルの制限のセットにバインドされます。 これにより、業務ニーズとアクセス ポリシーに基づいてチャット ルームを分離できます。
    
- Creators の一覧に含まれるユーザーが、カテゴリ内に新しいチャット ルームを作成できます。チャット ルームを作成できる組織内の担当者の数が制限されているシステムを実装する場合は、この制御を使用して要件を満たすことができます。 
    
カテゴリの Creators として特定されるユーザー、組織単位 (OU)、ユーザー グループは、そのカテゴリのチャット ルームの作成を許可されている個人およびグループです。 カテゴリを作成した後は、カテゴリの AllowedMembers リストからユーザー、OU、ユーザー グループをチャット ルームの管理と参加が可能なマネージャーおよびメンバーとして選択できます。 
  
カテゴリを構成する前に、 [Skype For Business Server 2015 の常設チャットカテゴリ、チャットルーム、ユーザーロール](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)をお読みください。
  
コントロール パネルを使用するか Windows PowerShell コマンドレットを使用すると、カテゴリを構成して管理することができます。

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 
  
## <a name="configure-categories-by-using-the-control-panel"></a>コントロール パネルを使用してカテゴリを構成する

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。
    
3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。
    
    複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。
    
4. [**カテゴリ**] ページで、[**新規**] または [**編集**] をクリックします。
    
5. [**サービスの選択**] で、カテゴリの作成が必要な常設チャットサーバープールに対応するサービスを選びます。 [サービス] は、カテゴリが属しているプールを特定するために常設チャットクライアントが使用する常設チャットサーバープールです。 カテゴリは、1つの常設チャットサーバープールにのみ所属でき、別のプールに移動したり、共有したりすることはできません。
    
6. [**新しいカテゴリ**] で、次の操作を実行します。
    
   - [**名前**] に、新しいルーム カテゴリの名前を指定します。
    
   - [**説明**] に、ルーム カテゴリの詳細を指定します (たとえば「Contoso 用のカテゴリ」と指定します)。
    
   - このカテゴリに属するチャットルームに対して招待を有効にできるかどうかを制御するには、[**招待を有効に**する] チェックボックスをオンまたはオフにします。 選択されている場合、このカテゴリの会議室の出席依頼のオンとオフを切り替えることができます。この設定をオフにすると、このカテゴリのルームに招待状は許可されません。 会議室が招待されている場合、会議室に新しいメンバーが追加されると、そのユーザーは、常設チャットクライアントで新しい会議室の通知を受け取ります。
    
   - このカテゴリに属するチャット ルームでファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合、このカテゴリのルームでは、ファイルのアップロードを有効または無効にできます。オフにした場合、このカテゴリのルームではファイルのアップロードは許可されません。
    
   - チャット履歴を管理するには、[**チャット履歴を有効に**する] チェックボックスをオンまたはオフにします。 選択されている場合、ルームチャットは永続的になります。それ以外の場合は、チャットメッセージは保持されません。 コンプライアンスが有効になっている場合、ルームのチャットはコンプライアンスに保存されますが、ユーザーは古いメッセージにアクセスすることはできません。 このオプションは、チャット履歴を保持する必要のないリアルタイムの共同作業用に指定された会議室に使用できます。
    
7. [**カテゴリの編集**] で、次の操作を実行します。
    
   - [許可された**メンバー** ] セクションの [**メンバーシップ**] で、チャットルームのメンバーとして追加することを許可されているユーザーおよびその他の Active Directory ドメインサービスプリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。カテゴリに属している。 カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索することができます (ルームが非表示になっている場合を除き、ルームのメンバーだけがディレクトリ内で検索できます)。
    
   - [**メンバーシップ**] の [**拒否するメンバー** ] セクションで、会議室から拒否されているメンバーに関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。
    
   - [**メンバーシップ**] の [ **** 作成者] セクションで、カテゴリの作成者に関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。 作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。
    
8. [**確定**] をクリックします。
    
## <a name="configure-categories-by-using-windows-powershell"></a>Windows PowerShell を使用してカテゴリを構成する

次の Windows PowerShell コマンドレットを使用すると、カテゴリを構成することができます。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |新しいカテゴリを作成する  <br/> |
|Set-CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成する  <br/> |
|Get-CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得する  <br/> |
|Remove-CsPersistentChatCategory  <br/> |カテゴリを削除する  <br/> |
   
カテゴリには、次のパラメーターを構成できます。
  
- EnableFileUpload。カテゴリ内のチャット ルームにファイルをアップロードすることができます。
    
- EnableInvitations。 カテゴリの招待を有効にします。 AllowedMembers リストに登録されているユーザーは、新しいチャット ルームが作成されると、そのチャット ルームへの参加を促す招待状を自動的に受信します。
    
- ChatHistory。 チャット履歴機能を有効または無効にします。
    
- Creators。 カテゴリ内でのチャット ルームの作成が許可されるユーザーを指定します。
    
- AllowedMembers。 カテゴリ内のチャット ルームへのアクセスが許可されるユーザーを指定します。
    
- DeniedMembers。カテゴリ内のチャット ルームへのアクセスが許可されないユーザーをリストします。
    
すべてのパラメーターを含む、コマンドレットの構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。
  
### <a name="create-a-new-category"></a>新しいカテゴリを作成する

**New-CsPersistentChatCategory** コマンドレットを使用すると、新しいカテゴリを作成できます。 たとえば、以下のコマンドを実行すると、プール atl-cs-001.contoso.com に HelpDesk という名前の新しいカテゴリが作成されます。 この例では、ファイル アップロードが有効になります。
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>既存のカテゴリを構成する

**Set-CsPersistentCategory** コマンドレットを使用すると、既存のカテゴリを構成できます。
  
たとえば、次のコマンドは、user1 が AllowedMember と Creator であることを示しますが、user2 はカテゴリ内の会議室へのアクセスを拒否しています。
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>カテゴリに関する情報を取得する

**Get-CsPersistentChatCategory** コマンドレットを使用すると、カテゴリに関する情報を取得できます。たとえば、以下のコマンドを実行すると、組織内のすべての常設チャット カテゴリに関する情報が戻されます。
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>カテゴリを削除する

**Remove-CsPersistentChatCategory** コマンドレットを使用すると、カテゴリを削除できます。カテゴリを削除する前に、そのカテゴリの下にあるすべてのチャット ルームを削除するか、それらのチャット ルームを新しいカテゴリに移動する必要があります。たとえば、以下のコマンドを実行すると、ID "atl-cs-001.contoso.com\helpdesk" が含まれるカテゴリが削除されます。
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
