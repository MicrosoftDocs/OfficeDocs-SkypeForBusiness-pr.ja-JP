---
title: 'Lync Server 2013: Microsoft Lync クライアントのポート範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cd4c109760756dd265526bd9d5285fdc9fed30
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Lync Server 2013 で Microsoft Lync クライアントのポート範囲を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-22_

既定では、Lync クライアントアプリケーションは、通信セッションに参加している場合は、ポート1024と65535の間の任意のポートを使うことができます。これは、特定のポート範囲がクライアントに対して自動的に有効にならないためです。 ただし、サービスの品質を使用するためには、さまざまな種類のトラフィック (オーディオ、ビデオ、メディア、アプリケーション共有、ファイル転送) を、一連の固有のポート範囲に割り当てる必要があります。 これを行うには、CsConferencingConfiguration コマンドレットを使用します。

<div>


> [!NOTE]  
> エンドユーザーはこれらの変更を行うことはできません。 ポートの変更は、CsConferencingConfiguration コマンドレットを使用している管理者のみが実行できます。



</div>

現在通信セッションに使用されているポート範囲を特定するには、Microsoft Lync Server 2013 管理シェルで次のコマンドを実行します。

    Get-CsConferencingConfiguration

Lync Server 2013 をインストールした後で会議の設定を変更していない場合は、次のプロパティ値を含む情報を取得する必要があります。

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

上記の出力をよく見ると、2つの重要な点が表示されます。 まず、ClientMediaPortRangeEnabled プロパティが False に設定されます。

    ClientMediaPortRangeEnabled : False

このプロパティが False に設定されている場合、通信セッションに参加するときに、Lync クライアントは、ポート1024と65535の間で利用可能なポートを使用します。これは、他のポート設定 (ClientMediaPort や ClientVideoPort など) に関係なく true になります。 指定した一連のポートに使用を制限する場合 (これは、サービスの品質の実装を計画している場合に実行します)、まずクライアントのメディアポート範囲を有効にする必要があります。 この操作を行うには、次の Windows PowerShell コマンドを使用します。

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

上のコマンドを実行すると、会議構成設定のグローバルコレクションに対してクライアントのメディアポート範囲が有効になります。ただし、これらの設定は、サイトのスコープやサービスの範囲 (会議サーバーサービスのみ) に適用することもできます。 特定のサイトまたはサーバーに対してクライアントのメディアポート範囲を有効にするには、Set-CsConferencingConfiguration を呼び出すときにそのサイトまたはサーバーの Id を指定します。

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

または、このコマンドを使用して、すべての会議構成設定のポート範囲を同時に有効にすることもできます。

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

2番目の重要な点は、既定では、各種類のネットワークトラフィックに設定されたメディアポート範囲が同じであることを示しています。

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

QoS を実装するために、これらの各ポート範囲は一意である必要があります。 たとえば、次のようなポート範囲を構成することができます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアントトラフィックの種類</th>
<th>ポートの開始</th>
<th>ポートの範囲</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オーディオ</p></td>
<td><p>50020</p></td>
<td><p>超える</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>58000</p></td>
<td><p>超える</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有</p></td>
<td><p>42000</p></td>
<td><p>超える</p></td>
</tr>
<tr class="even">
<td><p>ファイル転送</p></td>
<td><p>42020</p></td>
<td><p>超える</p></td>
</tr>
</tbody>
</table>


上の表のクライアントポート範囲は、サーバーに構成されているポート範囲のサブセットを表しています。 たとえば、サーバー上では、40803 ~ 49151 のポートを使用するようにアプリケーション共有が構成されています。クライアントコンピューターでは、[アプリケーション共有] は、42000 ~ 42019 のポートを使用するように構成されます。 これは主に、QoS の管理を簡単にするために行われています。クライアントポートは、サーバーで使われているポートのサブセットを表す必要はありません。 (たとえば、クライアントコンピューターで、1万 ~ 10019 のポートを使用するようにアプリケーション共有を構成することができます)。ただし、クライアントポート範囲をサーバーのポート範囲のサブセットにすることをお勧めします。

また、サーバー上でのアプリケーション共有のために8348のポートが設定されていても、クライアントでのアプリケーション共有については20個のポートしか設定されていないことに気付いた場合もあります。 これは推奨されていますが、ハード・ファースト・ファーストルールではありません。 一般的に、1つの通信セッションを表すために使用可能な各ポートを検討することができます。ポートの範囲内で利用可能な100ポートがある場合は、特定の時間に最大100の通信セッションに参加できることを意味します。 サーバーはクライアントよりも多くの会話に参加する可能性があるため、クライアントよりも多くのポートをサーバー上で開くことが適切です。 クライアント上のアプリケーション共有に20個のポートを確保することは、ユーザーが指定したデバイスで20個のアプリケーション共有セッションに参加することを意味します。 これは、ほとんどのユーザーにとって十分なものであることを証明する必要があります。

会議の構成設定のグローバルコレクションに上記のポート範囲を割り当てるには、次の Lync Server 管理シェルコマンドを使用できます。

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

または、このコマンドを使用して、すべての会議の構成設定にこれらと同じポート範囲を割り当てることができます。

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個々のユーザーは Lync からログオフしてから再びログインする必要があります。実際には、これらの変更は有効になります。

<div>


> [!NOTE]  
> クライアントのメディアポート範囲を有効にして、1つのコマンドを使用してこれらのポート範囲を割り当てることもできます。 例:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

