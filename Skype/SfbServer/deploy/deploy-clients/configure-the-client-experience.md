---
title: Skype for Business 2015 でのクライアント エクスペリエンスの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '概要: このトピックでは、Skype for Business ユーザーのクライアント エクスペリエンスを構成する方法について説明します。'
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805957"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Skype for Business 2015 でのクライアント エクスペリエンスの構成
 
**概要:** このトピックでは、Skype for Business 2015 ユーザーのクライアント エクスペリエンスを構成する方法について説明します。
  
Skype for Business 2015 は、Skype コンシューマー製品のエクスペリエンスに基づく新しいユーザー エクスペリエンスを提供します。 Skype for Business は、Lync のすべての機能に加えて、簡素化されたコントロールと使い慣れたアイコンを備え、新機能を提供します。 新しいクライアント エクスペリエンスの詳細については、「Skype for Business の探索」 [を参照してください](https://go.microsoft.com/fwlink/?LinkId=529022)。
  
Skype for Business Server は、新しい Skype for Business クライアント エクスペリエンスと Lync クライアント エクスペリエンスをサポートしています。 管理者は、ユーザーに優先するクライアント エクスペリエンスを選択できます。 たとえば、組織内のユーザーが新しい Skype for Business エクスペリエンスのトレーニングを完全に受け入れるまで、Lync クライアント エクスペリエンスを展開できます。 または、まだすべてのユーザーを Skype for Business Server にアップグレードしていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーに同じクライアント エクスペリエンスを提供できます。
  
> [!IMPORTANT]
> 組織に Skype for Business Server と Lync Server の両方が展開されている場合、既定のクライアント エクスペリエンスはサーバーのバージョンと UI 設定によって異なります。 ユーザーが初めて Skype for Business を起動すると、Lync クライアント エクスペリエンスを選択した場合でも、常に Skype for Business ユーザー インターフェイスが表示されます。 数分後、ユーザーは Lync モードに切り替える必要があります。 詳細については、このトピックの **「最初の起動クライアントの動作** 」を参照してください。
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョン以降のオプションではありません。 Lync 2013 クライアントを使用するためのクライアント環境の構成を試みる前に、クライアントのバージョンを確認して、番号 16 で始まるのではないか確認してください。例: 16.x.x.x。 
  
## <a name="configure-the-client-experience"></a>クライアント エクスペリエンスの構成

EnableSkypeUI パラメーターで **Set-CSClientPolicy** コマンドレットを使用すると、組織内のユーザーに表示されるクライアント エクスペリエンスを指定できます。
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

ここで、XdsIdentity はグローバル ポリシーまたは名前付きサイト ポリシーを参照します。
  
次のコマンドは、グローバル ポリシーの影響を受ける組織内のすべてのユーザーの Skype for Business クライアント エクスペリエンスを選択します (サイトまたはユーザー固有のポリシーはグローバル ポリシーより優先されます)。 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

次のコマンドは、グローバル ポリシーの影響を受ける組織内のすべてのユーザーの Lync クライアント エクスペリエンスを選択します。
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

次のコマンドは、Redmond サイト内のすべてのユーザーの Skype for Business クライアント エクスペリエンスを選択します。
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

組織内の特定のユーザーのクライアント エクスペリエンスを構成する場合は **、New-CsClientPolicy** コマンドレットを使用して新しいユーザー ポリシーを作成し **、Grant-CsClientPolicy** コマンドレットを使用してポリシーを特定のユーザーに割り当てできます。
  
たとえば、次のコマンドを実行すると、Skype for Business クライアント エクスペリエンスを選択する新しいクライアント ポリシー SalesClientUI が作成されます。
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

次のコマンドでは、Sales 部門のすべてのメンバーにポリシー SalesClientUI を割り当てる必要があります。
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>最初の起動クライアントの動作

既定では、ユーザーが Skype for Business 2015 を初めて起動すると、前述のように EnableSkypeUI パラメーターの値を $False に設定して Lync クライアント エクスペリエンスを選択した場合でも、Skype for Business ユーザー インターフェイスが常に表示されます。 数分後、ユーザーは Lync モードに切り替える必要があります。
  
ユーザーが初めて Skype for Business クライアントを起動するときに Lync ユーザー インターフェイスを表示する場合は、更新後にクライアントを初めて起動する前に、次の手順を実行します。
  
1. 前に説明したように、使用しているポリシー$False値が設定  `EnableSkypeUI` されている必要があります。
    
2. ユーザーのコンピューターのシステム レジストリを更新します。 これは、ユーザーが初めて Skype for Business クライアントを起動する前に行う必要があります。この操作は 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、後のセクションを参照してください。
    
    **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーで**、新しい Binary 値を **作成** します。
    
    値 **の名前は** **EnableSkypeUI** にする必要があります。 **また、値** データは **00 00 00 00** に設定する必要があります。
    
    キーは次のようになります。
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

ユーザーが初めて Skype for Business クライアントを起動すると、Lync ユーザー インターフェイスが表示されます。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>ようこそ画面のチュートリアルの表示を制御する

ユーザーが Skype for Business クライアントを開いた場合の既定の動作では、ほとんどのユーザーが求める 7 つのクイック ヒントを含むようこそ画面  *が表示されます*。 [ようこそ] 画面の表示をオフにすることもできますが、クライアント コンピューターで次のレジストリ値を追加することで、ユーザーがチュートリアルにアクセスできます。
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーで、新しい **DWORD (32 ビット) 値を作成します**。 値 **の名前は** **IsBasicTu valuelSeenByUser** で **、Value** データは **1** に設定する必要があります。
  
キーは次のようになります。
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>クライアントチュートリアルをオフにする

ユーザーがチュートリアルにアクセスできない場合は、次のレジストリ値を使用してクライアント チュートリアルをオフにできます。
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーで、新しい **DWORD (32 ビット) 値を作成します**。 値 **の名前は** **TutorialFeatureEnabled** で、 **値** データは **0** に設定する必要があります。
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

このチュートリアルを有効に戻すには、値データ **を** **1 に設定します**。
  
## <a name="default-client-behaviors"></a>既定のクライアント動作

組織に Skype for Business Server と Lync Server の両方が展開されている場合、クライアント エクスペリエンスはサーバーのバージョンと Skype UI 設定によって異なります。 次の表に、サーバーバージョンと UI 設定に基づく初期クライアント エクスペリエンスを示します。
  

|**サーバーのバージョン**|**EnableSkypeUI 設定**|**クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Server |既定値  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |正  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |ユーザーが Lync モードに切り替える必要があります (UI 設定を [Skype for Business] に変更した場合、ユーザーは後で Skype for Business に$true)  <br/> |
|Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)  <br/> |既定値  <br/> |ユーザーが Lync モードに切り替える必要があります (UI 設定を [Skype for Business] に変更した場合、ユーザーは後で Skype for Business に$true)  <br/> |
|Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)  <br/> |正  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)  <br/> |False  <br/> |ユーザーが Lync モードに切り替える必要があります (UI 設定を [Skype for Business] に変更した場合、ユーザーは後で Skype for Business に$true)  <br/> |
|Lync Server 2010 または Lync Server 2013 (パッチなし)  <br/> |既定値  <br/> |ユーザーが Lync モードに切り替える必要があります (ユーザーは後で Skype for Business に切り替えできません)  <br/> |
   
