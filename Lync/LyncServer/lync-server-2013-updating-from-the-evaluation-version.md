---
title: 'Lync Server 2013: 評価版からの更新'
description: 'Lync Server 2013: 評価版からの更新。'
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
ms.openlocfilehash: 340badf9f5d2506c50cf8c03faa82223eabbd5af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546253"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Lync Server 2013 の評価版からの更新

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-20_

Microsoft Lync Server 2013 の評価バージョンをインストールしている場合は、最終的に、そのインストールにライセンスされたソフトウェアのコピーを更新する必要があります。これは、評価版がインストールされてから180日で期限切れになるためです。 ただし、評価版を完全にアンインストールしてからライセンス版をインストールする必要はありません。 代わりに、有効なライセンスキーを取得した後で、lync server フロントエンドサーバー、ディレクター、またはエッジサーバーとして動作する各コンピューターで次の手順を実行することによって、Lync Server 2013 の評価バージョンを更新することができます。 なお、監視サーバーまたはアーカイブサーバーなど、他のサーバーの役割を実行するコンピューターを更新する必要はありません。

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013 の評価版からの更新

Lync Server 2013 の評価版からライセンス版のソフトウェアにコンピューターを更新するには、次のようにします。

**Microsoft Lync Server 2013 の評価版からの更新**

1.  ローカル管理者としてコンピューターにログオンします。

2.  [ **スタート**]、[ **すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します。
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    場合によっては、server.msi ファイルへの完全なパスを指定する必要があります。 このファイルは、Lync Server ボリュームメディアのインストールファイルのセットアップフォルダーにあります。

4.  セットアップの実行が終了したら、コマンド プロンプトから以下のコマンドを実行して、Enter キーを押します。
    
        Enable-CsComputer

5.  評価版の Lync Server を実行している他のフロントエンドサーバー、ディレクター、またはエッジサーバーでこの手順を繰り返します。 この手順は、Lync Server メディアインストールファイルを使用して展開されたすべてのブランチオフィスサーバーでも実行する必要があります。

評価版の Lync Server が特定のコンピューターで実行されているかどうかがわからない場合は、Lync Server 管理シェルから次のコマンドを実行して確認できます。

    Get-CsServerVersion

[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) コマンドレットは、ローカル コンピューターを分析して、以下のいずれかを報告します。

  - Lync Server ボリュームライセンスキーがコンピューターにインストールされていること、つまり更新が不要であることを意味します。

  - Lync Server 評価ライセンスキーがインストールされていることを意味します。つまり、コンピューターを更新する必要があります。

  - ボリューム ライセンス キーはこのコンピューターでは不要。評価版からライセンス版への更新は、フロントエンド サーバー、ディレクター、およびエッジ サーバーのみで必要。

</div>

</div>

<span> </span>

</div>

</div>

</div>

