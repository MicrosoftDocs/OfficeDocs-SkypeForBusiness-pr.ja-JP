---
title: Skype for Business 2015 でクライアント エクスペリエンスを構成する
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
description: '概要: Skype for Business ユーザーのクライアント エクスペリエンスを構成する方法については、このトピックを参照してください。'
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096011"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Skype for Business 2015 でクライアント エクスペリエンスを構成する
 
**概要:** このトピックでは、Skype for Business 2015 ユーザーのクライアント エクスペリエンスを構成する方法について説明します。
  
Skype for Business 2015 は、Skype コンシューマー製品エクスペリエンスに基づく新しいユーザー エクスペリエンスを提供します。 Lync のすべての機能に加えて、Skype for Business は、簡略化されたコントロールと使い慣れたアイコンを備えて新機能を提供します。 新しいクライアント エクスペリエンスの詳細については [、「Explore Skype for Business」を参照してください](https://go.microsoft.com/fwlink/?LinkId=529022)。
  
Skype for Business Server は、新しい Skype for Business クライアント エクスペリエンスと Lync クライアント エクスペリエンスをサポートします。 管理者は、ユーザーに優先するクライアント エクスペリエンスを選択できます。 たとえば、組織内のユーザーが新しい Skype for Business エクスペリエンスで完全にトレーニングされるまで、Lync クライアント エクスペリエンスを展開できます。 または、すべてのユーザーを Skype for Business Server にまだアップグレードしていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーに同じクライアント エクスペリエンスを提供する必要があります。
  
> [!IMPORTANT]
> 組織で Skype for Business Server と Lync Server の両方が展開されている場合、既定のクライアント エクスペリエンスはサーバーのバージョンと UI 設定によって異なります。 ユーザーが初めて Skype for Business を起動すると、Lync クライアント エクスペリエンスを選択した場合でも、Skype for Business ユーザー インターフェイスが常に表示されます。 数分後、ユーザーは Lync モードに切り替える必要があります。 詳細については、このトピックの「 **クライアントの動作を最初に起動する** 」を参照してください。
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョン以降のオプションではありません。 Lync 2013 クライアントを使用するクライアント環境を構成する前に、クライアントのバージョンを確認して、番号 16 で始まるのを確認してください。たとえば、16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>クライアント エクスペリエンスの構成

EnableSkypeUI パラメーターを使用して **Set-CSClientPolicy** コマンドレットを使用して、組織内のユーザーに表示されるクライアント エクスペリエンスを指定できます。
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

ここで、XdsIdentity はグローバル ポリシーまたは名前付きサイト ポリシーを参照します。
  
次のコマンドは、グローバル ポリシーの影響を受ける組織内のすべてのユーザーの Skype for Business クライアント エクスペリエンスを選択します (グローバル ポリシーは、サイトまたはユーザー固有のポリシーによって上書きされます)。 
  
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

組織内の特定のユーザーに対してクライアント エクスペリエンスを構成する場合は **、New-CsClientPolicy** コマンドレットを使用して新しいユーザー ポリシーを作成し **、Grant-CsClientPolicy** コマンドレットを使用してポリシーを特定のユーザーに割り当てできます。
  
たとえば、次のコマンドは、Skype for Business クライアント エクスペリエンスを選択する新しいクライアント ポリシー SalesClientUI を作成します。
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

次のコマンドは、Sales 部門のすべてのメンバーにポリシー SalesClientUI を割り当てる。
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>最初の起動クライアントの動作

既定では、ユーザーが Skype for Business 2015 を初めて起動すると、前述のように EnableSkypeUI パラメーターの値を $False に設定して Lync クライアント エクスペリエンスを選択した場合でも、Skype for Business ユーザー インターフェイスが常に表示されます。 数分後、ユーザーは Lync モードに切り替える必要があります。
  
ユーザーが Skype for Business クライアントを初めて起動するときに Lync ユーザー インターフェイスを表示する場合は、更新後にクライアントを初めて開始する前に、次の手順を実行します。
  
1. 前に説明したように、使用しているポリシー$Falseの値が設定  `EnableSkypeUI` されているのを確認します。
    
2. ユーザーのコンピューター上のシステム レジストリを更新します。 これは、ユーザーが初めて Skype for Business クライアントを起動する前に行う必要があります。この操作は 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、後のトピックのセクションを参照してください。
    
    **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーで**、新しい Binary 値を **作成** します。
    
    値 **名は** **EnableSkypeUI** で **、Value** データは **00 00 00 00 に設定する必要があります**。
    
    キーは次のようになります。
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

ユーザーが Skype for Business クライアントを初めて起動すると、Lync ユーザー インターフェイスが表示されます。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>ようこそ画面のチュートリアルの表示を制御する

ユーザーが Skype for Business クライアントを開く場合、既定の動作は、ほとんどのユーザーが求める 7 つのクイック ヒントを含むようこそ  *画面を表示します*。 [ようこそ] 画面の表示をオフにできますが、クライアント コンピューターに次のレジストリ値を追加することで、ユーザーがチュートリアルにアクセスできます。
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync] キーで**、新しい **DWORD (32 ビット) の値を作成します**。 値 **名は** **IsBasicTutorialSeenByUser** である必要があります。 **値** データは **1 に設定する必要があります**。
  
