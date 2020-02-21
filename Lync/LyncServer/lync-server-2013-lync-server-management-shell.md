---
title: 'Lync Server 2013: Lync Server 管理シェル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc4ab6a9c32a8b060308526fcdb1f1da403a9e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理シェル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-09-20_

<div>


> [!NOTE]  
> Skype for Business のコマンドレットリファレンスが docs.microsoft.com に移動されました。 以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。 これで、GitHub を通じてコミュニティの投稿に使用できるようになるコンテンツが公開されました。 投稿に興味はありますか? ここでは、リポジトリ内の README を確認してください。<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 は、Microsoft Office Communications Server 2007 R2 で利用可能な機能と比較して、新しい機能と改善された機能のセットを導入しました。 1つの改善点は、実装を管理する方法です。 たとえば、Lync Server コントロールパネルと呼ばれる新しいユーザーインターフェイスが用意されています。これは、Microsoft 管理コンソールで最も多くのユーザーが使用しているものから大きな変化を表します。 その他の管理性の向上には、Windows PowerShell が含まれています。

Windows PowerShell を使用すると、コマンドラインから Microsoft アプリケーションを管理できます。 Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。 Windows PowerShell は、最初は2006でリリースされた Windows オペレーティングシステム用のダウンロード可能なリリースとして導入され、Microsoft Exchange Server 2007 を管理するためのコマンドラインインターフェイスとして組み込まれていました。 その時点から、成長を続け、多くの Microsoft サーバー製品に組み込まれており、Microsoft Lync Server 2013 の最新の状態になっています。 Lync Server 2010 には、展開のすべての側面を管理するために使用できる、550製品固有のコマンドレットがあります。

次のセクションには、コマンドレットの一覧とその説明が含まれます。 この情報は、コマンド ラインから直接入手することもできます。 Lync Server 管理シェルコマンドプロンプトで、次のように入力します。

    Get-Help <cmdlet name> -Full

たとえば、**New-CsVoicePolicy** コマンドレットに関するヘルプをコマンド プロンプトから取得するには、以下のように入力します。

    Get-Help New-CsVoicePolicy -Full

Lync Server 2013 での Windows PowerShell について知っておくべき事柄:

  - Lync Server コマンドレットを実行するには、Lync Server 管理シェルを開きます。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 管理シェルではなく、Windows PowerShell ウィンドウを開くと、既定で Lync Server コマンドレットを実行することはできません。 Windows PowerShell 内から Lync Server コマンドレットを実行するには、まず Windows PowerShell コマンドプロンプトで次のように入力します。<BR>Import-Module Lync

    
    </div>

  - Lync server 管理シェルは、すべての Lync Server Enterprise Edition フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。

  - Windows PowerShell および Microsoft Lync Server 2013 コマンドレットの概要と詳細情報については、「Lync Server Windows PowerShell ブログ[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

