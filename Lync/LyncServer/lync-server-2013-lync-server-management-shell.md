---
title: 'Lync Server 2013: Lync Server 管理シェル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fdc8e5f13687d2bed0e0c35609187c57d11592
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理シェル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-09-20_

<div>


> [!NOTE]  
> Skype for Business コマンドレットリファレンスは docs.microsoft.com に移動されました。 以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。 これでコンテンツが公開され、GitHub を通じてコミュニティの投稿に使用できるようになりました。 投稿に興味をお持ちですか? ここでは、リポジトリ内の README を確認します。<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 は、Microsoft Office Communications Server 2007 R2 で利用可能な新機能と改善された機能のセットを導入しました。 改善点の1つとして、実装を管理する方法があります。 たとえば、Lync Server コントロールパネルと呼ばれる新しいユーザーインターフェイスが用意されています。このインターフェイスは、Microsoft 管理コンソールでほとんどのユーザーが使用しているものからの大きなシフトを表します。 管理性の大幅な向上には、Windows PowerShell が含まれています。

Windows PowerShell を使用すると、コマンドラインから Microsoft アプリケーションを管理できます。 コマンド ライン環境、製品固有のコマンド、完全なスクリプト言語が用意されています。 Windows PowerShell は、最初に2006の Windows オペレーティングシステムのダウンロード可能なリリースとして導入されましたが、Microsoft Exchange Server 2007 の管理のためのコマンドラインインターフェイスとして採用されています。 この時点では、今後も成長し、Microsoft Server 製品のほとんどに組み込まれており、最新の microsoft Lync Server 2013 になっています。 Lync Server 2010 は、展開のすべての局面を管理するために使用できる、550製品固有のコマンドレットに近い方法で導入されています。

以降のセクションに、コマンドレットの一覧とその説明を示します。 この情報は、コマンド ラインで直接表示することもできます。 Lync Server 管理シェルのコマンドプロンプトで次のように入力します。

    Get-Help <cmdlet name> -Full

たとえば、**New-CsVoicePolicy** コマンドレットに関するヘルプをコマンド プロンプトで表示するには、以下のように入力します。

    Get-Help New-CsVoicePolicy -Full

Lync Server 2013 での Windows PowerShell について知っておくべきこと:

  - Lync Server のコマンドレットを実行するには、Lync Server 管理シェルを開きます。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 管理シェルではなく、Windows PowerShell ウィンドウを開いた場合、既定では、Lync Server コマンドレットを実行することはできません。 Windows PowerShell 内から Lync Server コマンドレットを実行するには、Windows PowerShell コマンドプロンプトで次のように入力します。<BR>インポート-モジュール Lync

    
    </div>

  - Lync Server 管理シェルは、すべての Lync Server Enterprise Edition のフロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。

  - 新規および更新された情報、サンプルスクリプト、および使用を開始するためのヘルプ、および Windows PowerShell と Microsoft Lync Server 2013 コマンドレットの詳細につい[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)ては、「Lync Server Windows powershell ブログ」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

