---
title: 保留通話の内線番号の構成
TOCTitle: 保留通話の内線番号の構成
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48274196
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 保留通話の内線番号の構成

 

_**トピックの最終更新日:** 2012-09-10_

コール パーク アプリケーション は、コールをパークするために、コール パーク のオービット テーブルの内線番号を使用します。パークされた通話用に組織が予約した内線番号の範囲を指定して、コール パーク オービット テーブルを構成する必要があります。これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。コール パーク アプリケーションが展開および構成される各 Lync Server プールには、1 つ以上のオービット範囲を指定できます。オービット範囲は、Lync Server 展開でグローバルに一意である必要があります。


> [!IMPORTANT]
> コール パークを使用できるようにするには、音声ポリシーで [<STRONG>コール パークを有効にする</STRONG>] チェック ボックスをオンにする必要があります。既定では、このオプションはオフになっています。



## このセクション中

  - [Lync Server 2013 でのコール パーク オービット範囲の作成または変更](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [Lync Server 2013 でのコール パーク オービット範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)

