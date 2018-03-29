---
title: Skype for Business Server 2015 での CLS ログ キャプチャの開始または終了
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '概要: 開始またはビジネス サーバー 2015 の Skype のログ サービスの一元的なログのキャプチャ セッションを停止する方法を説明します。'
ms.openlocfilehash: 81db8c521f96306e118ebe5fe8053ff6e849dd54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での CLS ログ キャプチャの開始または終了
 
**の概要:**開始またはビジネス サーバー 2015 の Skype のログ サービスの一元的なログのキャプチャ セッションを停止する方法について説明します。
  
集中ログ サービスを使用してトレース ログをキャプチャするには、コンピューターとプールの 1 つまたは複数のログを記録するコマンドを発行します。 どのコンピューターまたはプールを AlwaysOn、別の事前定義されたシナリオでは、やなどを作成した場合)、実行するには、どのようなシナリオを定義するパラメーターも発行するビジネス サーバー コンポーネント (たとえば、S4、SipStack) をトレースするのには、どのような Skype。
  
適切な情報をキャプチャするには、問題に関連する情報を収集するために右のシナリオを使用するかどうかを確認する必要があります。 集中ログ サービスのシナリオは、ログの有効化サーバー コンポーネント、ログ レベル、およびフラグのコレクションに基づく効率的で、サーバーごとにこれらの要素を定義することよりも便利であるという概念です。 定義および実行するシナリオを指定してすべてのサーバーとインフラストラクチャの範囲内のプールの間で一貫性のあるシナリオを実行します。
  
既定のシナリオは、**AlwaysOn** です。AlwaysOn のねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。
  
集中ログ サービスでは、コマンドを実行する 2 つの方法を提供します。 トピックの数がされてにフォーカスしたビジネス サーバー管理シェルには、Skype で Windows PowerShell を使用しています。 多数の複雑な構成とコマンドを使用することは、ログ サービスの集中管理用の Windows PowerShell を優先します。 ビジネス サーバー管理シェルの Skype を介して Windows PowerShell が Skype ビジネス サーバー用のすべての関数の普及のため、Windows PowerShell コマンドのみを説明します。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>基本的なコマンドを使用して Windows PowerShell を開始 CsClsLogging を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 集中ログ サービスで、次を入力してログのシナリオを開始します。
    
  ```
  Start-CsClsLogging -Scenario <name of scenario>
  ```

    たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。
    
  ```
  Start-CsClsLogging -Scenario AlwaysOn
  ```

    > [!NOTE]
    > AlwaysOn シナリオには、既定の実行期間がありません。 **Stop CsClsLogging**コマンドレットを明示的に停止されるまで、このシナリオが実行されます。 詳細については、 [Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)を参照してください。 その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。 
  
3. Enter キーを押して、コマンドを実行します。 
    
    > [!NOTE]
    > このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。 
  
     ![Start-CsClsLogging の実行](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 別のシナリオを開始するには、追加シナリオの名前の**開始 CsClsLogging**コマンドレットを使用して、(たとえば、シナリオ**の認証**) を次のように実行します。
    
  ```
  Start-CsClsLogging -Scenario Authentication
  ```

    > [!IMPORTANT]
    > それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>高度なコマンドを使用して Windows PowerShell を開始 CsClsLogging を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 追加のパラメーターを使用して、このログ記録コマンドを管理できます。 -を使用することができますを実行するシナリオでは、時間の長さを調整する期間です。 定義することも、コンピューター、コンピューターの完全修飾ドメイン名 (Fqdn)、コンマで区切られたリストまたは、プールでは、コンマ区切りのログオンを実行するプールの Fqdn の一覧です。
    
    プール"pool01.contoso.net"の UserReplicator のシナリオでログ セッションを開始するとします。 また、このログ セッションの期間を 8 時間に指定します。 この場合、次のように入力します。
    
  ```
  Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"

  ```

    このシナリオが正常に実行されると、次のような結果が返されます。
    
     ![Start-CsClsLogging の実行](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>集中ログ サービスのログ キャプチャを終了する
<a name="stop"> </a>

現在実行中のセッションを停止 CsClsLogging コマンドレットを使用してログオンを停止することができます。 一般に、さまざまな状況のログ セッションを停止する必要がありません。 たとえば、ログを検索し、最初にログ記録を停止する必要のない構成を変更できます。 実行する開始する前に (、グローバル、サイト、プール、またはコンピューターのスコープで) その他のシナリオのいずれかの場合は 2 つのシナリオを実行している、AlwaysOn と UserReplicator などがある場合、認証に関連する情報を収集する必要がありを停止する必要があります。認証のシナリオです。 詳細については、 [Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)を参照してください。
  
> [!NOTE]
> 特定の展開、プール、またはコンピューターで実行することがどのようなシナリオを決定するときは、**コンピューターごと**に実行されている 2 つのシナリオに限定されることに注意してくださいする必要があります: AlwaysOn と 1 つのカスタム シナリオです。 プール上でのアクティビティ ログに記録する場合は、単一のエンティティとして、プールを扱う必要があります。 ほとんどの場合、そのことをプール内の各コンピューター上のさまざまなシナリオを実行します。 させることに関するデータを収集しているし、どのようなシナリオでは、展開全体で特定のコンピューターで最も有用なを考えている問題を確認します。 などの UserReplicator のシナリオを検討する場合は非常に小さな値にありますエッジ サーバーまたはエッジ プールの UserReplicator を実行しています。 
  
問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行していないかのような) データが得られる可能性があります。
  
ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの集中管理機能を制御するには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーをする必要があります。これら 2 つのグループのいずれかが含まれています。 (自分で作成したカスタムの RBAC の役割を含む) には、このコマンドレットが割り当てられているすべての RBAC の役割の一覧を返すするには、ビジネスのサーバー管理シェルまたは Windows PowerShell プロンプトに、Skype から次のコマンドを実行します。
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>現在実行中のログ サービスの一元的なセッションを停止するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 集中ログ サービスがどのようなシナリオは、現在実行されている、次を入力して、検索するクエリを実行します。
    
  ```
  Show-CsClsLogging
  ```

  ![Show-CsCl 呼び出し後の Windows PowerShell コンソール](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
  Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。 詳細については、[表示する CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)を参照してください。
    
3. 特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。
    
  ```
  Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
  ```
  次に例を示します。
    
  ```
  Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
  ```

  このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。
    
    > [!NOTE]
    > UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。 このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。 詳細については、[検索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)を参照してください。 
  
Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="stop"> </a>

#### 

[ビジネス 2015年の Skype での一元的なログ記録サービス](centralized-logging-service.md)

