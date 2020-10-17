---
title: 'Lync Server 2013: 集中ログサービス用のプロバイダーの構成'
description: 'Lync Server 2013: 集中ログサービス用のプロバイダーの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146865b3856f7956c6ae393ef38614b0fea168e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547953"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 での集中ログサービスのプロバイダーの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-03-19_

集中ログサービスの *プロバイダー* の概念と構成は、把握しておくべき最も重要なものの1つです。 *プロバイダー*は、lync server トレースモデルの lync server サーバーロールコンポーネントに直接マップされます。 プロバイダーは、追跡される Lync Server 2013 のコンポーネント、収集するメッセージの種類 (致命的、エラー、警告など)、およびフラグ (たとえば、TF \_ Connection または tf Diag) を定義し \_ ます。 プロバイダーは、各 Lync Server サーバーの役割で追跡可能なコンポーネントです。 プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。 定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。

Lync Server 管理シェルを使用して集中ログサービスの機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかを含むカスタムの RBAC の役割を持っている必要があります。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自分で作成したカスタムの RBAC の役割を含む) を戻すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

このトピックの以下の部分では、プロバイダーの定義方法、プロバイダーの変更方法、およびトラブルシューティングを最適化するためにプロバイダー定義に含まれるものに注目します。 集中ログサービスのコマンドを発行するには、2つの方法があります。 既定では、ディレクトリ C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 clsagent にある CLSController.exe を使用でき \\ ます。 または、Lync Server 管理シェルを使用して、Windows PowerShell コマンドを発行することもできます。 この 2 つの方法の重要な相違点は、CLSController.exe をコマンド ラインで使用する場合は、使用できるシナリオに限りがあり (プロバイダーが既に定義されたシナリオから選択)、プロバイダーを変更することはできませんが、ログ レベルは定義できます。 Windows PowerShell を使用すると、ログセッションで使用するために新しいプロバイダーを定義し、作成、収集内容、データを収集するレベルなどを詳細に制御できます。

<div class="">


> [!IMPORTANT]  
> 前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。<BR>プロバイダーの詳細を深く掘り下げて把握する必要はありませんが、集中ログサービスでは、既に定義されているいくつかのシナリオが用意されています。 用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。 まれに、プロバイダーを定義してシナリオに割り当てなければならない場合があります。 新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されているシナリオを十分に調べることを強くお勧めします。 ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。



</div>

