---
title: 集中ログ サービス プロバイダーの構成
TOCTitle: 集中ログ サービス プロバイダーの構成
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49886987
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集中ログ サービス プロバイダーの構成

 

_**トピックの最終更新日:** 2014-03-19_

集中ログ サービス におけるプロバイダーの概念と構成は、理解しておく必要がある最も重要な事柄の 1 つです。プロバイダーは、Lync Server トレース モデル内で Lync Server サーバーの役割をするコンポーネントに直接マップされます。プロバイダーは、トレースされる Lync Server 2013 のコンポーネント、収集するメッセージの種類 (重大、エラー、警告など)、およびフラグ (TF\_Connection、TF\_Diag など) を定義します。プロバイダーは、各 Lync Server サーバーの役割内のトレース可能なコンポーネントです。プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。

Lync Server 管理シェルを使用して 集中ログ サービス の機能を実行するには、役割ベースのアクセス制御 (RBAC) セキュリティ グループである CsAdministrator または CsServerAdministrator のどちらかのメンバーであるか、この 2 つのグループのどちらかを含むカスタム RBAC 役割のメンバーである必要があります。このコマンドレットが割り当てられている役割ベースのアクセス制御 (RBAC) 役割のリストを、自分で作成したカスタム RBAC も含めて戻すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

このトピックの以下の部分では、プロバイダーの定義方法、プロバイダーの変更方法、およびトラブルシューティングを最適化するためにプロバイダー定義に含まれるものに注目します。集中ログ サービス のコマンドを発行する方法は 2 つあります。既定で C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent ディレクトリに配置される CLSController.exe を使用できます。または、Lync Server 管理シェルを使用して、Windows PowerShell コマンドを発行できます。この 2 つの方法の重要な相違点は、CLSController.exe をコマンド ラインで使用する場合は、使用できるシナリオに限りがあり (プロバイダーが既に定義されたシナリオから選択)、プロバイダーを変更することはできませんが、ログ レベルは定義できます。Windows PowerShell を使用すると、ログ セッションで使用する新しいプロバイダーを定義でき、プロバイダーの作成、プロバイダーの収集対象、およびプロバイダーのデータ収集レベルを完全に制御できます。


> [!IMPORTANT]
> 前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。<BR>集中ログ サービス には定義済みのシナリオが多数用意されているため、プロバイダーの詳細を知る必要はありません。用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。まれに、プロバイダーを定義してシナリオに割り当てなければならない場合があります。新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されているシナリオを十分に調べることを強くお勧めします。ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。



「[集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)」で紹介されているように、シナリオで使用するプロバイダーの定義における重要な要素を次に示します。

  - **プロバイダー:** OCSLogger を熟知している場合、プロバイダーは、トレース エンジンによるログの収集対象を OCSLogger に通知するために選択するコンポーネントです。プロバイダーは OCSLogger のコンポーネントと同じコンポーネントであり、ほとんどの場合、同じ名前を持ちます。OCSLogger に慣れていない場合、プロバイダーはサーバーの役割固有のコンポーネントであり、集中ログ サービス はここからログを収集できます。集中ログ サービス の場合、CLSAgent は 集中ログ サービス のアーキテクチャの一部であり、プロバイダー構成に定義されたコンポーネントのトレースが実行されます。

  - **ログ レベル:** OCSLogger では、収集するデータの詳細レベルを選択できます。この機能は 集中ログ サービス とシナリオの不可欠な部分であり、**Type** パラメーターによって定義されます。次の中から選択できます。
    
      - **All:** 種類が重大、エラー、警告、および情報であるトレース メッセージを定義済みのプロバイダー用のログに収集します。
    
      - **Fatal:** 定義済みのプロバイダー用の障害を示すトレース メッセージのみ収集します。
    
      - **Error:** 定義済みのプロバイダー用のエラーに加え、重大なメッセージを示すトレース メッセージのみ収集します。
    
      - **Warning**定義済みのプロバイダー用の警告に加え、重大なメッセージとエラー メッセージを示すトレース メッセージのみ収集します。
    
      - **Info:** 定義済みのプロバイダー用の情報メッセージに加え、重大、エラー、および警告メッセージを示すトレース メッセージのみ収集します。
    
      - **Verbose:** 定義済みのプロバイダー用の種類が重大、エラー、警告、および情報であるすべてのトレース メッセージを収集します。

  - **フラグ:** OCSLogger では、トレース ファイルから取得できる情報の種類を定義する各プロバイダー用のフラグを選択できます。プロバイダーに基づいて、次のフラグを選択できます。
    
      - **TF\_Connection:** 接続に関連するログ エントリを提供します。これらのログには、特定のコンポーネントに対して確立された接続に関する情報が含まれます。さらに、ネットワーク レベルの重要な情報 (接続の概念を持たないコンポーネント用の情報) が含まれる場合があります。
    
      - **TF\_Security:** セキュリティに関連するすべてのイベント/ログ エントリを提供します。たとえば、SipStack の場合は、ドメイン検証エラー、クライアント認証/承認エラーなどのセキュリティ イベントです。
    
      - **TF\_Diag:** コンポーネントを診断またはトラブルシューティングするために使用できる診断イベントを提供します。たとえば、SipStack の場合は、証明書エラー、DNS 警告/エラーなどです。
    
      - **TF\_Protocol:** SIP メッセージ、CCCP メッセージなどのプロトコル メッセージを提供します。
    
      - **TF\_Component:** プロバイダーの一部として指定されたコンポーネントでのログ記録を有効にします。
    
      - **All:** プロバイダーで使用できるすべてのフラグを設定します。