キーは次のようになります。
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>クライアントのチュートリアルをオフにする

ユーザーがチュートリアルにアクセスできない場合は、次のレジストリ値を使用してクライアント チュートリアルをオフにできます。
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync] キーで**、新しい **DWORD (32 ビット) の値を作成します**。 値 **名は** **TutorialFeatureEnabled** で **、Value** データは **0** に設定する必要があります。
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

値データを 1 に設定すると、チュートリアル **をオンに****戻します**。
  
## <a name="default-client-behaviors"></a>既定のクライアント動作

組織で Skype for Business Server と Lync Server の両方が展開されている場合、クライアント エクスペリエンスはサーバーのバージョンと Skype UI 設定によって異なります。 次の表に、サーバーのバージョンと UI 設定に基づく初期クライアント エクスペリエンスを示します。
  

|**サーバーのバージョン**|**EnableSkypeUI の設定**|**クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Server |既定値  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |Lync モードへの切り替えを求めるユーザー (UI 設定を [Skype for Business] に変更した場合は、後で Skype for Business に切り$true)  <br/> |
|Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)  <br/> |既定値  <br/> |Lync モードへの切り替えを求めるユーザー (UI 設定を [Skype for Business] に変更した場合は、後で Skype for Business に切り$true)  <br/> |
|Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)  <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)  <br/> |False  <br/> |Lync モードへの切り替えを求めるユーザー (UI 設定を [Skype for Business] に変更した場合は、後で Skype for Business に切り$true)  <br/> |
|Lync Server 2010 または Lync Server 2013 (パッチなし)  <br/> |既定値  <br/> |Lync モードへの切り替えを求めるユーザー (ユーザーは後で Skype for Business に切り替えできません)  <br/> |
   
次の表は、管理者が Skype UI エクスペリエンスの初期設定を変更した場合のクライアント エクスペリエンスを示しています。
  

|**サーバーのバージョン**|**EnableSkypeUI の設定**|**クライアント UI = Lync**|**クライアント UI = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |Skype for Business への切り替えを求めるユーザー  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Lync モード  <br/> |Lync モードへの切り替えを求めるユーザー  <br/> |
|Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)  <br/> |True  <br/> |Skype for Business への切り替えを求めるユーザー  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)  <br/> |False  <br/> |Lync モード  <br/> |Lync モードへの切り替えを求めるユーザー  <br/> |
|Lync Server 2010 または Lync Server 2013 (パッチなし)  <br/> |既定値  <br/> |Lync モード (Skype for Business に切り替えできない)  <br/> |Lync モード (Skype for Business に切り替えできない)  <br/> |
   
