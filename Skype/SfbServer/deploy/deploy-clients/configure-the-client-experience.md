---
title: ビジネス 2015年の Skype のクライアント エクスペリエンスを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '概要: は、Skype のビジネス ユーザー向けのクライアント エクスペリエンスを構成する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: 65ca5592c3994cfcbb2703d22bc510a3b84b3507
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895392"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>ビジネス 2015年の Skype のクライアント エクスペリエンスを構成します。
 
**の概要:** ビジネス 2015年ユーザー Skype のクライアント エクスペリエンスを構成する方法の詳細については、このトピックを参照してください。
  
ビジネス 2015年の Skype は、Skype のコンシューマー製品の経験に基づく新たなユーザー エクスペリエンスを提供します。 Lync のすべての機能、に加えては、ビジネス用の Skype は、簡略化されたコントロールと一般的なアイコンでの新機能を提供します。 新しいクライアント エクスペリエンスの詳細については、[ビジネス用の Skype の表示](https://go.microsoft.com/fwlink/?LinkId=529022)を参照してください。
  
ビジネス サーバーの Skype では、Lync クライアントの操作性だけでなく、クライアントの機能をビジネスの新しい Skype をサポートしています。 管理者は、ユーザー用に優先するクライアント エクスペリエンスを選択できます。 などの業務経験の新しい Skype で、組織内のユーザーがトレーニングを完全にするまでは、Lync クライアント エクスペリエンスを展開する可能性があります。 または、ないまだにアップグレードするすべてのユーザー Skype ビジネス サーバーは、場合すべてのユーザーに、すべてが新しいサーバーにアップグレードするまで同一のクライアントの経験があります。
  
> [!IMPORTANT]
> 組織ビジネス サーバーの両方の Skype には、Lync Server の展開、サーバーのバージョン、および UI の設定によって既定のクライアントの動作が異なります。 ユーザーは、最初にビジネス用の Skype を起動すると、Lync クライアント エクスペリエンスを選択した場合でも、Skype のビジネス ユーザー インターフェイスが表示されます常に。 数分後、ユーザーは、Lync のモードに切り替えるには求められます。 詳細については、このトピックの後半にある「**最初の起動クライアントの動作**」を参照してください。
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype のビジネス 2016年のクライアント バージョンまたはそれ以降のオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
## <a name="configure-the-client-experience"></a>クライアント エクスペリエンスの構成

以下のように、EnableSkypeUI パラメーターを指定して **Set-CSClientPolicy** コマンドレットを使用すると、組織のユーザーに表示されるクライアント エクスペリエンスを指定できます。
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

上記の XdsIdentity は、グローバル ポリシーまたは名前付きサイト ポリシーを指します。
  
次のコマンドは、グローバル ポリシーによって影響を受ける、組織のビジネス クライアント エクスペリエンスのすべてのユーザー用の Skype を選択 (サイトまたはユーザー固有のポリシー、グローバル ポリシーをオーバーライドすることを思い出してください)。 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

次のコマンドは、グローバル ポリシーによって影響を受ける、組織内のすべてのユーザーの Lync クライアント エクスペリエンスを選択します。
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

次のコマンドは、Redmond サイト内のすべてのユーザーに対してクライアント エクスペリエンスのビジネス用の Skype を選択します。
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

組織内の特定のユーザーに対してクライアント エクスペリエンスを構成する場合は、**新規 CsClientPolicy**コマンドレットを使用して、新しいユーザー ポリシーを作成して特定のユーザーに**与える CsClientPolicy**を使用してポリシーを割り当てるコマンドレットです。
  
たとえば、次のコマンドでは、新しいクライアント ポリシーでは、クライアント エクスペリエンスのビジネス用の Skype を選択するには、SalesClientUI が作成されます。
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

次のコマンドを実行すると、Sales 部門のすべてのメンバーにポリシー SalesClientUI が割り当てられます。
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>最初の起動クライアントの動作

既定では、ユーザーが最初に、ビジネス 2015年の Skype を起動するときに常に表示されます、Skype のビジネス ユーザー ・ インタ フェース - 示すように、EnableSkypeUI パラメーターの値を $False に設定して Lync クライアント エクスペリエンスを選択した場合でも先に。 起動から数分後に、Lync モードに切り替えるかどうかを確認するメッセージが表示されます。
  
ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。
  
1. 確認の値`EnableSkypeUI`は前述のように使用しているポリシーで $False に設定します。
    
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

ユーザーは、ビジネス クライアント用の Skype を開き、既定の動作は*7 つのクイック ヒントのほとんどの人に依頼*を含む [ようこそ] 画面を表示するのには。 You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:
  
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

組織ビジネス サーバーの両方の Skype には、Lync Server の展開、クライアントの経験によって異なる場合がサーバーのバージョンと、Skype の UI 設定。 以下の表に、サーバー バージョンと UI 設定に基づく最初のクライアント エクスペリエンスを示します。
  

|**サーバー バージョン**|**EnableSkypeUI 設定**|**クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Server |既定  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |Lync モードに切り替えるには、ユーザーが求められます (ユーザーは、$true に、UI の設定を変更する場合に後で、ビジネスの Skype に切り替えることができます)  <br/> |
|Lync Server 2010 または (修正) の Lync Server 2013  <br/> |既定  <br/> |Lync モードに切り替えるには、ユーザーが求められます (ユーザーは、$true に、UI の設定を変更する場合に後で、ビジネスの Skype に切り替えることができます)  <br/> |
|Lync Server 2010 または (修正) の Lync Server 2013  <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または (修正) の Lync Server 2013  <br/> |False  <br/> |Lync モードに切り替えるには、ユーザーが求められます (ユーザーは、$true に、UI の設定を変更する場合に後で、ビジネスの Skype に切り替えることができます)  <br/> |
|Lync Server 2010 または (パッチ) せずに Lync Server 2013  <br/> |既定  <br/> |Lync モードに切り替えるには、ユーザーが求められます (ユーザーが後で、ビジネスの Skype に切り替えることはできません)  <br/> |
   
次の表は、管理者には、Skype の UI の操作性の初期設定が変更されたときにクライアント エクスペリエンスを示しています。
  

|**サーバー バージョン**|**EnableSkypeUI 設定**|**クライアント UI Lync を =**|**クライアント UI = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |ユーザーが、ビジネスの Skype への切り替えしようとしています。  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Lync モード  <br/> |ユーザーが、Lync のモードに切り替えるしようとしています。  <br/> |
|Lync Server 2010 または (修正) の Lync Server 2013  <br/> |True  <br/> |ユーザーが、ビジネスの Skype への切り替えしようとしています。  <br/> |Skype for Business  <br/> |
|Lync Server 2010 または (修正) の Lync Server 2013  <br/> |False  <br/> |Lync モード  <br/> |ユーザーが、Lync のモードに切り替えるしようとしています。  <br/> |
|Lync Server 2010 または (パッチ) せずに Lync Server 2013  <br/> |既定  <br/> |Lync のモード (ビジネス用の Skype に切り替えることはできません)  <br/> |Lync のモード (ビジネス用の Skype に切り替えることはできません)  <br/> |
   
ビジネス クライアント用の Skype の設定を管理するために必要な修正プログラムのバージョンは次のとおりです。
  
- Lync Server 2010 から Lync Server 2010 の累積的な更新 (4.0.7577.710) 年 2015年 2 月ことができます。 については、 [Lync Server 2010 用の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532771)を参照してください。
    
- Lync Server 2013 の Lync Server 2013 年 2014年 12 月累積的な更新 (5.0.8308.857) ことができます。 については、 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532772)を参照してください。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>ドメインに参加しているコンピューターのレジストリを変更するグループ ポリシー オブジェクトを作成する

Lync クライアント エクスペリエンスの最初の起動時、ユーザー ビジネス 2015年クライアントの Skype を表示するレジストリの更新は 1 回だけ行う必要があります。 グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。 
  
次の手順では、Lync クライアント エクスペリエンスの最初の起動時、ユーザー ビジネス 2015年クライアントの Skype が表示されるようにレジストリを変更する方法について説明します。 この手順は、レジストリを更新して前述のようこそ画面のチュートリアルを無効にするためにも使用できます。
  
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
  

