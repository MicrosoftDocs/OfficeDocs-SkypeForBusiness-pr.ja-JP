---
title: "Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: "Skype for Business と Lync クライアントのユーザー インターフェイス PowerShell を使用して、Office 365 の間の切り替え方法を学習します。 "
ms.openlocfilehash: ded1fbf0825fd03645aa2862cc4f51cc10374fbc
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える

Business Online 組織の skype のビジネス ユーザーの Skype for Business クライアント、Skype を使用するのにか、Skype for Business (Lync) クライアントのユーザー インターフェイスを有効にするのに Office 365 で、リモート PowerShell を使用することができます。既定の設定では、ユーザーは、Skype for Business クライアントのユーザー インターフェイスを使用します。Lync クライアント エクスペリエンスを使用する場合は、このトピックの後半で説明の手順に従って、Lync ユーザー インターフェイスを表示するのには、最初の起動クライアント動作を管理することができます。
  
> [!NOTE]
> Lync 2013 のクライアント エクスペリエンスは、Skype for Business 2016 クライアント版オプションです。Lync 2013 クライアントを使用するクライアント環境を構成するしようとすると、前に 16 には、番号に開始しないことを確認するクライアントのバージョンを確認してください。例: 16.x.x.x します。 
  
> [!TIP]
> ユーザー インターフェイスを簡単に移動するしてに手動で操作したくない場合は、 [Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?LinkId=532431)で、PowerShell スクリプトを簡単を参照してください。
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>Skype for Business ユーザーのユーザー インターフェイスの切り替え

Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。64 ビット版コンピューターでのみサポートされますが、このモジュールは、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。その他の情報は、「 [Skype for Business Online 管理コンピューターを構成する](https://go.microsoft.com/fwlink/?LinkId=534539)」を参照してください。
  
> [!IMPORTANT]
> 既にカスタム ポリシーが適用されているユーザーに、ユーザー インターフェイスの切り替えの_グローバル_ポリシー設定は適用されません。ユーザー インターフェイスを変更できるようにするには、カスタム ポリシーが適用されている各ユーザーは、次を実行する必要があります。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> _ClientPolicyEnableSkypeUI_ポリシーは、ユーザーの既存のカスタム ポリシー設定で置き換えられます。
  
すべての Skype for Business クライアントの使い方、組織のユーザーを有効にするには、リモート PowerShell を開いてし、次の値を入力します。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

ポリシーを正しくを設定すると表示されます。
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Skype for Business (Lync) クライアントを使用する組織のユーザーのすべてを有効にするには、リモート PowerShell を開いてし、次の値を入力します。 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

ポリシーを正しくを設定すると表示されます。
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Skype for Business クライアントを使用する組織内で 1 人のユーザーは、リモート PowerShell を開いてし、次の値を入力します。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

ポリシーを正しくを設定すると表示されます。
  
![Skype for Business Online - UI を有効にします。](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
Skype for Business (Lync) クライアントを使用する組織内で 1 人のユーザーは、リモート PowerShell を開いてし、次の値を入力します。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

ポリシーを正しくを設定すると表示されます。
  
![Skype for Business Online - UI 無効にします。](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
Skype for Business クライアントを使用する組織で複数のユーザーは、リモート PowerShell を開いてし、次の値を入力します。
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Skype for Business (Lync) クライアントを使用する組織で複数のユーザーは、リモート PowerShell を開いてし、次の値を入力します。
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Skype for Business クライアントの使い方、組織内のユーザーのグループは、リモート PowerShell を開いてし、次の値を入力します。
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Skype for Business (Lync) クライアントを使用、組織内のユーザーのグループは、リモート PowerShell を開いてし、次の値を入力します。
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  ユーザーの名前は、ポリシーを割り当てる必要がありますユーザーのアカウントの名前です。次の形式のいずれかで、ユーザーのアカウント名を入力することができます: > ユーザーの SIP アドレス > ユーザーのユーザー プリンシパル名 (UPN) > ドメイン\\ユーザーのユーザー名 > のユーザーの Active Directory 表示名
  
[Windows PowerShell による Lync Online の管理](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>Skype for Business Online のポリシー設定

次の表は、ユーザーに適用されるポリシーが最初に、ユーザー エクスペリエンスを示しています。
  
|**管理ポリシーの設定**|**表示されるユーザー インターフェイス**|
|:-----|:-----|
|ポリシーが設定されていません。 |ユーザーを引き続き for Business クライアントのユーザー インターフェイスの Skype を使用します。|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|ユーザーを引き続き for Business クライアントのユーザー インターフェイスの Skype を使用します。|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|ユーザーは、Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるように求められます。後で、切り替えることができます。|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|[ユーザーが使用する、Skype for Business クライアントのユーザー インターフェイスです。 |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|ユーザーは、Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるように求められます。管理者が、Skype for Business クライアントのユーザー インターフェイスに切り替えるを将来の設定を変更できます。 |
   
次の表は、ポリシーが変更されたときに、ユーザー エクスペリエンスを示しています。
  
|**管理ポリシーの設定**|**Skype for Business (Lync) ユーザー インターフェイス**|**Skype for Business ユーザー インターフェイス**|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|ユーザーは、Skype for Business クライアントのユーザー インターフェイスに切り替えるように求められます。  <br/> |ユーザーは引き続きの Skype for Business クライアントのユーザー インターフェイスを使用します。  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|ユーザーは引き続きの Skype for Business (Lync) のインターフェイスを使用します。  <br/> |ユーザーは、Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるように求められます。  <br/> |
|ポリシーが設定されていません。  <br/> |ポリシーが設定されていない場合、ユーザーは Skype for Business (Lync) クライアントのユーザー インターフェイスを表示しません。Skype for Business クライアントのユーザー インターフェイス常に使用します。  <br/> |ユーザーは引き続きの Skype for Business クライアントのユーザー インターフェイスを使用します。  <br/> |
   
次の表は、すべてのオンライン カスタム ポリシー利用可能なを示します。古いカスタム ポリシー EnableSkypeUI 旗の間の切り替え中に保存することに柔軟に管理者を作成した新しいポリシーがあります。上のコマンドレットを使用してくださいのいずれかを付与、ポリシーをユーザーに以下します。
  
|**ポリシーの名前**|**EnableSkypeUI**|
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

   
Windows PowerShell で開始するには、次のトピックを参照してください。
  
- [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>最初の起動クライアントの動作

既定では、ユーザーを初めて、Skype for Business を起動すると、常に表示されますが Skype for Business ユーザー インターフェイス - Lync クライアントの操作環境のクライアントのポリシーを設定して、Lync のクライアント エクスペリエンスを選択した場合でも (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) に従って先に。分後に、いくつか、ユーザーは、[ように求められます Lync モードに切り替えます。
  
ユーザーを初めて Skype for Business クライアントを起動すると、Lync ユーザー インターフェイスを表示する場合は、クライアントが更新される後に初めて開始する前にこれらの手順に従います。
  
1. このトピックの前の手順を実行し、クライアントのポリシーが Skype for Business ユーザー インターフェイスを無効に設定されていることを確認します。
    
2. ユーザーのコンピューター システムのレジストリを更新します。これは、ユーザーが初めてが Skype for Business クライアントを起動して、1 回だけ行います前に行う必要があります。ドメインのレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、結合されたコンピューターでは、トピックの後半の「を参照してください。
    
    **[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\Lync]**キーは、新しい**バイナリ**値を作成します。
    
    [**値の名前**でなければ**EnableSkypeUI**と**00 00 00**00**値のデータ**を設定する必要があります。
    
    キーは、次のようになります。
    
    [HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab"= dword:00000001
    
    "CanShareOneNoteInCollab"= dword:00000001
    
    "CanAppShareInCollab"= dword:00000001
    
    "EnableSkypeUI"= 16 進数: 00、00, 00, 00
    
ユーザーを初めて Skype for Business クライアントを起動すると、Lync ユーザー インターフェイスは表示されます。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>[ようこそ] 画面のチュートリアルの表示を制御します。

ユーザーが Skype for Business クライアントを開いたときの既定の動作が、*ほとんどのユーザーが求める 7 つのクイック ヒント*を含む [ようこそ] 画面を表示します。[ようこそ] 画面の表示をオフにするが、ユーザーは、クライアント コンピューターで次のレジストリ値を追加してチュートリアルにアクセスすることができます。
  
**[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync]**キーは、「新しい**DWORD (32 ビット) の値**を作成します。**値の名前** **IsBasicTutorialSeenByUser**] は、**値のデータ**を**1**に設定する必要があります。
  
キーは、次のようになります。
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a>クライアントのチュートリアルをオフにします。

チュートリアルにアクセスできるユーザーしたくない場合は、クライアントのチュートリアルでは、次のレジストリ値をオフにすることができます。
  
**[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync]**キーは、「新しい**DWORD (32 ビット) の値**を作成します。**値の名前** **TutorialFeatureEnabled**] は、**値のデータ**を**0**に設定する必要があります。
  
```
"TutorialFeatureEnabled"=dword:00000000
```

**値のデータ**を**1**に設定して後でチュートリアルを有効にできます。
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインの結合されるコンピューターでレジストリを変更するグループ ポリシー オブジェクトを作成します。

1 回だけ表示 Lync クライアント エクスペリエンスの初めてのユーザーが Skype for Business クライアントを起動するレジストリの更新を行う必要があります。レジストリを更新するグループ ポリシー オブジェクト (GPO) を使用している場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。GPO を適用すると、新しい値が存在しない場合は、GPO を作成し、値のデータを 0 に設定します。
  
次の手順では、Lync クライアント エクスペリエンスのユーザーが Skype for Business を起動 2 回目が表示されるように、レジストリを変更する方法について説明します。前述のように [ようこそ] 画面のチュートリアルを無効にするのにレジストリを更新するのに、この手順を使用することもできます。
  
 **GPO を作成するには**
  
1. **グループ ポリシーの管理コンソール**を起動します。
    
    グループ ポリシーの管理コンソールを使用する方法については、[グループ ポリシー管理コンソール](https://go.microsoft.com/fwlink/?LinkId=532759)を参照してください。
    
2. **グループ ポリシー オブジェクト**ノードを右クリックし、メニューの [**新規作成**します。
    
3. **新しい GPO** ] ダイアログ ボックスで、たとえば、MakeLyncDefaultUI、GPO の名前を入力し、し、[ **OK**] をクリックします。
    
4. 作成した新しい GPO で右クリックし、[メニューから [**編集**] を選びます。
    
5. **グループ ポリシー管理エディター**] で**ユーザー**の構成、**環境設定**を展開する**Windows の設定**] を展開し、**レジストリ**] ノードを選択します。
    
6. **レジストリ**] ノードを右クリックし、[**新規作成**] を選びます > **レジストリ アイテム**。
    
7. [**新しいレジストリのプロパティ**] ダイアログ ボックスで、次のように更新します。
    
|**フィールド**|**値を入力するか選びます**|
|:-----|:-----|
|**アクション** <br/> |**作成します。** <br/> |
|**ハイブ** <br/> | HKEY_CURRENT_USER <br/> |
|**キーのパス** <br/> |ソフトウェア\\Microsoft\\Office\\Lync  <br/> |
|**値の名前** <br/> |EnableSkypeUI  <br/> |
|**値の種類** <br/> |REG_BINARY  <br/> |
|**値のデータ** <br/> |00000000  <br/> |
   
変更内容を保存して**[OK** ] をクリックし、GPO を閉じます。
    
次に、OU など、ポリシーを割り当てるユーザーのグループを作成する GPO をリンクする必要があります。
  
 **GPO を使用して、ポリシーを割り当てる**
  
1. グループ ポリシーの管理コンソールでは、ポリシーを割り当てる OU で右クリックし、[**既存の GPO へのリンク**] を選びます。
    
2. [ **GPO の選択**] ダイアログ ボックスで、作成した GPO を選択し、[、[ **ok]**をクリックします。
    
3. 対象ユーザーのコンピューターでは、コマンド プロンプトを開きます。 し、次のコマンドを入力します。
    
    **gpupdate/target:user**
    
    メッセージの「更新ポリシー...」GPO が適用されて表示されます。完了すると、「ユーザー ポリシーの更新プログラムが正常に完了しました」メッセージが表示されます。
    
4. コマンド プロンプトで、次のコマンドを入力します。
    
    **gpresult/r**
    
    作成した GPO の名前での「グループ ポリシー オブジェクトの割り当てられている」の下に表示するが表示されます。
    
GPO 正常に更新したユーザーのコンピューター上のレジストリでレジストリを調べることを確認することもできます。レジストリ エディターを開きに移動、 **[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\Lync]**キーです。GPO レジストリを正常に更新する場合は、0 の値を含む EnableSkypeUI をという名前の値が表示されます。
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)

[ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。](let-skype-for-business-users-add-skype-contacts.md)
