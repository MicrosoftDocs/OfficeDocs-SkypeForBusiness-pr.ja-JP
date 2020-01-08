---
title: Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 0f24879c136c98db1a856765cb164d376417ad5a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962885"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える

[] Skype for Business Online を利用している組織の場合、Office 365 でリモート PowerShell を使って、Skype for Business ユーザーが Skype for Business クライアントまたは Skype for Business (Lync) クライアントのユーザー インターフェイスを使用できるように設定できます。 既定では、Skype for Business クライアントのユーザー インターフェイスを使用するように設定されています。 Lync クライアントエクスペリエンスを使用したい場合は、このトピックの後半の手順に従って、Lync ユーザーインターフェイスを表示する最初の起動クライアントの動作を管理することができます。
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョンのオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
> [!TIP]
> ユーザーインターフェイスを簡単に切り替えたい場合に、手動による手順を実行したくない場合は、 [Microsoft ダウンロードセンター](https://go.microsoft.com/fwlink/?LinkId=532431)の PowerShell スクリプトを参照してください。
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>ユーザー向けに Skype for Business のユーザー インターフェイスを切り替える

Skype for Business Online 用 Windows PowerShell モジュールでは、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 その他の情報については、「[Skype for Business Online 管理用のコンピューターの構成](https://go.microsoft.com/fwlink/?LinkId=534539)」を参照してください。
  
> [!IMPORTANT]
> ユーザー インターフェイスの切り替えに関する _Global_ ポリシー設定は、カスタム ポリシーが既に設定されているユーザーには適用されません。 ユーザー インターフェイスを変更できるようにするには、カスタム ポリシーが適用されているユーザーそれぞれについて、次のコマンドを実行する必要があります。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> _ClientPolicyEnableSkypeUI_ ポリシーによって、ユーザーに設定されている既存のカスタム ポリシーは置き換えられます。
  
組織内のすべてのユーザーが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

ポリシーを正しく設定すると、次のように表示されます。
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
組織内のすべてのユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

ポリシーを正しく設定すると、次のように表示されます。
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
組織内の 1 人のユーザーが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

ポリシーを正しく設定すると、次のように表示されます。
  
![Skype for Business Online - UI を有効にする](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
組織内の 1 人のユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

ポリシーを正しく設定すると、次のように表示されます。
  
![Skype for Business Online - UI を無効にする](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
組織内の複数のユーザーが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

組織内の複数のユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

組織内のユーザー グループが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

組織内のユーザー グループが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```PowerShell
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
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|ユーザーには、Skype for Business (Lync) クライアントのユーザーインターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。 後で切り替えることもできます。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|ユーザーは、Skype for Business クライアントのユーザーインターフェイスを使用します。 |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|ユーザーには、Skype for Business (Lync) クライアントのユーザーインターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。 管理者は、Skype for Business クライアントのユーザー インターフェイスに切り替える設定を、後で変更することができます。 |
   
次の表は、ポリシーが変更されたときのユーザー エクスペリエンスを示しています。
  
|**管理ポリシー設定**|**Skype for Business (Lync) のユーザー インターフェイス**|**Skype for Business のユーザー インターフェイス**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|ユーザーには、Skype for Business クライアントのユーザーインターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。  <br/> |ユーザーは、引き続き Skype for Business クライアントのユーザーインターフェイスを使用します。  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|ユーザーは、引き続き Skype for Business (Lync) インターフェイスを使用します。  <br/> |ユーザーには、Skype for Business (Lync) クライアントのユーザーインターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。  <br/> |
|ポリシーが設定されていない場合  <br/> |ポリシーが設定されていない場合、ユーザーに Skype for Business (Lync) クライアントのユーザーインターフェイスは表示されません。 ユーザーは、常に Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |ユーザーは、引き続き Skype for Business クライアントのユーザーインターフェイスを使用します。  <br/> |
   
次の表は、利用できるすべての Online カスタム ポリシーを示しています。 これには、管理者が古いカスタム ポリシーを保持しながら、EnableSkypeUI フラグを切り替えられるように、柔軟性を考慮して作成された新しいポリシーが含まれています。 上のコマンドレットを使って、下のポリシーの 1 つをユーザーに付与してください。
  
|**ポリシー名**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |False|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|False|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |False|

   
Windows PowerShell の使用を開始するには、次のトピックを参照してください。
  
- [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>最初の起動クライアントの動作

既定では、ユーザーが初めて Skype for Business を起動すると、以前のようにクライアントポリシーを Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) に設定して、lync クライアントエクスペリエンスを選択した場合でも、Skype for business のユーザーインターフェイスが表示されます。 起動から数分後に、Lync モードに切り替えるかどうかを確認するメッセージが表示されます。
  
ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。
  
1. このトピックの最初に説明している手順に従って、クライアント ポリシーで Skype for Business ユーザー インターフェイスが無効に設定されていることを確認します。
    
2. ユーザーのコンピューターで、システム レジストリを更新します。 レジストリの更新は、ユーザーが初めて Skype for Business クライアントを起動する前に 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。
    
    In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.
    
    The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.
    
    キーは、以下のようになります。
    
    [HKEY_CURRENT_USER\\ソフトウェア\\(\\Microsoft\\Office Lync)]
    
    "Can" の場合は、dword: 00000001
    
    "CanShareOneNoteInCollab" = dword: 00000001
    
    "Canapp/Inの形式 Ab" = dword: 00000001
    
    "EnableSkypeUI" = hex:00, 00, 00, 00
    
これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスが表示されるようになります。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>ようこそ画面のチュートリアルの表示を制御する

ユーザーが Skype for Business クライアントを開くと、既定の動作では [ようこそ] 画面が表示されます。これには、*ほとんどのユーザーからの質問に対する7つのヒント*が含まれています。 You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:
  
In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.
  
キーは、以下のようになります。
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>クライアント チュートリアルをオフにする

ユーザーがチュートリアルにアクセスできないようにするには、以下のレジストリ値を指定して、クライアント チュートリアルをオフにします。
  
In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

You can turn the tutorial back on by setting the **Value data** to **1**.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインに参加しているコンピューターのレジストリを変更するグループ ポリシー オブジェクトを作成する

ユーザーが初めて Skype for Business クライアントを起動したときに、Lync クライアント エクスペリエンスを表示するためのレジストリの更新は、1 回だけ行う必要があります。 グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。
  
以下の手順では、ユーザーが初めて Skype for Business を起動したときに、Lync クライアント エクスペリエンスが表示されるようにレジストリを変更する方法について説明します。 この手順を使って、前述のように [ようこそ] 画面のチュートリアルを無効にするために、レジストリを更新することもできます。
  
 **GPO を作成するには**
  
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
|**キー パス** <br/> |Microsoft\\\\Office\\Lync ソフトウェア  <br/> |
|**値の名前** <br/> |EnableSkypeUI  <br/> |
|**値の種類** <br/> |REG_BINARY  <br/> |
|**値のデータ** <br/> |00000000  <br/> |
   
[ **OK**] をクリックして変更を保存し、GPO を閉じます。
    
次に、ポリシーを割り当てる OU などのユーザー グループに、作成した GPO を接続する必要があります。
  
 **GPO を使ってポリシーを割り当てるには**
  
1. [グループ ポリシー管理コンソール] で、ポリシーを割り当てる OU を右クリックして、[ **既存の GPO にリンクする**] を選びます。
    
2. [ **GPO の選択**] ダイアログ ボックスで、作成済みの GPO を選んで、[ **OK**] を選びます。
    
3. ターゲット ユーザーのコンピューターで、コマンド プロンプトを開いて、以下のコマンドを入力します。
    
    **gpupdate /target:user**
    
    GPO の適用中、"ポリシーを更新しています..." というメッセージが表示されます。 処理が完了すると、"ユーザー ポリシーの更新が正常に完了しました" というメッセージが表示されます。
    
4. コマンド プロンプトに、以下のコマンドを入力します。
    
    **gpresult /r**
    
    "割り当て済みのグループ ポリシー オブジェクト" と表示され、その下に作成済みの GPO の名前が表示されます。
    
You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 