Skype for Business クライアントの構成を管理するために必要なパッチ バージョンは次のとおりです。
  
- Lync Server 2010 - 2015 年 2 月 Lync Server 2010 の累積的な更新プログラム (4.0.7577.710) 詳細については [、「Updates for Lync Server 2010」を参照してください。](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - 2014 年 12 月 Lync Server 2013 の累積的な更新プログラム (5.0.8308.857) 詳細については [、「Updates for Lync Server 2013」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインに参加しているコンピューター上のレジストリを変更するグループ ポリシー オブジェクトを作成する

ユーザーが Skype for Business 2015 クライアントを初めて起動した場合に Lync クライアント エクスペリエンスを表示するレジストリ更新プログラムは、1 回だけ実行する必要があります。 グループ ポリシー オブジェクト (GPO) を使用してレジストリを更新する場合は、Value データを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO が適用されると、新しい値が存在しない場合、GPO は GPO を作成し、Value データを 0 に設定します。 
  
次の手順では、ユーザーが Skype for Business 2015 クライアントを初めて起動した場合に Lync クライアント エクスペリエンスが表示されるレジストリを変更する方法について説明します。 前述のように、この手順を使用してレジストリを更新して、ようこそ画面のチュートリアルを無効にできます。
  
### <a name="to-create-the-gpo"></a>GPO を作成するには

1. グループ ポリシー管理 **コンソールを起動します**。
    
    グループ ポリシー管理コンソールの使用方法については、「グループ ポリシー管理コンソール [」を参照してください](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))。
    
2. [グループ ポリシー オブジェクト] ノード **を右クリックし** 、メニューの **[新規]** を選択します。
    
3. [新 **しい GPO]** ダイアログで、GPO の名前 (MakeLyncDefaultUI など) を入力し **、[OK] をクリックします**。
    
4. 作成した新しい GPO を右クリックし、メニューから **[編集]** を選択します。
    
5. グループ ポリシー **管理エディターで**、[ユーザー構成] を展開し、[基本設定] を展開し **、[Windows 設定**] を展開し、[レジストリ]**ノードを選択** します。
    
6. [レジストリ] ノードを **右** クリックし、[新しい **レジストリ** アイテム]  >  **を選択します**。
    
7. [新しい **レジストリのプロパティ] ダイアログで** 、次の項目を更新します。
    
   |**Field**|**選択または入力する値**|
   |:-----|:-----|
   |**Action** <br/> |**Create** <br/> |
   |**ハイブ** <br/> | HKEY_CURRENT_USER <br/> |
   |**キー パス** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**値の名前** <br/> |EnableSkypeUI  <br/> |
   |**値の型** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. **[OK]** をクリックして変更を保存し、GPO を閉じます。
    
次に、作成した GPO を、ポリシーを割り当てるユーザーのグループ (OU など) にリンクする必要があります。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>GPO を使用してポリシーを割り当てるには

1. グループ ポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、[既存の GPO へのリンク **] を選択します**。
    
2. [GPO **の選択]** ダイアログで、作成した GPO を選択し **、[OK] を選択します**。
    
3. ターゲット ユーザーのコンピューターで、コマンド プロンプトを開き、次のコマンドを入力します。
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. コマンド プロンプトで、以下のコマンドを入力します。
    
    **gpresult /r**
    
    [割り当てられたグループ ポリシー オブジェクト] が表示され、作成した GPO の名前が下に表示されます。
    
また、レジストリを調べることによって、GPO がユーザーのコンピューター上のレジストリを正常に更新されたことを確認することもできます。 [レジストリ エディター] を開き **、[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーに移動** します。 GPO がレジストリを正常に更新すると、値 0 の EnableSkypeUI という名前の値が表示されます。
