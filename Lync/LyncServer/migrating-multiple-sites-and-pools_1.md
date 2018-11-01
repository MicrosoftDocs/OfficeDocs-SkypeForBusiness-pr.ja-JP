---
title: 複数のサイトおよびプールの移行
TOCTitle: 複数のサイトおよびプールの移行
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49886919
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 複数のサイトおよびプールの移行

 

_**トピックの最終更新日:** 2012-08-26_

Lync Server 2013 は、複数のサイトと複数のプールで構成される展開をサポートしています。Office Communications Server 2007 R2 から Lync Server 2013 に複数のプールを移行する場合は、次の点について検討する必要があります。

1.  Lync Server 2013 パイロット プールを展開した後、Lync Server 2013 プールに移動するパイロット ユーザーのサブセット、およびそれらのユーザーの機能を確認する方法を定義する必要があります。

2.  パイロット プールでのエッジ サーバーの展開後は、外部のユーザーが Lync Server 2013 プールと通信できることを確認する必要があります。

3.  フェデレーション ルートを Office Communications Server 2007 R2 エッジ サーバーから Lync Server 2013 のパイロット エッジ サーバーに移行した後は、フェデレーション ユーザーが Lync Server 2013 プールと通信できることを確認する必要があります。

4.  ユーザーおよびユーザー以外のすべての連絡先オブジェクトを移動した後、Office Communications Server 2007 R2 プールが空であることを確認する必要があります。

5.  Office Communications Server 2007 R2 プールが空であることを確認した後、プールを非アクティブ化できます。
    
    従来の Office Communications Server 2007 R2 プールおよびサーバーを非アクティブ化する方法の詳細については、「[フェーズ 10: 従来のサイトを使用停止にする](phase-10-decommission-legacy-site.md)」を参照してください。

