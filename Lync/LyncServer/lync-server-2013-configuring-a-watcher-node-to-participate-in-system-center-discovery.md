---
title: System Center 検出に関与する監視ノードの構成
TOCTitle: System Center 検出に関与する監視ノードの構成
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48271370
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# System Center 検出に関与する監視ノードの構成

 

_**トピックの最終更新日:** 2012-10-22_

System Center Operations Manager の検出プロセスにウォッチャー ノードを参加させるには、System Center Operations Manager コンソールがインストールされているコンピューターで次の手順を実行する必要があります。

1.  \[**管理**\] タブで、\[**管理対象のエージェント**\] をクリックします。

2.  ウォッチャー ノード コンピューターの名前を右クリックし、\[**プロパティ**\] をクリックします。\[**プロパティ**\] ダイアログ ボックスの \[**セキュリティ**\] タブで、\[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**\] をオンにして、\[**OK**\] をクリックします。

ウォッチャー ノードがプロキシとして動作するように構成した後、ウォッチャー ノード コンピューターを再起動します。コンピューターが再起動したら、そのコンピューター上の Operations Manager イベント ログにエラー イベントが記録されていないことを確認します。コンピューターが 15 分ほど稼働した後、Operations Manager コンソールを使用して、Lync Server コンピューターが \[**Lync**\] カテゴリの下に表示されていることを確認します。

