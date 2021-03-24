---
title: Skype for Business Server 2015 で CLS ログ キャプチャを開始または停止する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '概要: Skype for Business Server 2015 で集中ログ サービス ログ キャプチャ セッションを開始または停止する方法について学習します。'
ms.openlocfilehash: 773b93f62690b01d33f84bc5eb68b135280842ea
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098823"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で CLS ログ キャプチャを開始または停止する
 
**概要:** Skype for Business Server 2015 で集中ログ サービス ログ キャプチャ セッションを開始または停止する方法について学習します。
  
集中ログ サービスを使用してトレース ログをキャプチャするには、1 つ以上のコンピューターとプールでのログ記録を開始するコマンドを発行します。 また、実行するコンピューターまたはプール、実行するシナリオ (AlwaysOn、別の定義済みシナリオ、作成したシナリオなど)、トレースする Skype for Business Server コンポーネント (S4、SipStack など) を定義するパラメーターも発行します。
  
適切な情報を取得するには、適切なシナリオを使用して問題に関連する情報を収集する必要があります。 集中ログ サービスのシナリオでは、サーバー コンポーネント、ログ レベル、フラグのコレクションに基づいてログをオンにするという概念が考え方であり、サーバー単位でこれらの要素を定義するよりもはるかに効率的で便利です。 実行するシナリオを定義して指定すると、シナリオはインフラストラクチャのスコープ内のすべてのサーバーとプールで一貫して実行されます。
  
既定のシナリオは、**AlwaysOn** です。AlwaysOn シナリオのねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。
  
集中ログ サービスには、コマンドを発行する 2 つの方法があります。 多くのトピックでは、Skype for Business Server 管理シェルWindows PowerShellを使用する方法に重点を置いて取り上がっています。 多数の複雑な構成とコマンドを使用する機能は、集中ログ サービスWindows PowerShellの使用をサポートします。 Skype for Business Server 管理Windows PowerShellを使用する方法は、Skype for Business Server のすべての機能でほぼユビキタスなので、Windows PowerShell コマンドについてのみ説明します。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>基本コマンドをStart-CsClsLoggingしてWindows PowerShellを実行するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 次のように入力して、集中ログ サービスを使用してログシナリオを開始します。
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > AlwaysOn シナリオには、既定の実行期間がありません。 このシナリオの実行は、**Stop-CsClsLogging** コマンドレットによって明示的に停止されるまで続きます。 詳細については、「[Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。 その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。 
  
3. Enter キーを押して、コマンドを実行します。 
    
    > [!NOTE]
    > このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。 
  
     ![Start-CsClsLogging の実行。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。 コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。 3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。 グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>高度なコマンドをStart-CsClsLoggingしてWindows PowerShellを実行するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 追加のパラメーターを使用して、このログ記録コマンドを管理できます。 -Duration を使用すると、シナリオを実行する時間の長さを調整できます。 また、-Computer、コンマで区切られたコンピューター完全修飾ドメイン名 (FQDN) の一覧、またはログオンを実行するプールの FQDN のコンマ区切りリストである -Pools を定義することもできます。
    
    プール "サーバー" で UserReplicator シナリオのログ セッションを開始 pool01.contoso.net。 また、このログ セッションの期間を 8 時間に指定します。 この場合、次のように入力します。
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    このシナリオが正常に実行されると、次のような結果が返されます。
    
     ![Start-CsClsLogging の実行。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>集中ログ サービスのログ キャプチャを停止する
<a name="stop"> </a>

現在実行中のログ セッションは、Stop-CsClsLoggingできます。 一般に、ログ セッションを停止する必要がある状況はそれほど多くはない。 たとえば、ログを検索したり、構成を変更したりすると、最初にログを停止する必要が生じることなく実行できます。 AlwaysOn や UserReplicator など、2 つのシナリオが実行されている場合、認証に関連する情報を収集する必要がある場合は、認証シナリオの実行を開始する前に、他のシナリオ (グローバル、サイト、プール、またはコンピューター スコープ) のいずれかを停止する必要があります。 詳細については、「[Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。
  
> [!NOTE]
> 特定の展開、プール、またはコンピューターで実行できるシナリオを決定する場合は、AlwaysOn と 1 つのカスタムシナリオの 2 つのシナリオを実行する場合に限られていることを覚えておく必要があります。 プールでアクティビティをログに記録する場合は、プールを 1 つのエンティティとして扱う必要があります。 ほとんどの場合、プール内の各コンピューターで異なるシナリオを実行しても意味がありません。 データを収集している問題を見て、展開全体で特定のコンピューターで最も意味のあるシナリオを考えるのは理にかなっています。 たとえば、UserReplicator シナリオを考える場合、エッジ サーバーまたはエッジ プールで UserReplicator を実行する場合の値は非常に少ない可能性があります。 
  
問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行してないかのような) データが得られる可能性があります。
  
Skype for Business Server 管理シェルを使用して集中ログ サービス機能を制御するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループ、またはこれら 2 つのグループのいずれかを含むカスタム RBAC 役割のメンバーである必要があります。 このコマンドレットが割り当てられているすべての RBAC 役割 (自分で作成したカスタム RBAC の役割を含む) の一覧を取得するには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> では、ログ記録が有効になっているので、ログはどこに保存されますか? CLS エージェントに送信される管理シェル クエリを使用してログに格納されている情報にアクセスし、結果をいくつかの可能なファイル形式に出力できます。各サーバーでは、CLS エージェントがレコードを保持することが実際には重要ではありません。  ログ ファイルは **、Snooper.exe** やNotepad.exeなどのテキスト ファイルを読み取るツールなど、さまざまなツールを使用して、指定および読み取りおよび分析する場所 **に保存できます**。 Snooper.exe Skype for Business Server 2015 デバッグ ツールの一部であり、Web ダウンロードとして [利用できます](https://go.microsoft.com/fwlink/p/?LinkId=285257)。

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>現在実行中の集中ログ サービス セッションを停止するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 集中ログ サービスにクエリを実行して、現在実行されているシナリオを確認するには、次のように入力します。
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell呼び出し後のコンソールShow-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。 詳細については、「[Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps)」を参照してください。
    
3. 特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   次に例を示します。
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。
    
    > [!NOTE]
    > UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。 このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。 詳細については、「[Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps)」を参照してください。 
  
Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。
## <a name="see-also"></a>関連項目
<a name="stop"> </a>

[Skype for Business 2015 の集中ログ サービス](centralized-logging-service.md)