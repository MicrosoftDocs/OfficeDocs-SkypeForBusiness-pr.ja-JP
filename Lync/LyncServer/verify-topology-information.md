---
title: トポロジ情報を確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>トポロジ情報を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-26_

マージが正常に完了したことを確認するための最初の手順は、Lync Server 2013 に統合した Office Communications Server 2007 R2 のトポロジ情報を表示することです。 トポロジビルダーでは、 **BackCompatSite**ノードに、マージした各 Office Communications Server 2007 R2 プールとサーバーの完全修飾ドメイン名 (FQDN) が表示されます。

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>トポロジビルダーで BackCompatSite を表示するには

1.  Office Communications Server 2007 R2 環境で、Office Communications Server 2007 R2 管理ツールを開き、従来のプールとサーバーの Fqdn をメモします。

2.  Lync Server 2013 環境で、[トポロジビルダー] を開き、[ **BackCompatSite** ] ノードを展開します。

3.  マージするプールとサーバーの Fqdn が表示されていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > フロントエンドサーバーまたは Standard Edition サーバーに併置されているサーバーの役割については、 <STRONG>BackCompatSite</STRONG>に情報は表示されません。 Office Communications Server 2007 R2 と Lync Server 2013 の間の相互運用性を確保するために必要なサーバーの役割のみが表示されます。

    
    </div>

![[トポロジビルダー BackCompatSite] ダイアログボックス](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "[トポロジビルダー BackCompatSite] ダイアログボックス")

Lync Server 2013 コントロールパネルを使用して、結合されたトポロジを表示することもできます。 Lync Server 2013 コントロールパネルでは、各サーバーの FQDN、プールの FQDN、およびマージされたトポロジのサイト名を確認できます。 結合されたサーバーには、 **BackCompatSite**の**サイト**名があります。

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルで結合されたトポロジを表示するには

1.  Lync Server 2013 コントロールパネルを開きます。

2.  [**トポロジ**] をクリックします。

3.  [**状態**] タブで、[**サイト**] 列の [ **BackCompatSite** ] を探して、マージしたサーバーとプールが表示されていることを確認します。

結合された![トポロジを示す Lync Server コントロールパネル]結合された(images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "トポロジを示す Lync Server コントロールパネル")

マージされたプールの詳細については、「 **CsPool**コマンドレットを使用する」を参照してください。 このコマンドレットでは、トポロジビルダーと Lync Server 2013 コントロールパネルで利用できる情報に加えて、Lync Server 2013 プールで実行されるサービスを表示します。

<div>


> [!NOTE]  
> トポロジビルダーでマージウィザードを実行した後にトポロジを発行すると、会議ディレクトリは Lync Server 2013 に統合されます。 <STRONG>CsConferenceDirectory</STRONG>コマンドレットを実行することで、会議ディレクトリを確認できます。



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>マージされたプールのサービスを表示するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    次に例を示します。
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>会議ディレクトリが結合されていることを確認するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsConferenceDirectory

3.  マージするプールまたはサーバーのすべての会議ディレクトリが Lync Server 2013 に表示されるようになっていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

