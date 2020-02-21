---
title: トポロジの情報を確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 491078161d86d379ebb78baf819f5b1d888018ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>トポロジの情報を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-26_

マージが正常に完了したことを確認するための最初の手順は、Lync Server 2013 に結合した Office Communications Server 2007 R2 のトポロジ情報を表示することです。 トポロジビルダーでは、 **BackCompatSite**ノードには、結合した各 Office Communications Server 2007 R2 プールおよびサーバーの完全修飾ドメイン名 (FQDN) が表示されます。

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>トポロジ ビルダーで BackCompatSite を表示するには

1.  Office Communications Server 2007 R2 環境で、Office Communications Server 2007 R2 管理ツールを開き、従来のプールとサーバーの Fqdn をメモします。

2.  Lync Server 2013 環境で、トポロジビルダーを開き、[ **BackCompatSite** ] ノードを展開します。

3.  マージするプールおよびサーバーの FQDN がすべて表示されていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>BackCompatSite</STRONG>では、フロントエンドサーバーまたは Standard Edition サーバーに併置されているサーバーの役割に関する情報は表示されません。 Office Communications Server 2007 R2 および Lync Server 2013 間の相互運用性を実現するために必要なサーバーの役割のみが示されています。

    
    </div>

![[トポロジビルダーの BackCompatSite] ダイアログボックス](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "[トポロジビルダーの BackCompatSite] ダイアログボックス")

Lync Server 2013 コントロールパネルを使用して、結合したトポロジを表示することもできます。 Lync Server 2013 コントロールパネルでは、各サーバーの FQDN、プールの FQDN、および結合されたトポロジのサイト名を表示できます。 マージされたサーバーの [**サイト**] 列には、[**BackCompatSite**] という名前が表示されます。

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルでマージされたトポロジを表示するには

1.  Lync Server 2013 コントロールパネルを開きます。

2.  [**トポロジ**] をクリックします。

3.  [**状態**] タブで、[**サイト**] 列の [**BackCompatSite**] を見つけて、マージしたサーバーおよびプールが表示されていることを確認します。

![統合されたトポロジを示す Lync Server コントロールパネル](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "統合されたトポロジを示す Lync Server コントロールパネル")

マージ済みプールの詳細を表示するには、**Get-CsPool** コマンドレットを使用します。 このコマンドレットでは、トポロジビルダーおよび Lync Server 2013 コントロールパネルで使用可能な情報に加えて、Lync Server 2013 プールで実行されるサービスを表示します。

<div>


> [!NOTE]  
> トポロジビルダーでマージウィザードを実行した後でトポロジを公開すると、会議ディレクトリが Lync Server 2013 に統合されます。 会議ディレクトリは、 <STRONG>get-csconferencedirectory</STRONG>コマンドレットを実行して確認できます。



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>マージ済みプール上のサービスを表示するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    次に例を示します。
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>マージされた会議ディレクトリを検証するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsConferenceDirectory

3.  マージするプールまたはサーバーのすべての会議ディレクトリが Lync Server 2013 に含まれるようになっていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