次の表に、管理者が Skype UI エクスペリエンスの初期設定を変更した場合のクライアント エクスペリエンスを示します。
  

|**サーバーのバージョン**|**EnableSkypeUI 設定**|**クライアント UI = Lync**|**クライアント UI = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |正  <br/> |ユーザーが Skype for Business に切り替える必要がありました  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Lync モード  <br/> |ユーザーが Lync モードに切り替える必要がありました  <br/> |
|Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)  <br/> |正  <br/> |ユーザーが Skype for Business に切り替える必要がありました  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)  <br/> |False  <br/> |Lync モード  <br/> |ユーザーが Lync モードに切り替える  <br/> |
|Lync Server 2010 または Lync Server 2013 (パッチなし)  <br/> |既定値  <br/> |Lync モード (Skype for Business に切り替えできない)  <br/> |Lync モード (Skype for Business に切り替えできない)  <br/> |
   
Skype for Business クライアントの構成を管理するために必要な修正プログラムのバージョンは次のとおりです。
  
- Lync Server 2010 - 2015 年 2 月 Lync Server 2010 の累積的な更新プログラム (4.0.7577.710) 詳細については[、「Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)の更新プログラム」を参照してください。
    
- Lync Server 2013 - Lync Server 2013 用の 2014 年 12 月の累積的な更新プログラム (5.0.8308.857)。 詳細については [、「Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772)の更新プログラム」を参照してください。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>グループ ポリシー オブジェクトを作成してドメインに参加しているコンピューターのレジストリを変更する

