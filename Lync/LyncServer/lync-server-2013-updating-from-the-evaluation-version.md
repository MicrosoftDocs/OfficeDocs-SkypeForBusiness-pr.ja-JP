---
title: 'Lync Server 2013: 評価版から更新する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b4cc704a77f824cbf7b2ec8ab4920c25454f3c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Lync Server 2013 の評価版からの更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-20_

Microsoft Lync Server 2013 の評価版をインストールしている場合、最終的にソフトウェアのライセンスコピーをインストールする必要があります。これは、評価バージョンがインストールされてから180日後に期限切れになるためです。 ただし、評価版を完全にアンインストールしてから、ライセンスを取得したバージョンをインストールする必要はありません。 有効なライセンスキーを取得した後は、lync server のフロントエンドサーバー、ディレクター、またはエッジサーバーとして機能するコンピューターごとに、次の手順を実行して、Lync Server 2013 の評価バージョンを更新できます。 監視サーバーやアーカイブサーバーなど、他のサーバーの役割を実行しているコンピューターは更新する必要がないことに注意してください。

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013 の評価版からの更新

Lync Server 2013 の評価版から、ライセンスを付与されたバージョンのソフトウェアにコンピューターを更新するには、次の操作を行います。

**Microsoft Lync Server 2013 の評価版からの更新**

1.  ローカル管理者としてコンピューターにログオンします。

2.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **Lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します。
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    ファイルサーバー .msi への完全なパスを指定する必要があることに注意してください。 このファイルは、Lync Server ボリュームメディアインストールファイルのセットアップフォルダーにあります。

4.  セットアップの実行が完了したら、コマンドプロンプトで次を入力して、enter キーを押します。
    
        Enable-CsComputer

5.  評価版の Lync Server が実行されている他のフロントエンドサーバー、ディレクター、またはエッジサーバーで、この手順を繰り返します。 この手順は、Lync Server メディアインストールファイルを使用して展開されたブランチオフィスサーバーでも実行する必要があります。

Lync Server の評価版が特定のコンピューターで実行されているかどうかがわからない場合は、Lync Server 管理シェルで次のコマンドを実行して確認できます。

    Get-CsServerVersion

[CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion)コマンドレットを実行すると、ローカルコンピューターが分析され、次のいずれかが返されます。

  - Lync Server ボリュームライセンスキーがコンピューターにインストールされていることを意味します。つまり、更新は必要ありません。

  - Lync Server 評価ライセンスキーがインストールされていることを意味します。つまり、コンピューターを更新する必要があります。

  - これは、コンピューター上にボリュームライセンスキーが必要ないことを示します。 評価版からライセンス版への更新は、フロントエンドサーバー、監督、エッジサーバーでのみ行う必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

