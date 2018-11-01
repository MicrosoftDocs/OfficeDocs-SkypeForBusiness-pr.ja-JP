---
title: "Lync Server 2013: 既存の Enterprise Edition への Standard Edition の展開"
TOCTitle: 既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48271129
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開

 

_**トピックの最終更新日:** 2012-10-01_

既存の Enterprise Edition 展開への Standard Edition サーバーの展開は、追加のサーバーの役割の展開と類似しています。Standard Edition サーバーは、別のサイトに展開される場合もあります。この場合、そのサイト内のユーザーは、ワイド エリア ネットワーク (WAN) 全体の フロント エンド プールではなく、Standard Edition サーバーに所属できます。 そのサイトに新しいサイトとサーバーをインストールする手順については、「[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」ドキュメントの他のセクションで定義されています。

**新しいサイトを定義するには**

1.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。

2.  コンソール ツリーで、**Lync Server 2013** を右クリックし、続いて \[**新しいセントラル サイト**\] をクリックします。

3.  \[**サイトの識別**\] ページでサイトに名前を付け、オプションで説明を入力します。

4.  サイト トポロジの残りを定義する手順を実行します。詳細については、「[Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

5.  更新したトポロジを公開します。詳細については、「[Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)」を参照してください。

6.  Standard Edition サーバーを設定してインストールします。
    

    > [!TIP]
    > Standard Edition サーバーのみで環境を展開した場合は、[<STRONG>最初の Standard Edition サーバーの準備</STRONG>] のリンクを使用して新しい Standard Edition サーバーに初期データベース ファイルをインストールすることで、Lync Server 展開ウィザードからセットアップ プロセスを既に開始していることになります。Standard Edition サーバーを既存の Lync Server 2013 展開にインストールする場合は、そのプロセスを実行 <STRONG>しないでください</STRONG>。


