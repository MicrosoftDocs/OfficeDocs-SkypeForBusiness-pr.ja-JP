---
title: SCOM 監視の構成
TOCTitle: SCOM 監視の構成
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49886928
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SCOM 監視の構成

 

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2013 に移行したら、次のタスクを実行し、System Center Operations Manager を操作できるように Lync Server 2013 を構成する必要があります。

  - Lync Server 2010 更新プログラムを中央検出ロジックの管理用サーバーに適用する。

  - 中央検出候補サーバーのレジストリ キーを更新する。

  - 候補中央検出ノードが上書きされるようにプライマリ System Center Operations Manager 管理サーバーを構成する。

各タスクを実行する手順を次に示します。

**Lync Server 2010 更新プログラムを中央検出ロジックの管理用サーバーに適用する。**

1.  System Center Operations Manager エージェント ファイルがインストールされ、候補検出ノードとして構成されているサーバーを選択します。

2.  Lync Server 2010 更新プログラムをこのサーバーに適用します。「[Lync Server 2010 の更新プログラムの適用](apply-lync-server-2010-updates.md)」を参照してください。

**中央検出候補サーバーのレジストリ キーを更新する。**

1.  中央検出ロジックの管理用サーバーで、Windows PowerShell コマンド ウィンドウを開きます。

2.  コマンドラインで、次のように入力します。
    
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"

       &nbsp;
    
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
    
    > [!NOTE]
    > レジストリを編集すると、&quot;レジストリ キーが既に存在する場合はコマンドが失敗する&quot; というエラーが発生することがあります。このエラーは無視しても問題ありません。


**候補中央検出監視ノードが上書きされるようにプライマリ System Center Operations Manager 管理サーバーを構成する。**

1.  System Center Operations Manager コントロールがインストールされているコンピューターで、\[ **管理パック オブジェクト**\] を展開し、\[ **オブジェクト検出**\] を選択します。

2.  \[ **スコープの変更**\] をクリックします。

3.  \[ **管理パック オブジェクトのスコープ設定**\] ページで、\[ **LS Discovery Candidate**\] を選択します。

4.  前の手順で選択した候補サーバーの名前の \[ **LS Discovery Candidate Effective Value**\] を上書きします。

最後に、変更を確定するには、System Center Operations Manager のルート管理サーバーで状態サービスを再起動します。