[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)では、シナリオで使用するプロバイダーを定義する主な要素として、次の要素を紹介しています。

  - **Providers**    OCSLogger を熟知している場合、プロバイダーは、トレースエンジンがログを収集する内容を OCSLogger に通知するために選択するコンポーネントです。 プロバイダーは同じコンポーネントで、多くの場合、OCSLogger のコンポーネントと同じ名前になります。 OCSLogger を使い慣れていない場合、プロバイダーは、集中ログサービスがログを収集できる、サーバーロール固有のコンポーネントです。 集中ログサービスの場合、CLSAgent は、プロバイダ構成で定義したコンポーネントのトレースを実行している、集中ログサービスのアーキテクチャ部分です。

  - **ログ出力レベル**    OCSLogger では、収集されるデータの詳細レベルの数を選択するオプションが提供されています。 この機能は、集中ログサービスとシナリオの重要な部分であり、 **Type** パラメーターで定義されています。 次のいずれかを選択できます。
    
      - **すべて**    指定されたプロバイダーについて、重大、エラー、警告、および情報の種類のトレースメッセージをログに収集します。
    
      - **致命的**     な定義済みのプロバイダーのエラーを示すトレースメッセージのみを収集します。
    
      - **エラー**    定義済みのプロバイダーのエラー、および致命的なメッセージを示すトレースメッセージのみを収集します。
    
      - **警告**    定義済みのプロバイダーについての警告、および致命的メッセージとエラーメッセージを示すトレースメッセージのみを収集します。
    
      - **情報**    定義済みのプロバイダーの情報メッセージに加え、致命的、エラー、および警告メッセージを示すトレースメッセージのみを収集します。
    
      - **詳細**    定義済みのプロバイダーについて、種類が fatal、error、warning、info のすべてのトレースメッセージを収集します。

  - **Flags**    OCSLogger では、トレースファイルから取得できる情報の種類を定義するプロバイダーごとにフラグを選択するオプションが用意されています。 プロバイダーに基づいて、次のフラグを選択できます。
    
      - **TF \_接続**     接続に関連するログエントリを提供します。 これらのログには、特定のコンポーネントとの間で確立された接続に関する情報が含まれます。 これには、ネットワークレベルの重要な情報 (接続の概念を持たないコンポーネント) が含まれることもあります。
    
      - **TF \_セキュリティ**     セキュリティに関連するすべてのイベント/ログエントリを提供します。 たとえば、SipStack の場合、これらはドメイン検証エラーなどのセキュリティイベント、およびクライアント認証/承認エラーです。
    
      - **TF \_Diag**     は、コンポーネントの診断またはトラブルシューティングに使用できる診断イベントを提供します。 たとえば、SipStack の場合は、証明書が失敗したか、DNS の警告/エラーが発生します。
    
      - **TF \_Protocol**     SIP、組み合わせたコミュニティコーデックパックメッセージなどのプロトコルメッセージを提供します。
    
      - **TF \_コンポーネント**     は、プロバイダーの一部として指定されたコンポーネントのログ記録を有効にします。
    
      - **すべて**    プロバイダーで使用可能なすべての使用可能なフラグを設定します。

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>既存の集中ログサービスシナリオプロバイダーに関する情報を確認するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  既存のプロバイダーの構成をレビューするには、次を入力します。
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。
    
        Get-CsClsScenario -Identity "global/CAA"
    
    このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。 表示されている情報が不足している場合や、既定の Windows PowerShell リスト形式でリストが長すぎる場合は、別の出力メソッドを定義することで追加情報を表示できます。 これを行うには、次のように入力します。
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>新しい集中ログサービスシナリオプロバイダーを定義するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これは実行するには次のように入力します。
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level は、重大、エラー、警告、および情報メッセージを収集します。 使用されるフラグは、一からの Ss プロバイダーに対して定義されているもので、TF \_ Connection、tf \_ DIAG、tf プロトコルが含まれてい \_ ます。

変数 $LyssProvider を定義した後、**New-CsClsScenario** コマンドレットでその変数を使用して Lyss プロバイダーからトレースを収集できます。 このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>既存の集中ログサービスシナリオプロバイダーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  既存のプロバイダーの構成を更新または変更するには、次のように入力します。
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    次のように入力することで、プロバイダーを割り当てるシナリオを更新します。
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

コマンドを実行すると、最終的にシナリオ site:Redmond/RedmondLyssInfo のフラグと割り当てられるプロバイダーのレベルが更新されます。 Get-CsClsScenario を使用して、新しいシナリオを表示できます。 詳細については、「[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)」を参照してください。

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> は、フラグが有効かどうかを確認しません。 フラグのスペル (TF_DIAG や TF_CONNECTION など) が正しいことを確認してください。 フラグのスペルが正しくない場合、プロバイダーは期待されるログ情報を返すことができません。



</div>

このシナリオに対してプロバイダーを追加するには、次のように入力します。

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Add ディレクティブで定義される各プロバイダーは、**New-CsClsProvider** プロセスで既に定義されています。

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>シナリオ プロバイダーを削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。 プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。 プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。 たとえば、プロバイダー LyssProvider は、ログの種類、デバッグのレベルセット、flags セットが TF CONNECTION および TF DIAG として、WPP で定義されてい \_ \_ ます。 このフラグを "All" に変更する必要があるとします。 このプロバイダーを変更するには、次のように入力します。
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  シナリオとそれに関連付けられているプロバイダーを完全に削除するには、次のように入力します。
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    次に例を示します。
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <STRONG>Remove-CsClsScenario</STRONG> コマンドレットは、確認のプロンプトを表示しません。 シナリオは、それに関連付けられているプロバイダーと共に削除されます。 シナリオを初めて作成したときに使用したコマンドを再実行することで、シナリオを再作成できます。 削除したシナリオまたはプロバイダーを回復するための手順はありません。

    
    </div>

**Remove-CsClsScenario** コマンドレットを使用してシナリオを削除すると、シナリオはスコープから完全に削除されます。 作成したシナリオとシナリオの一部であったプロバイダーを使用するには、新しいプロバイダーを作成し、それらを新しいシナリオに割り当てます。

</div>

<div>

## <a name="see-also"></a>関連項目


[取得-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[新しい-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[削除-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[新しい-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

