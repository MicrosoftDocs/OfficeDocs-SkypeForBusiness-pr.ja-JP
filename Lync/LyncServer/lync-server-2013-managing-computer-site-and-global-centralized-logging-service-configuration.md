---
title: コンピューター、サイト、およびグローバルな集中ログサービスの構成を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b405cef9efd63956b6d676d751027318897f5e98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Lync Server 2013 でのコンピューター、サイト、およびグローバルな集中ログサービスの構成の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-04_

集中ログサービスは、1台のコンピューター、コンピューターのプール、サイトスコープ (展開内のコンピューターとプールのコレクションが含まれているサイト Redmond などの定義済みサイト)、またはグローバルスコープ (場合があります) を含むスコープで実行できます。、展開内のすべてのコンピューターとプール)。

Lync Server 管理シェルを使用して集中ログサービススコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または、を含むカスタムの RBAC の役割を持っている必要があります。これら2つのグループのどちらか。 このコマンドレットが割り当てられているすべての RBAC の役割 (自分で作成したカスタムの RBAC の役割を含む) の一覧を返すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

例:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell には、CLSController を使用して利用できないオプションと追加の構成オプションが用意されています。 CLSController は、コマンドをすばやく、簡単に実行するための方法を提供しますが、CLSController で使用できるコマンドのセットに制限されています。 Windows PowerShell は、CLSController のコマンドプロセッサで使用可能なコマンドだけに制限されていません。また、幅広いコマンドと豊富なオプションが用意されています。 たとえば、CLSController では、– computers および–プールのスコープオプションが提供されます。 Windows PowerShell を使用すると、ほとんどのコマンドでコンピューターやプールを指定できます。また、新しいシナリオを定義するときに (CLSController にはユーザーが変更できないシナリオの数が限られています)、サイトまたはグローバルスコープを定義できます。 Windows PowerShell のこの強力な機能により、シナリオをサイトまたはグローバルスコープで定義できますが、実際のログ出力はコンピューターまたはプールに制限されます。<BR>Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。 Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、これらのシナリオをトラブルシューティングのシナリオに合わせてわかりやすく再利用できます。 CLSController では、コマンドを発行して結果を取得する高速で効率的な方法が提供されていますが、CLSController のコマンドセットは、コマンドラインから使用可能な有限コマンドによって制限されます。 Windows PowerShell コマンドレットとは異なり、CLSController では新しいシナリオを定義したり、サイトまたはグローバルレベルでスコープを管理したり、動的に構成することができない制限されたコマンドセットに関するその他の多くの制限を設けたりすることはできません。 CLSController は高速実行の手段を提供しますが、Windows PowerShell では、集中化されたログサービス機能を、CLSController で可能な範囲を超えて拡張する手段が提供されています。



</div>

