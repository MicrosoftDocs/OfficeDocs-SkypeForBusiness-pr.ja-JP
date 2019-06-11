---
title: 'Lync Server 2013: Windows PowerShell 3.0 のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Lync Server 2013 用の Windows PowerShell 3.0 のインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-27_

Lync Server 2013 を正常に展開するには、Lync Server トポロジの一部である各コンピューターに Windows PowerShell 3.0 が必要です。

Windows Server 2012 または Windows Server 2012 R2 を実行しているシステムでは、何もする必要はありません。また、これらのオペレーティングシステムに PowerShell 3.0 が含まれているため、次の展開の段階に進むことができます。

<div>


> [!IMPORTANT]  
> ただし、Windows Server 2008 R2 SP1 を実行しているシステムの場合は、Lync Server 2013 をインストールする前に PowerShell 3.0 を前提条件としてインストールする必要があります。そうしないと、動作しません。 PowerShell 3.0 をインストールするには、「 <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>」を参照してください。 これは、PowerShell 3.0 ダウンロードページへの直接リンクであり、正常にインストールされることに関する情報が含まれています。



</div>

インストールが完了したら、または確認して、Lync Server の展開を続行する前に確認してください。次のような場合は、PowerShell 3.0 がサーバーにインストールされていることを確認することが簡単です。

1.  確認するサーバーで、[**スタート**]、[すべての**プログラム**]、[**アクセサリ**]、[ **windows powershell**] の順にクリックして、[ **windows powershell**] をクリックします。

2.  Windows PowerShell コンソールで、コマンドプロンプトで次のコマンドを入力し、enter キーを押します。
    
        Get-Host | Select-Object Version

3.  Windows PowerShell 3.0 がインストールされている場合は、次のような出力が表示されます。
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

