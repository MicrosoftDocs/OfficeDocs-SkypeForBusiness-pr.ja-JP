---
title: 共存シナリオでの Lync Server 2010 管理パックの使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8014f947a669b7b636061f17e40dee0fef287345
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>共存シナリオでの Lync Server 2010 管理パックの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

多くのお客様は、ユーザーが Microsoft Lync Server 2010 から Lync Server 2013 に段階的に移行されることで、企業の内部でロールアウトプログラムを採用しています。 これらの企業の管理者は、両方のバージョンの Lync Server を監視することに注意して、すべてのエンドユーザーが確実に最高のコミュニケーションを実現できるようにしています。 このシナリオでは、Lync server 2013 管理パックは、Lync Server 2010 管理パックとのサイドバイサイドの移行パスをサポートします。

Lync Server 2010 では、中央管理ストアに格納されているトポロジドキュメントを通じて Lync Server コンピューターが検出されました。 この構成では、1台のコンピューターが他のすべての Lync Server コンピューターの存在を報告します。

Lync server 2013 用の管理パックは、Lync Server 2010 で使用されていた中央検出メカニズムではなく、マシンレベルの検出を使用するようになりました。 これは、各 System Center エージェントが基本的に自身を検出し、その存在を System Center Operations Manager に報告することを意味します。 コンピューターレベルの探索を使用すると、システムセンターインフラストラクチャの管理が簡単になり、Lync server 管理パックの異なるバージョン (たとえば、lync server 2010 用の管理パックおよび Lync Server 2013 用の管理パック) も有効になります。より簡単に共存できます。

この移行をサポートするには、まず、既存の Lync Server 2010 監視をアップグレードして、範囲の不足を回避する必要があります。 これを行うには、中央管理ストアを Lync Server 2013 にアップグレードする前に、lync Server 2010 の中央探索スクリプトを処理する既存の Lync Server 2010 コンピューターを選択します。 このためには、次の 4 つの手順を実行します。

1.  Lync Server 2010 管理パックを累積的な更新プログラム7にアップグレードします。

2.  Lync Server 2010 コンピューターに中央探索スクリプトを実行するように指示します。

3.  Microsoft Lync Server 2010 管理パックの中央探索候補を上書きします。

4.  新しい Central Discovery Candidate が検出されていることを確認します。

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Lync Server 2010 コンピューターに Central Discovery スクリプトを実行するよう指示する

中央管理ストアコンピューター (たとえば、Lync Server フロントエンド) サーバーが集中検出を処理するように指名するには、中央管理ストアサーバーに次のレジストリキーを作成する必要があります。

HKLM\\ソフトウェア\\Microsoft\\リアルタイムコミュニケーション\\正常性\\centraldiscoverycandidate」

このレジストリ キーを作成するには、次の手順を実行します。

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  [**ファイル名を指定して実行**] ダイアログ ボックスで「**regedit**」と入力し、Enter キーを押します。

3.  レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**ソフトウェア**] を展開し、[ **Microsoft**] を展開して、[**リアルタイム通信**] を展開します。

4.  [**Health**] を右クリックし、[**新規**] をクリックして、[**キー**] をクリックします。**Health** キーが存在しない場合は、[**Real-Time Communications**] を右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。新しいキーが作成されたら、「Health」と入力し、Enter キーを押します。
    
    新しいキーが作成されたら、「**CentralDiscoveryCandidate**」と入力し、Enter キーを押してキーの名前を変更します。

コンピューターがこの変更を取得するのに数時間かかることがあります。 この変更を直ちに有効にするには、Health Agent サービスをいったん停止してから再起動します。 正常性エージェントサービスを再起動するには、Lync Server 2010 コンピューターで次の手順を実行します。

1.  [**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

2.  コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
        Net stop HealthService

3.  "System Center Management サービスが停止する" ことを知らせるメッセージが表示され、その後、サービスが停止したことを伝えるメッセージが表示されます。サービスが停止した後、次のコマンドを入力し、Enter キーを押すと、サービスを再起動できます。
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Lync Server 2010 管理パックでの Central Discovery Candidate のオーバーライド

Lync server 2010 コンピューターに Lync Server 2010 コンピューターのレポートを表示するように指示した後、lync server 2010 管理パックにもこの変更について通知する必要があります。 これを行うには、管理パックにオーバーライドを作成する必要があります。 このためには、次の手順を実行します。

1.  Operations Manager コンソールで、[**作成**] をクリックします。

2.  [作成] タブで [**管理パック オブジェクト**] を展開し、[**オブジェクト検出**] をクリックし、[**スコープ**] をクリックします。

3.  [**管理パック オブジェクトのスコープ設定**] ダイアログ ボックスで、ターゲット **LS Discovery Candidate**が指定された項目選択し、[**OK**] をクリックします。 Lync Server 2010 管理パックをインストールした場合にのみ、LS 検出候補が表示されることに注意してください。

4.  Operations Manager コンソールで、[**LS Discovery Candidate**] を右クリックし、[**上書き**]、[**オブジェクト検出の上書き**] の順にポイントし、[**クラス LS Discovery Candidate のすべてのオブジェクト**] をクリックします。

5.  [**上書きのプロパティ**] ダイアログ ボックスで、パラメーター **Central Discovery WatcherNode Fqdn** の横の [**上書き**] チェック ボックスをオンにします。 [**上書き値**] ボックスと [**有効な値**] ボックスに、Lync Server 2010 コンピューターの完全修飾ドメイン名を入力します。 [**強制**] チェック ボックスをオンにして、[**OK**] をクリックします。

オーバーライドを作成した後、ルート管理サーバーで正常性サービスを再起動する必要があります。正常性サービスを再起動するには、ルート管理サーバーで次の手順を実行します。

1.  [**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

2.  コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
        Net stop HealthService

3.  "System Center Management サービスが停止する" ことを知らせるメッセージが表示され、その後、サービスが停止したことを伝えるメッセージが表示されます。サービスが停止したら、次のコマンドを入力し、Enter キーを押して、サービスを再起動できます。
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>新しい Central Discovery Candidate が検出されたことを確認する

中央管理ストアをアップグレードする前に、最後の手順として、Lync Server 2010 管理パックによって新しい中央検出候補が検出されたことを確認します。 このためには、Operations Manager コンソールを開き、[監視] をクリックします。 [監視] タブで、[**Microsoft Lync Server 2010 Health**]、[**Topology Discovery**] の順に展開し、[**Discovery State View**] をクリックします。 表示の行の**パス**に Central Discovery Candidate の完全修飾ドメイン名が表示されていることを確認します。 コンピューターの状態が**健全**と報告されていることを確認する必要もあります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

