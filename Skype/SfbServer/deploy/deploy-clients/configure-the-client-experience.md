---
title: Skype for Business 2015 でクライアントエクスペリエンスを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '概要: このトピックでは、Skype for Business ユーザーのクライアントエクスペリエンスを構成する方法について説明します。'
ms.openlocfilehash: bf6245b5b26875c7437990f09dd101ece01b1b47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298285"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Skype for Business 2015 でクライアントエクスペリエンスを構成する
 
**概要:** このトピックでは、Skype for Business 2015 ユーザーのクライアントエクスペリエンスを構成する方法について説明します。
  
Skype for Business 2015 は、Skype コンシューマーの製品エクスペリエンスに基づいた新しいユーザーエクスペリエンスを提供します。 Skype for Business には、Lync のすべての機能に加えて、簡単なコントロールと使い慣れたアイコンが付いた新機能が用意されています。 新しいクライアントエクスペリエンスの詳細については、「 [Skype For business の紹介](https://go.microsoft.com/fwlink/?LinkId=529022)」を参照してください。
  
Skype for Business Server では、新しい Skype for Business クライアントエクスペリエンスと Lync クライアントエクスペリエンスがサポートされています。 管理者は、ユーザー用に優先するクライアント エクスペリエンスを選択できます。 たとえば、新しい Skype for Business のエクスペリエンスで組織内のユーザーが完全にトレーニングを受けられるまで、Lync クライアントエクスペリエンスを展開することができます。 または、すべてのユーザーを Skype for Business Server にアップグレードしていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーが同じクライアントエクスペリエンスを使用できるようにする必要があります。
  
> [!IMPORTANT]
> 組織に Skype for Business Server と Lync Server の両方が展開されている場合、既定のクライアントエクスペリエンスはサーバーのバージョンと UI の設定によって異なります。 ユーザーが Skype for Business を初めて起動すると、Lync クライアントエクスペリエンスを選んだ場合でも、常に Skype for business のユーザーインターフェイスが表示されます。 数分後に、ユーザーは Lync モードに切り替えるように求められます。 詳細については、このトピックの後半にある「**最初の起動クライアントの動作**」を参照してください。
  
> [!NOTE]
> Lync 2013 クライアントエクスペリエンスは、Skype for Business 2016 クライアントバージョン以降では使用できません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
## <a name="configure-the-client-experience"></a>クライアント エクスペリエンスの構成

以下のように、EnableSkypeUI パラメーターを指定して **Set-CSClientPolicy** コマンドレットを使用すると、組織のユーザーに表示されるクライアント エクスペリエンスを指定できます。
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

上記の XdsIdentity は、グローバル ポリシーまたは名前付きサイト ポリシーを指します。
  
次のコマンドは、組織内のすべてのユーザーに対してグローバルポリシーの影響を受ける Skype for Business クライアントのエクスペリエンスを選択します (「サイトまたはユーザー固有のポリシーはグローバルポリシーを上書きします)」を選択します。 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

次のコマンドでは、組織内のすべてのユーザーに対して、グローバルポリシーの影響を受ける Lync クライアントエクスペリエンスが選択されます。
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

次のコマンドは、Redmond サイト内のすべてのユーザーに対して Skype for Business クライアントエクスペリエンスを選択します。
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

組織内の特定のユーザーに対してクライアントエクスペリエンスを構成する場合は、**新しい**ユーザーポリシーを作成して、**グラント clientpolicy**を使用して特定のユーザーにポリシーを割り当てることができます。コマンドレット.
  
たとえば、次のコマンドは、Skype for Business クライアントエクスペリエンスを選択する新しいクライアントポリシー、SalesClientUI を作成します。
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

次のコマンドを実行すると、Sales 部門のすべてのメンバーにポリシー SalesClientUI が割り当てられます。
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>最初の起動クライアントの動作

既定では、ユーザーが Skype for business 2015 を初めて起動したときに、以下のように、EnableSkypeUI パラメーターの値を $False に設定して、Lync クライアント環境を選択した場合でも、Skype for Business のユーザーインターフェイスが表示されます。先に。 起動から数分後に、Lync モードに切り替えるかどうかを確認するメッセージが表示されます。
  
ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。
  
1. 前に説明した`EnableSkypeUI`ように使用しているポリシーで、の値が $False に設定されていることを確認します。
    
2. ユーザーのコンピューターで、システム レジストリを更新します。 レジストリの更新は、ユーザーが初めて Skype for Business クライアントを起動する前に 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。
    
    **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** キーに新しい [**バイナリ**] 値を作成します。
    
    The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.
    
    キーは、以下のようになります。
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスが表示されるようになります。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>ようこそ画面のチュートリアルの表示を制御する

ユーザーが Skype for Business クライアントを開くと、既定の動作では [ようこそ] 画面が表示されます。これには、*ほとんどのユーザーからの質問に対する7つのヒント*が含まれています。 You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーに新しい [**DWORD (32 ビット) 値**] を作成します。[**値の名前**] に「**IsBasicTutorialSeenByUser**」と入力し、[**値のデータ**] を「**1**」に設定する必要があります。
  
キーは次のようになります。
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>クライアント チュートリアルをオフにする

ユーザーがチュートリアルにアクセスできないようにするには、次のレジストリ値を指定してクライアント チュートリアルを無効にします。
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーに新しい [**DWORD (32 ビット) 値**] を作成します。[**値の名前**] に「**TutorialFeatureEnabled**」と入力し、[**値データ**] を「**0**」に設定する必要があります。
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

チュートリアルを有効に戻すには、[**値のデータ**] を「**1**」に設定します。
  
## <a name="default-client-behaviors"></a>既定のクライアントの動作

組織に Skype for Business Server と Lync Server の両方が展開されている場合、クライアントのエクスペリエンスはサーバーのバージョンと Skype の UI の設定によって異なります。 以下の表に、サーバー バージョンと UI 設定に基づく最初のクライアント エクスペリエンスを示します。
  

|**サーバー バージョン**|**EnableSkypeUI 設定**|**クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Server |既定  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。  <br/> |
|Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)  <br/> |既定  <br/> |ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。  <br/> |
|Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)  <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)  <br/> |False  <br/> |ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。  <br/> |
|Lync Server 2010 または Lync Server 2013 (パッチなし)  <br/> |既定  <br/> |ユーザーが Lync モードに切り替えるように求められた (ユーザーは後で Skype for Business に切り替えることができません)  <br/> |
   