ユーザーが初めて Skype for Business 2015 クライアントを起動する場合に Lync クライアント エクスペリエンスを表示するレジストリ更新は、1 回だけ行う必要があります。 グループ ポリシー オブジェクト (GPO) を使用してレジストリを更新する場合は、値データを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO が適用されると、新しい値が存在しない場合、GPO によって作成され、値データが 0 に設定されます。 
  
次の手順では、ユーザーが初めて Skype for Business 2015 クライアントを起動する場合に Lync クライアント エクスペリエンスが表示されるレジストリを変更する方法について説明します。 この手順を使用してレジストリを更新し、前述のようにようこそ画面のチュートリアルを無効にできます。
  
### <a name="to-create-the-gpo"></a>GPO を作成するには

1. グループ ポリシー **管理コンソールを起動します**。
    
    グループ ポリシー管理コンソールの使い方については、グループ ポリシー管理コンソール [を参照してください](https://go.microsoft.com/fwlink/?LinkId=532759)。
    
2. [グループ ポリシー オブジェクト] **ノードを右クリックし** 、メニューの **[新規** ] を選択します。
    
3. [新 **しい GPO]** ダイアログで、GPO の名前 (MakeLyncDefaultUI など) を入力し **、[OK]** をクリックします。
    
4. 作成した新しい GPO を右クリックし、メニューから **[** 編集] を選択します。
    
5. グループ ポリシー **管理エディターで**、[ユーザーの構成]を展開し、[基本設定] を展開し **、[Windows の** 設定] を展開して、[レジストリ] ノード **を選択** します。
    
6. レジストリ ノードを右クリックし **、[** 新しいレジストリ項目]  >  **を選択します**。
    
7. [新 **しいレジストリのプロパティ] ダイアログ** で、以下を更新します。
    
   |**Field**|**選択または入力する値**|
   |:-----|:-----|
   |**操作** <br/> |**Create** <br/> |
   |**ハイブ** <br/> | HKEY_CURRENT_USER <br/> |
   |**キー パス** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**値の名前** <br/> |EnableSkypeUI  <br/> |
   |**値の型** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. **[OK]** をクリックして変更を保存し、GPO を閉じます。
    
次に、作成した GPO を、ポリシーを割り当てるユーザーのグループ (OU など) にリンクする必要があります。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>GPO を使用してポリシーを割り当てるには

1. グループ ポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、既存の GPO へのリンク **を選択します**。
    
2. [GPO **の選択] ダイアログ** で、作成した GPO を選択し **、[OK]** を選択します。
    
3. ターゲット ユーザーのコンピューターで、コマンド プロンプトを開き、次のコマンドを入力します。
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. コマンド プロンプトで、以下のコマンドを入力します。
    
    **gpresult /r**
    
    [割り当てられたグループ ポリシー オブジェクト] が表示され、下に作成した GPO の名前が表示されます。
    
また、レジストリを調べて、GPO がユーザーのコンピューター上のレジストリを正常に更新したのを確認することもできます。 レジストリ エディターを開き **、[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーに移動** します。 GPO がレジストリを正常に更新すると、EnableSkypeUI という名前の値が 0 で表示されます。
  

