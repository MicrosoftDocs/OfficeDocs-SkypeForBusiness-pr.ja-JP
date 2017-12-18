---
title: "Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 6/1/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom: Adm_O365_FullSet
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
description: "Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 "
---

# Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。 
  
Skype for Business Online を利用している組織の場合、Office 365 でリモート PowerShell を使って、Skype for Business ユーザーが Skype for Business クライアントまたは Skype for Business (Lync) クライアントのユーザー インターフェイスを使用できるように設定できます。 既定では、Skype for Business クライアントのユーザー インターフェイスを使用するように設定されています。 Lync クライアント エクスペリエンスを使用したい場合は、このトピックの後半で説明する手順に従って、初めて起動するクライアントの動作を管理し、Lync ユーザー インターフェイスを表示することができます。
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョンのオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
> [!TIP]
> ユーザー インターフェイスを簡単に移動するしてに手動で操作したくない場合は、 [Microsoft ダウンロード センター ](https://go.microsoft.com/fwlink/?LinkId=532431)で、PowerShell スクリプトを簡単を参照してください。 
  
## ユーザー向けに Skype for Business のユーザー インターフェイスを切り替える

Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。64 ビット版コンピューターでのみサポートされますが、このモジュールは、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)に Microsoft ダウンロード センターからダウンロードできます。その他の情報は、[お使いのコンピューターの Skype for Business Online の管理を構成する](https://go.microsoft.com/fwlink/?LinkId=534539)を参照してください。
  
> [!IMPORTANT]
> ユーザー インターフェイスの切り替えに関する _Global_ ポリシー設定は、カスタム ポリシーが既に設定されているユーザーには適用されません。 ユーザー インターフェイスを変更できるようにするには、カスタム ポリシーが適用されているユーザーそれぞれについて、次のコマンドを実行する必要があります。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
>  _ClientPolicyEnableSkypeUI_ ポリシーによって、ユーザーに設定されている既存のカスタム ポリシーは置き換えられます。
  
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
  
![Skype for Business Online - UI を有効にする](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.gif)
  
組織内の 1 人のユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

ポリシーを正しく設定すると、次のように表示されます。
  
![Skype for Business Online - UI を無効にする](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.gif)
  
組織内の複数のユーザーが Skype for Business クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
> 
  ```
  $users = @("sip:bob@contoso.com","sip:fred@contoso.com")
  ```

> 
  ```
  $users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
  ```

組織内の複数のユーザーが Skype for Business (Lync) クライアントを使用できるようにするには、リモート PowerShell を開いて、次のように入力します。
  
> 
  ```
  $users = @("sip:bob@contoso.com","sip:fred@contoso.com")
  ```

> 
  ```
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
  
## Skype for Business Online のポリシー設定

次の表は、ポリシーが最初にユーザーに適用されたときのユーザー エクスペリエンスを示しています。
  
|**管理ポリシー設定**|**表示されるユーザー インターフェイス**|
|:-----|:-----|
|ポリシーが設定されていない場合  <br/> |ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

|ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

|ユーザーに Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。 後で切り替えることもできます。  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

|ユーザーは、Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |
|
```
Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

|ユーザーに Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。 管理者は、Skype for Business クライアントのユーザー インターフェイスに切り替える設定を、後で変更することができます。  <br/> |
   
次の表は、ポリシーが変更されたときのユーザー エクスペリエンスを示しています。
  
|**管理ポリシー設定**|**Skype for Business (Lync) のユーザー インターフェイス**|**Skype for Business のユーザー インターフェイス**|
|:-----|:-----|:-----|
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

|ユーザーに Skype for Business クライアントのユーザー インターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。  <br/> |ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

|ユーザーは、引き続き Skype for Business (Lync) のインターフェイスを使うことになります。  <br/> |ユーザーに Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるかどうかをたずねるメッセージが表示されます。  <br/> |
|ポリシーが設定されていない場合  <br/> |ポリシーが設定されていない場合、ユーザーには Skype for Business (Lync) クライアントのユーザー インターフェイスが表示されることはありません。 ユーザーは、常に Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |ユーザーは、引き続き Skype for Business クライアントのユーザー インターフェイスを使うことになります。  <br/> |
   
次の表は、利用できるすべての Online カスタム ポリシーを示しています。 これには、管理者が古いカスタム ポリシーを保持しながら、EnableSkypeUI フラグを切り替えられるように、柔軟性を考慮して作成された新しいポリシーが含まれています。 上のコマンドレットを使って、下のポリシーの 1 つをユーザーに付与してください。
  
|**ポリシー名**|**EnableSkypeUI**|
|:-----|:-----|
|
```
ClientPolicyDefaultPhoto
```

||
|
```
ClientPolicyDefaultPhotoDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoIMURL
```

||
|
```
ClientPolicyNoIMURLDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoIMURLPhoto
```

||
|
```
ClientPolicyNoIMURLPhotoDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingI
```

||
|
```
ClientPolicyNoSaveIMNoArchivingDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURL
```

||
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto
```

||
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingPhoto
```

||
|
```
ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI
```

|False  <br/> |
   
Windows PowerShell を使い始めるには、以下のトピックを参照してください。
  
- [Office 365 を管理する Windows PowerShell を使用する理由 6 つの理由]( https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Windows PowerShell で Office 365 を管理する最善の方法]( https://go.microsoft.com/fwlink/?LinkId=525142)
    
## 初めて起動するクライアントの動作

既定では、ユーザーが初めて Skype for Business を起動すると、前述のようにクライアント ポリシーを Lync クライアント エクスペリエンス ( `Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) に設定して、Lync クライアント エクスペリエンスを選んでいても、常に Skype for Business のユーザー インターフェイスが表示されます。 起動から数分後に、Lync モードに切り替えるかどうかを確認するメッセージが表示されます。
  
ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。
  
1. このトピックの最初に説明している手順に従って、クライアント ポリシーで Skype for Business ユーザー インターフェイスが無効に設定されていることを確認します。
    
2. ユーザーのコンピューターで、システム レジストリを更新します。 レジストリの更新は、ユーザーが初めて Skype for Business クライアントを起動する前に 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。
    
    [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync] キーに、新しい **バイナリ**値を作成します。
    
    [ **値の名前**] には「EnableSkypeUI」を指定し、[ **値のデータ**] には「00 00 00 00」を設定する必要があります。
    
    キーは、以下のようになります。
    
> [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab"=dword:00000001
    
    "CanShareOneNoteInCollab"=dword:00000001
    
    "CanAppShareInCollab"=dword:00000001
    
    "EnableSkypeUI"=hex:00,00,00,00
    
これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスが表示されるようになります。
  
### [ようこそ] 画面のチュートリアルの表示方法を制御する

ユーザーが Skype for Business クライアントを開くと、既定の動作では、最も一般的な 7 つのポップ ヒントが [ようこそ] 画面に表示されます。 [ようこそ] 画面の表示はオフにすることができますが、オフにしても、ユーザーはクライアント コンピューターで以下のレジストリ値を追加すれば、チュートリアルにアクセスできます。
  
[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync] キーに、新しい DWORD (32 ビット) 値を作成します。 [値の名前] には「IsBasicTutorialSeenByUser」を指定し、[値のデータ] には「1」を設定する必要があります。
  
キーは、以下のようになります。
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### クライアント チュートリアルをオフにする

ユーザーがチュートリアルにアクセスできないようにするには、以下のレジストリ値を指定して、クライアント チュートリアルをオフにします。
  
[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync] キーに、新しい DWORD (32 ビット) 値を作成します。 [値の名前] には「TutorialFeatureEnabled」を指定し、[値のデータ] には「0」を設定する必要があります。
  
```
"TutorialFeatureEnabled"=dword:00000000
```

[値のデータ] を「1」に設定すれば、チュートリアルをオンに戻すことができます。
  
## ドメインに参加しているコンピューターでレジストリを変更するグループ ポリシー オブジェクトを作成する

ユーザーが初めて Skype for Business クライアントを起動したときに、Lync クライアント エクスペリエンスを表示するためのレジストリの更新は、1 回だけ行う必要があります。 グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。
  
以下の手順では、ユーザーが初めて Skype for Business を起動したときに、Lync クライアント エクスペリエンスが表示されるようにレジストリを変更する方法について説明します。 この手順を使って、前述のように [ようこそ] 画面のチュートリアルを無効にするために、レジストリを更新することもできます。
  
 **GPO を作成するには**
  
1. **グループ ポリシー管理コンソール**を起動します。
    
    グループ ポリシーの管理コンソールを使用する方法については、[グループ ポリシー管理コンソール](https://go.microsoft.com/fwlink/?LinkId=532759)を参照してください。
    
2. [ **グループ ポリシー オブジェクト**] ノードを右クリックして、メニューから [ **新規作成**] を選びます。
    
3. [ **新しい GPO**] ダイアログ ボックスに、「MakeLyncDefaultUI」などの GPO 名を入力して、[ **OK**] をクリックします。
    
4. 作成した新しい GPO を右クリックして、メニューから [ **編集**] を選びます。
    
5. [ **グループ ポリシー管理エディター**] で、[ **ユーザーの構成**]、[ **ユーザー設定**]、[ **Windows 設定**] の順に展開して、[ **レジストリ**] ノードを選びます。
    
6. [ **レジストリ**] ノードを右クリックして、[ **新規作成**]、[ **レジストリ項目**] の順に選びます。
    
7. [ **新しいレジストリのプロパティ**] ダイアログ ボックスで、以下のように項目を更新します。
    
|**フィールド**|**選択または入力する値**|
|:-----|:-----|
|**操作** <br/> |**作成** <br/> |
|**ハイブ** <br/> | HKEY_CURRENT_USER <br/> |
|**キー パス** <br/> |Software\\Microsoft\\Office\\Lync  <br/> |
|**値の名前** <br/> |EnableSkypeUI  <br/> |
|**値の種類** <br/> |REG_BINARY  <br/> |
|**値のデータ** <br/> |00000000  <br/> |
   
8. [ **OK**] をクリックして変更を保存し、GPO を閉じます。
    
次に、ポリシーを割り当てる OU などのユーザー グループに、作成した GPO を接続する必要があります。
  
 **GPO を使用して、ポリシーを割り当てる**
  
1. [グループ ポリシー管理コンソール] で、ポリシーを割り当てる OU を右クリックして、[ **既存の GPO にリンクする**] を選びます。
    
2. [ **GPO の選択**] ダイアログ ボックスで、作成済みの GPO を選んで、[ **OK**] を選びます。
    
3. ターゲット ユーザーのコンピューターで、コマンド プロンプトを開いて、以下のコマンドを入力します。
    
    **gpupdate /target:user**
    
    GPO の適用中、"ポリシーを更新しています..." というメッセージが表示されます。 処理が完了すると、"ユーザー ポリシーの更新が正常に完了しました" というメッセージが表示されます。
    
4. コマンド プロンプトに、以下のコマンドを入力します。
    
    **gpresult /r**
    
    "割り当て済みのグループ ポリシー オブジェクト" と表示され、その下に作成済みの GPO の名前が表示されます。
    
レジストリの内容を調べれば、ユーザーのコンピューターで GPO によってレジストリが正常に更新されたことを確認することもできます。 レジストリ エディターを開いて、[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync] キーに移動します。 GPO によってレジストリが正常に更新されていれば、「0」が設定された EnableSkypeUI という名前の値が表示されます。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  