次の表は、管理者が Skype UI エクスペリエンスの初期設定を変更したときのクライアントエクスペリエンスを示しています。
  

|**サーバー バージョン**|**EnableSkypeUI 設定**|**クライアント UI = Lync**|**クライアント UI = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |Skype for Business に切り替えるように求められたユーザー  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Lync モード  <br/> |Lync モードへの切り替えを求められたユーザー  <br/> |
|Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)  <br/> |True  <br/> |Skype for Business に切り替えるように求められたユーザー  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)  <br/> |False  <br/> |Lync モード  <br/> |Lync モードへの切り替えを求められたユーザー  <br/> |
|Lync Server 2010 または Lync Server 2013 (パッチなし)  <br/> |既定  <br/> |Lync モード (Skype for Business に切り替えることはできません)  <br/> |Lync モード (Skype for Business に切り替えることはできません)  <br/> |
   
Skype for Business クライアントの構成を管理するために必要な更新プログラムのバージョンは次のとおりです。
  
- Lync Server 2010-Lync Server 2010 用の2015年2月の累積更新プログラム (4.0.7577.710)。 詳細については、「 [Lync Server 2010 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532771)」を参照してください。
    
- Lync Server 2013-Lync Server 2013 用に2014年12月の累積更新プログラム (5.0.8308.857)。 詳細については、「 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532772)」を参照してください。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインに参加しているコンピューターのレジストリを変更するグループ ポリシー オブジェクトを作成する

ユーザーが Skype for Business 2015 クライアントを初めて起動したときに Lync クライアントエクスペリエンスを表示するためのレジストリ更新は、1回だけ実行する必要があります。 グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。 
  
次の手順では、ユーザーが Skype for Business 2015 クライアントを初めて起動したときに Lync クライアントエクスペリエンスが表示されるようにレジストリを変更する方法について説明します。 この手順は、レジストリを更新して前述のようこそ画面のチュートリアルを無効にするためにも使用できます。
  
### <a name="to-create-the-gpo"></a>GPO を作成するには

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
   |**キーのパス** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**値の名前** <br/> |EnableSkypeUI  <br/> |
   |**値の種類** <br/> |REG_BINARY  <br/> |
   |**値のデータ** <br/> |00000000  <br/> |
   
8. [ **OK**] をクリックして変更を保存し、GPO を閉じます。
    
次に、作成した GPO を、ポリシーを割り当てるユーザー グループ (OU など) にリンクする必要があります。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>GPO を使用してポリシーを割り当てるには

1. グループ ポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、[**既存の GPO のリンク**] を選びます。
    
2. [ **GPO の選択**] ダイアログ ボックスで、作成済みの GPO を選んで、[ **OK**] を選びます。
    
3. ターゲット ユーザーのコンピューターで、コマンド プロンプトを開いて、以下のコマンドを入力します。
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. コマンド プロンプトに、以下のコマンドを入力します。
    
    **gpresult /r**
    
    [適用されたグループ ポリシーオブジェクト] と、作成した GPO 名が下に表示されます。
    
また、レジストリを確認して、GPO でユーザーのコンピューターのレジストリが正常に更新されたことを確認する方法もあります。レジストリ エディターを開き、**[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** キーに移動します。GPO によってレジストリが正常に更新された場合、値が 0 の EnableSkypeUI が表示されます。
  

