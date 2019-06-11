---
title: 共存シナリオでの Lync Server 2010 管理パックの使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>共存シナリオでの Lync Server 2010 管理パックの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

多くのお客様は、ユーザーが Microsoft Lync Server 2010 から Lync Server 2013 に段階的に移行されている組織内でロールアウトプログラムを採用しています。 これらの会社の管理者は、両方のバージョンの Lync Server を監視して、すべてのエンドユーザーが最高のコミュニケーションエクスペリエンスを実現できるようにすることをお勧めします。 このシナリオでは、Lync Server 2013 管理パックは、Lync Server 2010 管理パックを使用してサイドバイサイドの移行パスをサポートしています。

Lync server 2010 では、Lync Server コンピューターは、中央管理ストアに保存されているトポロジドキュメントを通じて検出されました。 この構成では、1台のコンピューターで他のすべての Lync Server コンピューターの存在が報告されます。

Lync server 2013 用の管理パックで、Lync Server 2010 で使用されていたセントラル探索メカニズムではなく、マシンレベルの検出が使用されるようになりました。 つまり、各 System Center agent は基本的に自分自身を検出し、System Center Operations Manager にその存在を報告します。 マシンレベルの検出を使用すると、System Center インフラストラクチャの管理が簡単になり、さまざまなバージョンの Lync Server 管理パック (たとえば、lync Server 2010 用の管理パックと Lync Server 2013 用の管理パック) も有効になります。より簡単になります。

この移行をサポートするには、最初に既存の Lync Server 2010 監視をアップグレードして、範囲内のギャップを回避する必要があります。 これを行うには、既存の Lync Server 2010 コンピューターを選択して、中央管理ストアを Lync Server 2013 にアップグレードする前に、Lync Server 2010 のセントラル探索スクリプトを処理するようにします。 これは、4つのステップからなるプロセスです。

1.  Lync Server 2010 管理パックを累積更新プログラム7にアップグレードします。

2.  Lync Server 2010 コンピューターに、セントラル探索スクリプトを実行するように指示します。

3.  Microsoft Lync Server 2010 管理パックのセントラル探索候補を上書きします。

4.  新しいセントラル検出候補が検出されたことを確認します。

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>セントラル探索スクリプトを実行するように Lync Server 2010 コンピューターに指示する

中央の検出を処理するために、中央管理ストア以外のコンピューター (たとえば、Lync Server フロントエンド) サーバーを指名するには、次のレジストリキーをサーバーの非セントラル管理ストアサーバーに作成する必要があります。

HKLM\\ソフトウェア\\Microsoft\\リアルタイム通信\\正常性\\CentralDiscoveryCandidate

このレジストリキーを作成するには、次の手順を実行します。

1.  [**スタート**] をクリックし、[**実行**] をクリックします。

2.  [**実行**] ダイアログボックスで、「 **regedit** 」と入力し、enter キーを押します。

3.  レジストリエディターで、[ **HKEY\_ローカル\_コンピューター**]、[**ソフトウェア**]、[ **Microsoft**] の順に展開し、[**リアルタイム通信**] を展開します。

4.  [**正常性**] を右クリックし、[**新規作成**] をクリックして、[**キー**] をクリックします。 **正常性**キーが存在しない場合は、**リアルタイム通信**を右クリックし、[**新規作成**] をポイントして、[**キー**] をクリックします。 新しいキーが作成されたら、「Health」と入力して、enter キーを押します。
    
    新しいキーを作成したら、「 **CentralDiscoveryCandidate** 」と入力し、enter キーを押してキーの名前を変更します。

この変更を選択するには、コンピューターに数時間かかることがあります。 変更をすぐに有効にするには、正常性エージェントサービスを停止してから再起動します。 正常性エージェントサービスを再起動するには、Lync Server 2010 コンピューターで次の手順を実行します。

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。

2.  コンソールウィンドウで、次のコマンドを入力し、enter キーを押します。
    
        Net stop HealthService

3.  "System Center 管理サービスは停止しています" というメッセージが表示され、その後にサービスが停止されたことを示す2番目のメッセージが表示されます。 サービスが停止した後、次のコマンドを入力して ENTER キーを押すと、サービスを再起動できます。
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Lync Server 2010 管理パックでの中央の検出候補の上書き

Lync server 2010 コンピューターに Lync Server 2010 コンピューターについて報告するように指示した後、lync Server 2010 管理パックにもこの変更について通知する必要があります。 これを行うには、管理パックで上書きを作成する必要があります。 この操作を行うには、次の手順を実行します。

1.  Operations Manager コンソールで、[**作成**] をクリックします。

2.  [作成] タブで [**管理パックオブジェクト**] を展開し、[**オブジェクト**検出] をクリックして、[**スコープ**] をクリックします。

3.  [ **Scope Management Pack Objects** ] ダイアログボックスで、対象の**LS 検出候補**を含むアイテムを選び、[ **OK]** をクリックします。 LS 検出候補は、Lync Server 2010 管理パックをインストールしている場合にのみ表示されることに注意してください。

4.  Operations Manager コンソールで、[ **LS 検出候補**] を右クリックし、 ****[上書き] をポイントして、[**オブジェクト検出の上書き**] をポイントし、[ **class: LS 検出候補のすべてのオブジェクト**] をクリックします。

5.  [**プロパティの上書き**] ダイアログボックスで、[ **Central Discovery WatcherNode Fqdn**] の横にある [**上書き**] チェックボックスをオンにします。 [**上書き値**] ボックスと [**有効な値**] ボックスに、Lync Server 2010 コンピューターの完全修飾ドメイン名を入力します。 [**強制**] チェックボックスをオンにし、[ **OK]** をクリックします。

上書きを作成したら、ルート管理サーバーで正常性サービスを再起動する必要があります。 正常性サービスを再起動するには、ルート管理サーバーで次の手順を実行します。

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。

2.  コンソールウィンドウで、次のコマンドを入力し、enter キーを押します。
    
        Net stop HealthService

3.  "System Center 管理サービスは停止しています" というメッセージが表示され、その後にサービスが停止されたことを示す2番目のメッセージが表示されます。 サービスが停止した後、次のコマンドを入力して ENTER キーを押すと、サービスを再起動できます。
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>新しいセントラル探索候補が検出されたことを確認する

全体管理ストアをアップグレードする前の最後の手順では、新しいセントラル探索候補が Lync Server 2010 管理パックによって検出されたことを確認します。 これを行うには、Operations Manager コンソールを開き、[監視] をクリックします。 [監視] タブで、[ **Microsoft Lync Server 2010 正常性**] を展開し、[**トポロジの検出**] を展開して、[**検出状態の表示**] をクリックします。 表示される行に、セントラル検出候補の完全修飾ドメイン名を一覧表示する**パス**が含まれていることを確認します。 また、コンピューターの状態が**正常**であると報告されていることも確認する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

