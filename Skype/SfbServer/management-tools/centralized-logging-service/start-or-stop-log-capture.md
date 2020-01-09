---
title: Skype for Business Server 2015 での CLS ログ キャプチャの開始または終了
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '概要: Skype for Business Server 2015 で一元管理されたログサービスログキャプチャセッションを開始または停止する方法について説明します。'
ms.openlocfilehash: b4da74e05a1eb6f6945f44c0c045c2292e7acca7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991442"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での CLS ログ キャプチャの開始または終了
 
**概要:** Skype for Business Server 2015 で中央のログサービスログキャプチャセッションを開始または停止する方法について説明します。
  
一元ログサービスを使ってトレースログをキャプチャするには、1つ以上のコンピューターとプールでログの記録を開始するコマンドを実行します。 また、どのコンピューターまたはプール、実行するシナリオ (AlwaysOn、別の定義済みシナリオ、作成したシナリオ)、どの Skype for Business Server コンポーネント (たとえば、S4、SipStack) を追跡するかを定義するパラメーターを発行します。
  
適切な情報を取得するには、適切なシナリオを使用して、問題に関連する情報を収集していることを確認する必要があります。 一元化されたログサービスでは、サーバーコンポーネント、ログレベル、フラグなどのコレクションに基づいてログ記録を有効にするという概念があります。これは、サーバーごとにこれらの要素を定義するよりも効率的で便利です。 実行するシナリオを定義して指定すると、インフラストラクチャの範囲内のすべてのサーバーとプールでシナリオが一貫して実行されます。
  
既定のシナリオは、**AlwaysOn** です。AlwaysOn のねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。
  
中央集中ログサービスでは、2つの方法でコマンドを発行できます。 Skype for Business Server 管理シェルでの Windows PowerShell の使用に重点を置いているいくつかのトピックが正方形されました。 多数の複雑な構成とコマンドを使う機能は、Windows PowerShell を使用して一元的なログサービスを使うことができます。 Skype for business Server の管理シェルである Windows PowerShell は、Skype for Business Server のすべての機能に対して最も広く普及しているため、Windows PowerShell コマンドのみについて説明します。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>基本的なコマンドを使用して Windows PowerShell で CsClsLogging を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のように入力して、集中化されたログサービスでログシナリオを開始します。
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > AlwaysOn シナリオには、既定の実行期間がありません。 このシナリオの実行は、**Stop-CsClsLogging** コマンドレットによって明示的に停止するまで続きます。 詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。 その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。 
  
3. Enter キーを押して、コマンドを実行します。 
    
    > [!NOTE]
    > このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。 
  
     ![Start-CsClsLogging の実行](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>詳細なコマンドを使用して、Windows PowerShell での Start CsClsLogging を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 追加のパラメーターを使用して、このログ記録コマンドを管理できます。 -Duration を使用して、シナリオを実行する時間の長さを調整することができます。 また、コンピューターの定義を行うこともできます。これには、コンピューターの完全修飾ドメイン名 (Fqdn) をコンマ (,) で区切った一覧と、ログに記録するプールの Fqdn のコンマ区切りリストを指定します。
    
    UserReplicator というシナリオによるログ セッションをプール “pool01.contoso.net” で開始するとします。 また、このログ セッションの期間を 8 時間に指定します。 この場合、次のように入力します。
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    このシナリオが正常に実行されると、次のような結果が返されます。
    
     ![Start-CsClsLogging の実行](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>集中ログ サービスのログ キャプチャを終了する
<a name="stop"> </a>

Stop-CsClsLogging コマンドレットを使用して、現在実行されているログセッションを停止することができます。 一般的に、ログセッションを停止する必要がある状況はあまり多くありません。 たとえば、ログを検索して構成を変更するには、まずログの記録を停止する必要があります。 AlwaysOn と UserReplicator などの2つのシナリオが実行されていて、認証に関連する情報を収集する必要がある場合は、次のいずれかのシナリオ (グローバル、サイト、プール、またはコンピューターのスコープ) を停止してから実行を開始する必要があります。認証シナリオ。 詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。
  
> [!NOTE]
> 特定の展開、プール、またはコンピューターで実行できるシナリオを決定する際には、**コンピューターごと**に2つのシナリオ (AlwaysOn と1つのカスタムシナリオ) の実行に制限されていることを覚えておく必要があります。 プールにアクティビティを記録する場合は、プールを単一のエンティティとして扱う必要があります。 ほとんどの場合、プール内の各コンピューターで異なるシナリオを実行することは意味がありません。 データを収集している問題を確認し、全体的な展開で特定のコンピューターで最も意味のあるシナリオについて考えてみてください。 たとえば、UserReplicator シナリオを検討している場合は、Edge サーバーまたはエッジプールで UserReplicator を実行するだけでは、あまり意味がありません。 
  
問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行していないかのような) データが得られる可能性があります。
  
Skype for Business Server 管理シェルを使用して中央集中ログサービス機能を制御するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループ、またはカスタム RBAC ロールのいずれかのメンバーである必要があります。この2つのグループのいずれかが含まれます。 このコマンドレットが割り当てられているすべての RBAC ロールの一覧 (自分自身で作成したカスタム RBAC ロールを含む) を返すには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> ログを有効にしたのに、ログはどこに保存されているのか不思議に思われるかもしれません。 ログに保存されている情報には、CLS エージェントに送信された管理シェルクエリを使ってアクセスするため、さまざまなファイル形式で結果を出力することができます。これにより、各サーバー上でそのレコードが実際には重要ではないことがわかります。  ログファイルは、 **Snooper**や、 **notepad.exe**などのテキストファイルを読み取ることができるツールなど、さまざまなツールを使用して、指定した場所に保存することができます。 Snooper は、Skype for Business Server 2015 デバッグツールの一部であり、 [Web ダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=285257)として利用できます。

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>現在実行中の中央記録サービスセッションを停止するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次を入力して、現在実行されているシナリオを確認します。
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Show-CsCl 呼び出し後の Windows PowerShell コンソール](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。詳細については、「[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)」を参照してください。
    
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
    > UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。詳細については、「[Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)」を参照してください。 
  
Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。
## <a name="see-also"></a>関連項目
<a name="stop"> </a>

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)
