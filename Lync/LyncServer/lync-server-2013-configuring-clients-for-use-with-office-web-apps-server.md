---
title: Office Web Apps サーバーで使用するクライアントの構成
TOCTitle: Office Web Apps サーバーで使用するクライアントの構成
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48273890
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Office Web Apps サーバーで使用するクライアントの構成

 

_**トピックの最終更新日:** 2013-02-25_

Office Web App Server のフル機能をユーザーに体験してもらいたい場合は、ユーザーを Microsoft Lync 2013にアップグレードする必要があります。Lync 2013のユーザーのみが、実際の PowerPoint プレゼンテーションに関係なく PowerPoint スライドをスクロールすることなどが行えます (つまり、実際のプレゼンテーションにいかなる方法でも干渉せずに、プレゼンテーションのスライドをいつでも見ることができます)。Lync 2013を使用していないユーザーは、引き続きオンライン会議に参加したり、PowerPoint プレゼンテーションを閲覧できますが、スライドを別個にスクロールしたり、スライドの変遷を閲覧したり、埋め込まれたビデオを視聴したりすることはできません。

Lync 2013 のユーザーはこれらの機能を常に使用できることに注意してください。これは、PowerPoint 発表者が Microsoft Lync 2010 を実行している場合でも当てはまります。PowerPoint プレゼンテーションが Lync 2010 を実行しているユーザーにホストされている場合、Lync Server 2013 は Office Web Apps Server と連携して、Lync 2013 のユーザーにそのプレゼンテーションの Office Web Apps Server バージョンが表示されるようにします。Office Web Apps Server は、Lync 2013 以外のクライアントを実行しているユーザーに PowerPoint サービスを提供しません。その代わり、それらのユーザーは、Microsoft Lync Server 2010 で行った同じ方法で会議サーバー サービスに接続し、PowerPoint プレゼンテーションを閲覧します。つまり、これらのユーザーは、Lync Server 2010 によって提供されるより制限された機能へのアクセスのみが可能です。

Office Web Apps Server では、クライアント構成が不要ですが (ユーザーを Lync 2013にアップグレードすること以外)、会議出席者を Internet Explorer 9 にアップグレードすることをお勧めします。Internet Explorer 8 を使用して会議にアクセスできますが、この Web ブラウザーの使用にはいくつかの制限があります。たとえば、Internet Explorer 8 のユーザーは、PowerPoint ステージをカスタム サイズに変更できません。代わりに、事前設定された 3 つのステージ サイズのいずれかを使用するように制限されています。同様に、Internet Explorer 8 のユーザーはメディア ファイルを再生できません。