## 既存の 集中ログ サービス シナリオのプロバイダーに関する情報をレビューするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  既存のプロバイダーの構成をレビューするには、次を入力します。
    
        Get-CsClsScenario -Identity <scope and scenario name>
    
    たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。
    
        Get-CsClsScenario -Identity "global/CAA"
    
    このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。表示される情報が不足している、または既定の Windows PowerShell リスト形式で表示するには一覧が長すぎる場合は、別の出力方法を定義することで追加情報を表示できます。これを行うには、次のように入力します。
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。

## 新しい 集中ログ サービス シナリオ プロバイダーを表示するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これは実行するには次のように入力します。
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level では、重大、エラー、警告、および情報メッセージが収集されます。使用されるフラグは、Lyss プロバイダー用に定義されたすべてのフラグであり、TF\_Connection、TF\_Diag、および TF\_Protocol を含みます。

変数 $LyssProvider を定義した後、**New-CsClsScenario** コマンドレットでその変数を使用して Lyss プロバイダーからトレースを収集できます。このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。

## 既存の 集中ログ サービス シナリオ プロバイダーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  既存のプロバイダーの構成を更新または変更するには、次のように入力します。
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    次のように入力することで、プロバイダーを割り当てるシナリオを更新します。
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

コマンドを実行すると、最終的にシナリオ site:Redmond/RedmondLyssInfo のフラグと割り当てられるプロバイダーのレベルが更新されます。Get-CsClsScenario を使用して、新しいシナリオを表示できます。詳細については、「[Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario)」を参照してください。


> [!WARNING]
> <STRONG>New-ClsCsProvider</STRONG> は、フラグが有効かどうかを確認しません。フラグのスペル (TF_DIAG、TF_CONNECTION など) が正しいことを確認してください。フラグのスペルが正しくない場合、プロバイダーは期待されるログ情報を返すことができません。



このシナリオに対してプロバイダーを追加するには、次のように入力します。

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Add ディレクティブで定義される各プロバイダーは、**New-CsClsProvider** プロセスで既に定義されています。

## シナリオ プロバイダーを削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。たとえば、プロバイダー LyssProvider では、ログの種類として WPP、レベルとして Debug、およびフラグとして TF\_CONNECTION と TF\_DIAG が定義されています。このフラグを "All" に変更する必要があるとします。このプロバイダーを変更するには、次のように入力します。
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

       &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  シナリオとそれに関連付けられているプロバイダーを完全に削除するには、次のように入力します。
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    次に例を示します。
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    

    > [!WARNING]
    > <STRONG>Remove-CsClsScenario</STRONG> コマンドレットは、確認のプロンプトを表示しません。シナリオは、それに関連付けられているプロバイダーと共に削除されます。シナリオを初めて作成したときに使用したコマンドを再実行することで、シナリオを再作成できます。削除したシナリオまたはプロバイダーを回復するための手順はありません。



**Remove-CsClsScenario** コマンドレットを使用してシナリオを削除すると、シナリオはスコープから完全に削除されます。作成したシナリオとシナリオの一部であったプロバイダーを使用するには、新しいプロバイダーを作成し、それらを新しいシナリオに割り当てます。

## 関連項目

#### その他のリソース

[Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider)

