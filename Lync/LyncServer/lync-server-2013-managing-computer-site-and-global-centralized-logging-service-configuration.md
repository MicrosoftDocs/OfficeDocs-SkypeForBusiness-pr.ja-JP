---
title: コンピューター、サイト、グローバルな集中化されたログサービスの構成を管理する
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
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Lync Server 2013 でのコンピューター、サイト、グローバルな集中ログサービスの構成の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-04_

一元ログサービスは、1台のコンピューター、コンピューターのプール、サイトのスコープ (つまり、展開のコンピューターとプールのコレクションを含むサイトの Redmond などの定義済みサイト)、またはグローバルスコープで実行することができます (これは、[展開に含まれるすべてのコンピューターとプール] を選びます。

Lync Server 管理シェルを使用して一元的なログサービスのスコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかです。 このコマンドレットが割り当てられているすべての RBAC ロールの一覧を返すには (自分自身で作成したカスタム RBAC ロールを含む)、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell には、CLSController を使って利用できないその他のオプションとその他の構成オプションが用意されています。 CLSController は、コマンドを実行するための簡単で簡潔な方法を提供しますが、CLSController で利用できるコマンドのセットに制限されています。 Windows PowerShell は、CLSController のコマンドプロセッサで利用できるコマンドだけに限らず、幅広いコマンドと豊富なオプションを提供します。 たとえば、CLSController では、コンピューターとプールのスコープオプションが提供されます。 Windows PowerShell では、ほとんどのコマンドでコンピューターまたはプールを示すことができます。また、新しいシナリオを定義する場合は、サイトまたはグローバルスコープを定義できます。 Windows PowerShell のこの強力な機能により、サイトまたはグローバルスコープを定義できますが、実際のログはコンピューターまたはプールに制限されます。<BR>Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。 Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、トラブルシューティングシナリオには、わかりやすい方法でこれらのシナリオを再利用することもできます。 CLSController には、コマンドを発行して結果を取得するための高速で効率的な方法が用意されていますが、CLSController 用のコマンドセットは、コマンドラインから利用できる有限コマンドによって制限されます。 Windows PowerShell コマンドレットとは異なり、CLSController では、新しいシナリオを定義することはできません。サイトまたはグローバルレベルでスコープを管理することも、動的に構成できない有限コマンドセットに関するその他多くの制限事項もあります。 CLSController は、高速実行の手段を提供しますが、Windows PowerShell は、CLSController で可能な範囲を超えて一元的なログサービス機能を拡張するための手段を提供します。



</div>

-Computers パラメーターを使用して [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))、[Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))、[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))、[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))、[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))、[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) の各コマンドを実行する場合に、単一のコンピューターのスコープを定義できます。-Computers パラメーターには、対象のコンピューターの完全修飾ドメイン名 (FQDN) のコンマ区切り一覧を指定できます。

<div>


> [!TIP]
> -Pools およびログ記録コマンドを実行するプールのコンマ区切り一覧を定義することもできます。



</div>

サイトとグローバルスコープ**は、****新しい****集中化さ**れたログサービスコマンドレットで定義されます。 以下の例は、サイト スコープとグローバル スコープを設定する方法を示しています。

<div>


> [!IMPORTANT]
> 表示されるコマンドには、他のセクションで説明するパラメーターと概念が含まれている場合があります。 この例のコマンドは、スコープを定義する<STRONG>– Identity</STRONG>パラメーターの使い方を示すことを目的としており、その他のパラメーターが完全に含まれており、スコープを指定するために使用されます。 <STRONG>Set-csclsconfiguration</STRONG>コマンドレットの詳細については、「操作のドキュメントでの<A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 」をご覧ください。



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>現在の集中化ログサービス構成を取得するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Get-CsClsConfiguration

**New-CsClsConfiguration** コマンドレットと **Set-CsClsConfiguration** コマンドレットを使用して、新しい構成を作成するか、既存の構成を更新します。

**Get-CsClsConfiguration** を実行すると、次のスクリーンショットに示すような情報が表示されます。現在、この展開には既定のグローバル構成がありますが、サイト構成は定義されていません。

![Get-CsClsConfiguration からのサンプル出力](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からのサンプル出力")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>コンピューターのローカルストアから現在の集中化されたログサービス構成を取得するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Get-CsClsConfiguration -LocalStore

最初の例の " **Get-CsClsConfiguration**でパラメーターが指定されていない" という最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。 Parameter – LocalStore を指定した場合、コマンドは中央管理ストアではなくコンピューターの LocalStore を参照します。

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>現在定義されているシナリオの一覧を取得するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    たとえば、グローバル スコープで定義されているシナリオを取得するには、次のように入力します。
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

**Get-CsClsConfiguration** コマンドレットを使用すると、特定のスコープの構成に含まれるシナリオが常に表示されます。 ほとんどの場合、シナリオがすべて表示されるのではなく、一部が切り捨てられます。 ここで使用するコマンドは、すべてのシナリオおよび使用されているプロバイダー、設定、およびフラグに関する一部の情報を一覧表示します。

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して一元的なログサービスのグローバルスコープを更新するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    次に例を示します。
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、展開内の各コンピューターおよびプールの CLSAgent に指示します。すべてのサイトのコンピューターとプールがこのコマンドの対象となり、コンピューターとプールの構成済みのトレース ログのロールオーバーの値が 40 MB に設定されます。

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して一元的なログサービスのサイト範囲を更新するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    次に例を示します。
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > この例に示すように、ログ ファイルの既定の場所は %TEMP%\Tracing です。ただし、これは実際にはファイルを書き込む CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるため、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。

    
    </div>

このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。他のサイトのコンピューターとプールはこのコマンドの対象ではなく、現在構成されているトレース ログのロールオーバーの値 (既定値の 20 MB またはログ記録セッションの開始時に定義された値) が引き続き使用されます。

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>新しい一元ログサービス構成を作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-CsClsConfiguration を使用すると、オプションの多数の構成設定にアクセスできます。 構成オプションの詳細については、「 <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">CsClsConfiguration</A> 」および「 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013 での一元ログサービスの構成設定につい</A>て」を参照してください。

    
    </div>
    
    たとえば、キャッシュ ファイル用のネットワーク フォルダー、ログ ファイルのロールオーバー時間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のように入力します。
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

新しい構成の作成を慎重に計画し、一元管理サービスの新しいプロパティを定義する方法を検討してください。 変更は慎重に行い、問題のシナリオのログを適切に記録する機能に及ぼす影響について理解しておいてください。 ログの管理機能を強化する、つまり発生した問題を解決するためのサイズおよびロールオーバー時間を定義できるように構成を変更する必要があります。

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>既存の一元ログサービス構成を削除するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    たとえば、ログファイルのロールオーバー時間を増やすために作成した一元ログサービスの構成を削除するには、ロールオーバーログファイルのサイズを大きくして、次のようにログファイルキャッシュの場所をネットワーク共有に設定します。
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > これは、「新しい一元ログサービス構成を作成する」の手順で作成した新しい構成です。

    
    </div>

サイト レベルの構成の削除を選択すると、そのサイトではグローバル設定が使用されます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の一元管理されたログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Lync Server 2013 で中央集中ログサービスの構成設定を管理する](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[CsClsConfiguration の削除](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

