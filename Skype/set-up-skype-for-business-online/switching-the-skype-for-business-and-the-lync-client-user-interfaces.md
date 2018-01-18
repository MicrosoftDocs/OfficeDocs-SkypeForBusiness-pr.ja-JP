---
title: "Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 8a6dd2b1966bb789d104a3bcdbd330f5a8370a88
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える

For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface. The default setting is for users to use the Skype for Business client user interface. If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョンのオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
> [!TIP]
> 手動で操作せずに、ユーザー インターフェイスを簡単に切り替えたい場合は、[Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?LinkId=532431)で、PowerShell スクリプトを使った切り替え方法を参照してください。
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>ユーザー向けに Skype for Business のユーザー インターフェイスを切り替える

Skype for Business Online 用 Windows PowerShell モジュールでは、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 その他の情報については、「[Skype for Business Online 管理用のコンピューターの構成](https://go.microsoft.com/fwlink/?LinkId=534539)」を参照してください。
  
> [!IMPORTANT]
> ユーザー インターフェイスの切り替えに関する _Global_ ポリシー設定は、カスタム ポリシーが既に設定されているユーザーには適用されません。 ユーザー インターフェイスを変更できるようにするには、カスタム ポリシーが適用されているユーザーそれぞれについて、次のコマンドを実行する必要があります。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> _ClientPolicyEnableSkypeUI_ ポリシーによって、ユーザーに設定されている既存のカスタム ポリシーは置き換えられます。
  
組織内のすべてのユーザーが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

ポリシーを正しく設定すると、次のように表示されます。
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
組織内のすべてのユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

ポリシーを正しく設定すると、次のように表示されます。
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
組織内の 1 人のユーザーが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

ポリシーを正しく設定すると、次のように表示されます。
  
![Skype for Business Online - UI を有効にする](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
組織内の 1 人のユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

ポリシーを正しく設定すると、次のように表示されます。
  
![Skype for Business Online - UI を無効にする](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
組織内の複数のユーザーが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

組織内の複数のユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

組織内のユーザー グループが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

組織内のユーザー グループが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  ユーザーの名前は、ポリシーを割り当てるユーザーのアカウント名です。 ユーザーのアカウント名は、次のいずれかの形式で入力できます。>  ユーザーの SIP アドレス>  ユーザーのユーザー プリンシパル名 (UPN)>  ユーザーのドメイン\\ユーザー名>  ユーザーの Active Directory 表示名
  
[Windows PowerShell による Lync Online の管理](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>Skype for Business Online のポリシー設定

次の表は、ポリシーが最初にユーザーに適用されたときのユーザー エクスペリエンスを示しています。
  
|**管理ポリシー設定**|**表示されるユーザー インターフェイス**|
|:-----|:-----|
|ポリシーが設定されていない場合 |ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|ユーザーに Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。 後で切り替えることもできます。|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|ユーザーは、Skype for Business クライアントのユーザー インターフェイスを使うことになります。 |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|The user will be asked to switch to the Skype for Business (Lync) client user interface. An admin can change the setting in the future that will switch them to the Skype for Business client user interface. |
   
次の表は、ポリシーが変更されたときのユーザー エクスペリエンスを示しています。
  
|**管理ポリシー設定**|**Skype for Business (Lync) のユーザー インターフェイス**|**Skype for Business のユーザー インターフェイス**|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|ユーザーに Skype for Business クライアントのユーザー インターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。  <br/> |ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|The user will continue to use the Skype for Business (Lync) interface.  <br/> |The user will be asked to switch to the Skype for Business (Lync) client user interface.  <br/> |
|ポリシーが設定されていない場合  <br/> |Users will never see the Skype for Business (Lync) client user interface if the policy is not set. They will always use the Skype for Business client user interface.  <br/> |ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |
   
次の表は、利用できるすべての Online カスタム ポリシーを示しています。 これには、管理者が古いカスタム ポリシーを保持しながら、EnableSkypeUI フラグを切り替えられるように、柔軟性を考慮して作成された新しいポリシーが含まれています。 上のコマンドレットを使って、下のポリシーの 1 つをユーザーに付与してください。
  
|**ポリシー名**|**EnableSkypeUI**|
|:-----|:-----|
```ClientPolicyDefaultPhoto```||
```ClientPolicyDefaultPhotoDisableSkypeUI``` |False|
```ClientPolicyNoIMURL```||
```ClientPolicyNoIMURLDisableSkypeUI``` |False|
```ClientPolicyNoIMURLPhoto```||
```ClientPolicyNoIMURLPhotoDisableSkypeUI``` |False|
```ClientPolicyNoSaveIMNoArchivingI```||
```ClientPolicyNoSaveIMNoArchivingDisableSkypeUI``` |False|
```ClientPolicyNoSaveIMNoArchivingNoIMURL```||
```ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI``` |False|
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto``` ||
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI```|False|
```ClientPolicyNoSaveIMNoArchivingPhoto```||
```ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI``` |False|

   
Windows PowerShell を使い始めるには、以下のトピックを参照してください。
  
- [Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>初めて起動するクライアントの動作

By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously. 数分後、ユーザーは Lync モードに切り替えるかどうかを尋ねられます。
  
ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。
  
1. このトピックの最初に説明している手順に従って、クライアント ポリシーで Skype for Business ユーザー インターフェイスが無効に設定されていることを確認します。
    
2. ユーザーのコンピューターで、システム レジストリを更新します。 レジストリの更新は、ユーザーが初めて Skype for Business クライアントを起動する前に 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。
    
    In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.
    
    The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.
    
    キーは、以下のようになります。
    
    [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab"=dword:00000001
    
    "CanShareOneNoteInCollab"=dword:00000001
    
    "CanAppShareInCollab"=dword:00000001
    
    "EnableSkypeUI"=hex:00,00,00,00
    
これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスが表示されるようになります。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>[ようこそ] 画面のチュートリアルの表示方法を制御する

When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*. You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:
  
In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. [**値の名前**] に「**IsBasicTutorialSeenByUser**」と入力し、[**値のデータ**] を「**1**」に設定する必要があります。
  
キーは、以下のようになります。
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a>クライアント チュートリアルをオフにする

ユーザーがチュートリアルにアクセスできないようにするには、以下のレジストリ値を指定して、クライアント チュートリアルをオフにします。
  
In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. [**値の名前**] に「**TutorialFeatureEnabled**」と入力し、[**値データ**] を「**0**」に設定する必要があります。
  
```
"TutorialFeatureEnabled"=dword:00000000
```

[値のデータ] を「1」に設定すれば、チュートリアルをオンに戻すことができます。
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインに参加しているコンピューターでレジストリを変更するグループ ポリシー オブジェクトを作成する

ユーザーが初めて Skype for Business クライアントを起動したときに、Lync クライアント エクスペリエンスを表示するためのレジストリの更新は、1 回だけ行う必要があります。 グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。
  
以下の手順では、ユーザーが初めて Skype for Business を起動したときに、Lync クライアント エクスペリエンスが表示されるようにレジストリを変更する方法について説明します。 この手順を使って、前述のように [ようこそ] 画面のチュートリアルを無効にするために、レジストリを更新することもできます。
  
 **To create the GPO**
  
1. **グループ ポリシー管理コンソール**を起動します。
    
    グループ ポリシー管理コンソールの使い方については、「[グループ ポリシー管理コンソール](https://go.microsoft.com/fwlink/?LinkId=532759)」を参照してください。
    
2. [ **グループ ポリシー オブジェクト**] ノードを右クリックして、メニューから [ **新規作成**] を選びます。
    
3. [ **新しい GPO**] ダイアログ ボックスに、「MakeLyncDefaultUI」などの GPO 名を入力して、[ **OK**] をクリックします。
    
4. 作成した新しい GPO を右クリックして、メニューから [ **編集**] を選びます。
    
5. [ **グループ ポリシー管理エディター**] で、[ **ユーザーの構成**]、[ **ユーザー設定**]、[ **Windows 設定**] の順に展開して、[ **レジストリ**] ノードを選びます。
    
6. Right-click on the **Registry** node, and then select **New** > **Registry Item**.
    
7. [ **新しいレジストリのプロパティ**] ダイアログ ボックスで、以下のように項目を更新します。
    
|**フィールド**|**選択または入力する値**|
|:-----|:-----|
|**操作** <br/> |**作成** <br/> |
|**ハイブ** <br/> | HKEY_CURRENT_USER <br/> |
|**キー パス** <br/> |Software\\Microsoft\\Office\\Lync  <br/> |
|**値の名前** <br/> |EnableSkypeUI  <br/> |
|**値の種類** <br/> |REG_BINARY  <br/> |
|**値のデータ** <br/> |00000000  <br/> |
   
[ **OK**] をクリックして変更を保存し、GPO を閉じます。
    
次に、ポリシーを割り当てる OU などのユーザー グループに、作成した GPO を接続する必要があります。
  
 **To use the GPO to assign the policy**
  
1. [グループ ポリシー管理コンソール] で、ポリシーを割り当てる OU を右クリックして、[ **既存の GPO にリンクする**] を選びます。
    
2. [ **GPO の選択**] ダイアログ ボックスで、作成済みの GPO を選んで、[ **OK**] を選びます。
    
3. ターゲット ユーザーのコンピューターで、コマンド プロンプトを開いて、以下のコマンドを入力します。
    
    **gpupdate /target:user**
    
    GPO の適用中、"ポリシーを更新しています..." というメッセージが表示されます。 処理が完了すると、"ユーザー ポリシーの更新が正常に完了しました" というメッセージが表示されます。
    
4. コマンド プロンプトに、以下のコマンドを入力します。
    
    **gpresult /r**
    
    [適用されたグループ ポリシーオブジェクト] と、作成した GPO 名が下に表示されます。
    
また、レジストリを確認して、GPO でユーザーのコンピューターのレジストリが正常に更新されたことを確認する方法もあります。 Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. GPO によってレジストリが正常に更新された場合、値が 0 の EnableSkypeUI が表示されます。
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md)
