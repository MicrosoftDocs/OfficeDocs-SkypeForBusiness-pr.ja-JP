---
title: ベスト プラクティス アナライザー実行の要件
TOCTitle: ベスト プラクティス アナライザー実行の要件
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg591345(v=OCS.15)
ms:contentKeyID: 48271826
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ベスト プラクティス アナライザー実行の要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013、ベスト プラクティス アナライザーを使用すると、Lync Server 2013 環境をスキャンできます。以前の環境のスキャンに、これを使用することはできません。以前の環境をスキャンするには、以前のバージョンのツールを使用します。Lync Server 2010 および Office Communications Server 2007 R2 バージョンのベスト プラクティス アナライザーのダウンロードおよび使用の詳細については、「Lync Server 2010, Best Practices Analyzer」([http://go.microsoft.com/fwlink/?linkid=210536\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=256358%26clcid=0x411)) および「Best Practices Analyzer for Office Communications Server 2007 and Office Communications Server 2007 R2」([http://go.microsoft.com/fwlink/?linkid=256358\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=210651%26clcid=0x411)) を参照してください。

スキャンを開始する前に、Lync Server 2013 のすべてのコンポーネントが実行中でオンラインになっていることを確認する必要があります。

> [!NOTE]
> ファイアウォールの設定、アクセス許可など、エッジ サーバーの構成や関連する境界ネットワーク設定によっては、ベスト プラクティス アナライザーがエッジ サーバーにアクセスできず、スキャンを実行できない可能性があります。スキャン対象にエッジ サーバーが含まれ、エッジ サーバーへのアクセスに問題が発生していることがレポートで報告された場合、その問題がレポートに表示されないようにするには、エッジ サーバーをスキャン オプションから削除し、再度スキャンを実行します。