1台のコンピュータースコープは、検索の実行中に定義できます。このスコープは、-Computers パラメーターを使用して、[検索-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))、 [Show-](https://technet.microsoft.com/library/JJ619173(v=OCS.15))csclslogging、 [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))、 [Stop-csclslogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))、 [Sync-csclslogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) 、および[Update-](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) csclslogging コマンドの実行中に定義できます。 – Computers パラメーターには、ターゲットコンピューターの完全修飾ドメイン名 (Fqdn) のコンマ区切りリストを指定します。

<div>


> [!TIP]
> また、ログコマンドを実行するプールとコンマで区切られた一覧を定義することもできます。



</div>

サイトとグローバルスコープは、**新しい-**、 **Set-** および**Remove-** 集中ログサービスのコマンドレットで定義されています。 次の例は、サイトとグローバルスコープを設定する方法を示しています。

<div>


> [!IMPORTANT]
> 表示されているコマンドには、他のセクションで説明しているパラメーターと概念が含まれている場合があります。 この例では、 <STRONG>-Identity</STRONG>パラメーターを使用してスコープを定義することを示し、その他のパラメーターは完全に、そのスコープを指定することを目的としています。 <STRONG>設定-csclsconfiguration</STRONG>コマンドレットの詳細については、「操作」のドキュメントの「 <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 」を参照してください。



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>現在の集中ログサービスの構成を取得するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインプロンプトで次のように入力します。
    
        Get-CsClsConfiguration

新しい構成を作成したり、既存の構成を更新したりするには、**新しい-csclsconfiguration**および**Set-csclsconfiguration**コマンドレットを使用します。

**取得-CsClsConfiguration**を実行すると、次のスクリーンショットに示すような情報が表示されます。現在、展開には既定のグローバル構成がありますが、サイト構成は定義されていません。

![Get-CsClsConfiguration からの出力例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からの出力例。")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>コンピューターのローカルストアから現在の集中ログサービスの構成を取得するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインプロンプトで次のように入力します。
    
        Get-CsClsConfiguration -LocalStore

**Get-CsClsConfiguration**でパラメーターが指定されていない最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。 パラメーター– LocalStore を指定すると、コマンドは中央管理ストアの代わりにコンピューターの LocalStore を参照します。

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>現在定義されているシナリオの一覧を取得するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインプロンプトで次のように入力します。
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    たとえば、グローバルスコープで定義されているシナリオを取得するには、次のようにします。
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

コマンドレットを**取得**すると、指定したスコープの構成の一部であるシナリオが常に表示されます。 ほとんどの場合、すべてのシナリオは表示されず、切り捨てられます。 ここで使用しているコマンドは、すべてのシナリオと、プロバイダー、設定、およびフラグを使用することに関する情報の一部を示しています。

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して集中ログサービスのグローバルスコープを更新するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインプロンプトで次のように入力します。
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    例:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

このコマンドは、展開内の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定するように指示します。 すべてのサイトのコンピューターとプールはコマンドの影響を受け、構成済みのトレースログのロールオーバー値は40メガバイトに設定されます。

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して集中ログサービスのサイトスコープを更新するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインプロンプトで次のように入力します。
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    例:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > 例に示されているように、ログファイルの既定の場所は%TEMP%\Tracing. です。 ただし、実際には、ファイルを書き込み中で、CSLAgent はネットワークサービスとして実行されるので、このような場合、%Windir%\serviceprofiles\networkservice\appdata\local には% TEMP% 変数が展開されます。

    
    </div>

このコマンドは、サイト Redmond の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定します。 他のサイト内のコンピューターとプールはコマンドの影響を受けず、現在構成されているトレースログのロールオーバー値 (既定値 (20 mb) またはログセッションの開始時) を引き続き使用します。

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>新しい集中ログサービスの構成を作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインプロンプトで次のように入力します。
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > 新しい-CsClsConfiguration を使用すると、多数のオプションの構成設定にアクセスできます。 構成オプションの詳細については、「<A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">取得-CsClsConfiguration</A> 」および「 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013 での集中ログサービスの構成設定に</A>ついて」を参照してください。

    
    </div>
    
    たとえば、キャッシュファイル用のネットワークフォルダー、ログファイルのロールオーバー期間、およびログファイルのロールオーバーサイズを定義する新しい構成を作成するには、次のように入力します。
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

新しい構成の作成を慎重に計画し、集中ログサービスの新しいプロパティを定義する方法を検討する必要があります。 変更を行って、問題のシナリオを適切にログに記録する機能への影響を理解しておく必要があります。 ログの管理能力を向上させるように構成を変更する必要があります。これにより、問題が発生したときに問題を解決するためのサイズとロールオーバー期間が向上します。

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>既存の集中ログサービスの構成を削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインプロンプトで次のように入力します。
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    たとえば、ログファイルのロールオーバー時間を長くするために作成した集中ログサービスの構成を削除するには、次のように、ロールオーバーログファイルのサイズを大きくして、ログファイルのキャッシュの場所をネットワーク共有に設定します。
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > これは、「新しい集中ログサービスの構成を作成するには」の手順で作成した新しい構成です。

    
    </div>

サイトレベルの構成の削除を選択すると、サイトではグローバル設定が使用されます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Lync Server 2013 での集中ログサービスの構成設定の管理](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[設定-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[取得-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[新しい-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[削除-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

