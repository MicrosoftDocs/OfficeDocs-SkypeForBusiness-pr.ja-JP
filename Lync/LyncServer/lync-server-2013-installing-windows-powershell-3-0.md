---
title: 'Lync Server 2013: Windows PowerShell 3.0 のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35ab12cc2e00bf81bc17552253eb56417dde2c6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Lync Server 2013 用の Windows PowerShell 3.0 のインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-27_

Lync Server 2013 を正常に展開するには、Lync Server トポロジの一部である各コンピューターで Windows PowerShell 3.0 が必要になります。

Windows Server 2012 または Windows Server 2012 R2 を実行しているシステムでは、ここでは何もする必要はありません。また、次の展開ステージに進むことができます。これは、これらのオペレーティングシステムに PowerShell 3.0 が含まれているためです。

<div>


> [!IMPORTANT]  
> ただし、Windows Server 2008 R2 SP1 を実行しているシステムでは、Lync Server 2013 をインストールする前に、前提条件として PowerShell 3.0 をインストールする必要があります。そうしないと機能しないことがあります。 PowerShell 3.0 をインストールするには、「 <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>」を参照してください。 これは、PowerShell 3.0 ダウンロードページへの直接リンクであり、正常なインストールに関連する情報も含まれています。



</div>

インストールが完了した後、または Lync Server の展開を続行する前に確認しておく必要がある場合は、次のような場合には、PowerShell 3.0 がサーバーにあることを確認してください。

1.  確認するサーバーで、[**スタート**]、[すべての**プログラム**]、[**アクセサリ**]、[ **windows powershell**]、[ **windows powershell**] の順にクリックします。

2.  Windows PowerShell コンソールで、コマンドプロンプトに次のコマンドを入力し、enter キーを押します。
    
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

