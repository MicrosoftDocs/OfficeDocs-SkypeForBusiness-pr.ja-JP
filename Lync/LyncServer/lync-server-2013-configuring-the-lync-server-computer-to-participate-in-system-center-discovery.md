---
title: System Center 検出に関与する Lync Server コンピューターの構成
TOCTitle: System Center 検出に関与する Lync Server コンピューターの構成
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48271627
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# System Center 検出に関与する Lync Server コンピューターの構成

 

_**トピックの最終更新日:** 2012-10-20_

新しい Lync Server エージェントが System Center Operations Manager の検出プロセスに組み込まれるように、System Center Operations Manager コンソールがインストールされている各コンピューター上で次の手順を実行する必要があります。

1.  \[**管理**\] タブで、\[**管理対象のエージェント**\] をクリックします。

2.  コンピューターの名前を右クリックし、\[**プロパティ**\] をクリックします。\[**プロパティ**\] ダイアログ ボックスの \[**セキュリティ**\] タブで、\[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**\] を選択し、\[**OK**\] をクリックします。

手順 2. が完了したら、正常性エージェント サービスを再起動します (サービスを再起動すると、強制的に新しいコンピューターの検出が実行されます。サービスを再起動しないと、System Center Operations Manager によって新しいコンピューターが検出されるまでに 4 時間かかる場合があります)。サービスを再起動した後、そのコンピューター上の Operations Manager のイベント ログに、エラー イベントが記録されていないことを確認します。

