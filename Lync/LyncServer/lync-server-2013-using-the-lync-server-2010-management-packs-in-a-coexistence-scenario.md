---
title: 共存シナリオでの Lync Server 2010 管理パックの使用
TOCTitle: 共存シナリオでの Lync Server 2010 管理パックの使用
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48272816
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共存シナリオでの Lync Server 2010 管理パックの使用

 

_**トピックの最終更新日:** 2012-10-22_

ユーザーが Microsoft Lync Server 2010 から Lync Server 2013 に徐々に移行する企業内では、多くのユーザーがロールアウト プログラムを採用します。これらの企業の管理者は、両方のバージョンの Lync Server の監視に留意し、すべてのエンド ユーザーが最良の通信環境を確実に利用できるようにします。このシナリオでは、Lync Server 2013 管理パックが、Lync Server 2010 管理パックを使用したサイド バイ サイド移行パスをサポートします。

Lync Server 2010 では、Lync Server コンピューターは、中央管理ストアに格納されたトポロジ ドキュメントを使用して検出されていました。この構成では、単一コンピューターが、他のすべての Lync Server コンピューターの存在を報告します。

Lync Server 2013 の管理パックでは、Lync Server 2010 で使用されていた中央検出メカニズムではなく、マシン レベルの検出を使用します。これは、各 System Center エージェントが基本的に自身を検出し、その存在を System Center Operations Manager に報告することを意味します。マシン レベルの検出を使用すると、System Center インフラストラクチャの管理が簡素化され、また異なるバージョンの Lync Server 管理パック (Lync Server 2010 の管理パック、Lync Server 2013 の管理パックなど) を簡単に共存させることができます。

この移行をサポートするために、まず既存の Lync Server 2010 の監視をアップグレードして、バージョン間の移行でのギャップが生じないようにする必要があります。これを行うには、Lync Server 2010 に Central Discovery スクリプトを提供する既存の Lync Server 2010 コンピューターを選択してから、中央管理ストアを Lync Server 2013 にアップグレードします。このためには、次の 4 つの手順を実行します。

1.  Lync Server 2010 管理パックを、累積的な更新プログラム 7 にアップグレードします。

2.  Lync Server 2010 コンピューターに Central Discovery スクリプトを実行するよう指示します。

3.  Microsoft Lync Server 2010 管理パックの Central Discovery Candidate をオーバーライドします。

4.  新しい Central Discovery Candidate が検出されていることを確認します。

## Lync Server 2010 コンピューターに Central Discovery スクリプトを実行するよう指示する

中央管理ストア コンピューター以外 (Lync Server フロントエンドなど) のサーバーが Central Discovery を処理するように指定するには、中央管理ストア以外のサーバーに次のレジストリ キーを作成する必要があります。

HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate

このレジストリ キーを作成するには、次の手順を実行します。

1.  \[**スタート**\] ボタンをクリックし、\[**ファイル名を指定して実行**\] をクリックします。

2.  \[**ファイル名を指定して実行**\] ダイアログ ボックスで「**regedit**」と入力し、Enter キーを押します。

3.  レジストリ エディターで、\[**HKEY\_LOCAL\_MACHINE**\]、\[**SOFTWARE**\]、\[**Microsoft**\]、\[**Real-Time Communications**\] の順に展開します。

4.  \[**Health**\] を右クリックし、\[**新規**\] をクリックして、\[**キー**\] をクリックします。**Health** キーが存在しない場合は、\[**Real-Time Communications**\] を右クリックし、\[**新規**\] をポイントして、\[**キー**\] をクリックします。新しいキーが作成されたら、「Health」と入力し、Enter キーを押します。
    
    新しいキーが作成されたら、「**CentralDiscoveryCandidate**」と入力し、Enter キーを押してキーの名前を変更します。

コンピューターがこの変更を取得するのに数時間かかることがあります。この変更を直ちに有効にするには、Health Agent サービスをいったん停止してから再起動します。Health Agent サービスを再起動するには、Lync Server 2010 コンピューターで次の手順を実行します。

1.  \[**スタート**\] ボタンをクリックし、\[**すべてのプログラム**\]、\[**アクセサリ**\] の順にクリックし、\[**コマンド プロンプト**\] を右クリックし、\[**管理者として実行**\] をクリックします。

2.  コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
        Net stop HealthService

3.  "System Center Management サービスが停止する" ことを知らせるメッセージが表示され、その後、サービスが停止したことを伝えるメッセージが表示されます。サービスが停止した後、次のコマンドを入力し、Enter キーを押すと、サービスを再起動できます。
    
        Net start HealthService

## Lync Server 2010 管理パックでの Central Discovery Candidate のオーバーライド

Lync Server 2010 コンピューターに Lync Server 2010 コンピューターについて報告するよう指示した後、Lync Server 2010 管理パックにもこの変更について通知する必要があります。これを行うには、管理パックにオーバーライドを作成する必要があります。このためには、次の手順を実行します。

1.  Operations Manager コンソールで、\[**作成**\] をクリックします。

2.  \[作成\] タブで \[**管理パック オブジェクト**\] を展開し、\[**オブジェクト検出**\] をクリックし、\[**スコープ**\] をクリックします。

3.  \[**管理パック オブジェクトのスコープ設定**\] ダイアログ ボックスで、ターゲット **LS Discovery Candidate**が指定された項目選択し、\[**OK**\] をクリックします。LS Discovery Candidate は、Lync Server 2010 管理パックをインストールしている場合にのみ表示されます。

4.  Operations Manager コンソールで、\[**LS Discovery Candidate**\] を右クリックし、\[**上書き**\]、\[**オブジェクト検出の上書き**\] の順にポイントし、\[**クラス LS Discovery Candidate のすべてのオブジェクト**\] をクリックします。

5.  \[**上書きのプロパティ**\] ダイアログ ボックスで、パラメーター **Central Discovery WatcherNode Fqdn** の横の \[**上書き**\] チェック ボックスをオンにします。\[**上書き値**\] ボックスおよび \[**有効な値**\] ボックスに Lync Server 2010 コンピューターの完全修飾ドメイン名を入力します。\[**強制**\] チェック ボックスをオンにして、\[**OK**\] をクリックします。

オーバーライドを作成した後、ルート管理サーバーで正常性サービスを再起動する必要があります。正常性サービスを再起動するには、ルート管理サーバーで次の手順を実行します。

1.  \[**スタート**\] ボタンをクリックし、\[**すべてのプログラム**\]、\[**アクセサリ**\] の順にクリックし、\[**コマンド プロンプト**\] を右クリックし、\[**管理者として実行**\] をクリックします。

2.  コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
        Net stop HealthService

3.  "System Center Management サービスが停止する" ことを知らせるメッセージが表示され、その後、サービスが停止したことを伝えるメッセージが表示されます。サービスが停止したら、次のコマンドを入力し、Enter キーを押して、サービスを再起動できます。
    
        Net start HealthService

## 新しい Central Discovery Candidate が検出されたことを確認する

中央管理ストアのアップグレード前に行う最後のステップは、新しい Central Discovery Candidate が Lync Server 2010 管理パックによって検出されたことを確認することです。このためには、Operations Manager コンソールを開き、\[監視\] をクリックします。\[監視\] タブで、\[**Microsoft Lync Server 2010 Health**\]、\[**Topology Discovery**\] の順に展開し、\[**Discovery State View**\] をクリックします。表示の行の**パス**に Central Discovery Candidate の完全修飾ドメイン名が表示されていることを確認します。コンピューターの状態が**健全**と報告されていることを確認する必要もあります。

